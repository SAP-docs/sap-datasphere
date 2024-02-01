<!-- loio88ca394d455642ccbdd3102298de7959 -->

# Aggregation and Exception Aggregation

Aggregation is a process to summarize measures, for example, by grouping values of multiple rows into a single result.

The standard aggregation is used to aggregate with respect to any dimension not in query drill-down. Exception aggregation is always performed in addition to standard aggregation. It defines the exception: It is used to aggregate with respect to the defined dimensions for exception aggregation. You can use exception aggregation if warehouse stock cannot be totaled up at the time, or if counters count the number of dimensions for a specific dimension.

A measure is calculated in the following order: first the standard aggregation, then the formula, and then the exception aggregation.

> ### Note:  
> Using many dimensions in an exception aggregation will have an impact on the performance. This is because more data must be processed after the main aggregation, which uses the SAP HANA build-in engines and data structures. While these engines can use optimized data storage and processes, the exception aggregation is more generic and slower than the low level aggregation.



<a name="loio88ca394d455642ccbdd3102298de7959__section_d4w_ptq_5zb"/>

## Examples



### Calculate Stock

You want to calculate the stock at the beginning of a month and the end of the month. You can do that by creating two measures: one with different exception aggregation behavior First and one with exception aggregation behavior Last.

With exception aggregation First, only the value of the first day in the month is taken and with exception aggregation Last, only the value of the last day in the month is taken.



### Count Number of Customers Within a Year


<table>
<tr>
<th valign="top">

Count Number of Customers per Year \(2022\)

</th>
<th valign="top">

NetAmount 2022

</th>
<th valign="top">

Number of Customers in 2022

</th>
<th valign="top">

Average NetAmount per Customer

</th>
</tr>
<tr>
<td valign="top">

Colorado

</td>
<td valign="top">

55,871.75 $

</td>
<td valign="top">

35

</td>
<td valign="top">

1,596.34 $

</td>
</tr>
<tr>
<td valign="top">

Conneticut

</td>
<td valign="top">

7,924.00 $

</td>
<td valign="top">

5

</td>
<td valign="top">

1,584.80 $

</td>
</tr>
<tr>
<td valign="top">

Delaware

</td>
<td valign="top">

35,217.10 $

</td>
<td valign="top">

7

</td>
<td valign="top">

5,031.01 $

</td>
</tr>
<tr>
<td valign="top">

Florida

</td>
<td valign="top">

10,634.35 $

</td>
<td valign="top">

14

</td>
<td valign="top">

759.60 $

</td>
</tr>
<tr>
<td valign="top">

Florida

</td>
<td valign="top">

47,895.40 $

</td>
<td valign="top">

25

</td>
<td valign="top">

1,915.82 $

</td>
</tr>
<tr>
<td valign="top">

Florida

</td>
<td valign="top">

582.85 $

</td>
<td valign="top">

1

</td>
<td valign="top">

582.85 $

</td>
</tr>
<tr>
<td valign="top">

Maryland

</td>
<td valign="top">

1,521.15 $

</td>
<td valign="top">

4

</td>
<td valign="top">

380.29 $

</td>
</tr>
<tr>
<td valign="top">

Pennsylvania

</td>
<td valign="top">

53,748.20 $

</td>
<td valign="top">

23

</td>
<td valign="top">

2,336.88 $

</td>
</tr>
</table>

The above query shows the companies, revenue of 2022 in combination with the number of customers within this year. The special aspect here is, that the "counting of the customers" does not need to have the CUSTOMER dimension itself within the current result set. The aggregation is done over exception aggregation and over the exception aggregation dimension CUSTOMER for the counting. This allows you to leave the dimension CUSTOMER out of the result set. Based on this you can have further analysis, e.g. with a formula which calculates the average revenue per customer in the year.

