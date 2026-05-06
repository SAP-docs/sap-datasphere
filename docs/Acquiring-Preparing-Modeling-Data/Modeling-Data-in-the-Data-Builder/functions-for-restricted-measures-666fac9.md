<!-- loio666fac98493f49d788b3ba72017a5012 -->

# Functions for Restricted Measures

This is a list of functions you can use in expressions for restricted measures.



## Date Time Functions


<table>
<tr>
<th valign="top">

Function

</th>
<th valign="top">

Description

</th>
<th valign="top">

Syntax

</th>
<th valign="top">

Example

</th>
</tr>
<tr>
<td valign="top">

YTD \(Year to Date\)

</td>
<td valign="top">

Sums the aggregated values from the beginning of the year to the current date.

</td>
<td valign="top">

Without Hierarchy

```
"DATE_DIM" = YTD()
```

With Hierarchy

```
"DATE_DIM" = YTD('YQM') 
```



</td>
<td valign="top">

The following example returns the sum of the values for ExpectedClosingDate from the beginning of the year to the current date:

```
 "ExpectedClosingDate" = YTD();
```

.

</td>
</tr>
<tr>
<td valign="top">

MTD \(Month to Date\)

</td>
<td valign="top">

Sums the aggregated values from the beginning of the month to the current date.

</td>
<td valign="top">

Without Hierarchy

```
"DATE_DIM" = MTD()
```

With Hierarchy

```
"DATE_DIM" = MTD('YQM') 
```



</td>
<td valign="top">

The following example returns the sum of the values from the beginning of the month to the current date:

```
 "ExpectedClosingDate" = MTD();
```



</td>
</tr>
<tr>
<td valign="top">

QTD \(Quarter to Date\)

</td>
<td valign="top">

Sums the aggregated values from the beginning of the quarter to the current date.

</td>
<td valign="top">

Without Hierarchy

```
"DATE_DIM" = QTD()
```

With Hierarchy

```
"DATE_DIM" = QTD('YQM') 
```



</td>
<td valign="top">

The following example returns the sum of the values from the beginning of the quarter to the current date:

```
 "ExpectedClosingDate" = QTD();
```



</td>
</tr>
</table>

