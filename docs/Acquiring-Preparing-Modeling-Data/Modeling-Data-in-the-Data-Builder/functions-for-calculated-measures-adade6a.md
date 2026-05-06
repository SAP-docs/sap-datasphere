<!-- loioadade6acba974203a71f3fdb4fd4e4b4 -->

# Functions for Calculated Measures

This is a list of functions you can use in expressions for calculated measures.



## Numeric Functions


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

ABS\(number\)

</td>
<td valign="top">

Returns the absolute value of a number \(the number without its sign\).

</td>
<td valign="top">

```
ABS( <num>)
```



</td>
<td valign="top">

`ABS(-11)` returns 11

</td>
</tr>
<tr>
<td valign="top">

EXP\(number\)

</td>
<td valign="top">

Natural exponential function. Returns the value of e \(2.718\) raised to a power.

</td>
<td valign="top">

```
EXP( <number>)
```



</td>
<td valign="top">

`EXP(3)` returns 20.0855

</td>
</tr>
<tr>
<td valign="top">

Floor

</td>
<td valign="top">

Returns the largest integer that is not greater than the specified numeric argument.

</td>
<td valign="top">

```
FLOOR( <number>)
```



</td>
<td valign="top">

***FLOOR\(14.8\)*** returns the value 14

***FLOOR\(14.82,0\)*** returns the value 14

***FLOOR\(14.82,1\)*** returns the value 14.8

***FLOOR\(14.82,-1\)*** returns the value 10

</td>
</tr>
<tr>
<td valign="top">

LN \(LOG\)

</td>
<td valign="top">

Returns the natural logarithm of a number.

</td>
<td valign="top">

```
LN( <number>)
```



</td>
<td valign="top">

`LOG(100)` returns 4.605

</td>
</tr>
<tr>
<td valign="top">

LOG \(LOG10\)

</td>
<td valign="top">

Returns the natural logarithm of a number specified by <number\> and a base specified by <base\>, where <base\> must be a positive value greater than 1, and <number\> must be any positive value.

</td>
<td valign="top">

```
LOG( <base>,  <number>)
```



</td>
<td valign="top">

```
LOG (10, 2)
```

returns the natural logarithm for 2 base 10, which is ***0.30102999566398114***

</td>
</tr>
<tr>
<td valign="top">

MOD \(%\)

</td>
<td valign="top">

Returns the remainder of a number <number\> divided by a divisor <divisor\>.

When <number\> is negative, this function acts differently to the standard computational modulo operation. The following list shows examples of what the MOD function returns as the result:

-   If <divisor\> is zero, then <number\> is returned.
-   If *<number\>* is greater than 0 and *<number\>* is less than *<divisor\>*, then *<number\>* is returned.

-   If *<number\>* is less than 0 and *<number\>* is greater than *<divisor\>*, then *<number\>* is returned.

-   In cases other than those mentioned above, the remainder of the absolute value of *<number\>* divided by the absolute value of *<divisor\>* is used to calculate the remainder. If *<number\>* is less than 0, then the returned remainder from MOD is a negative number, and if *<number\>* is greater than 0, then the returned remainder from MOD is a positive number.




</td>
<td valign="top">

```
MOD( <number>,  <divisor>)
```



</td>
<td valign="top">

`MOD(15,2)` returns the value 1

`MOD (15, 4)` returns the value ***3***

`MOD (-15, 4)` returns the value ***\-3***

</td>
</tr>
<tr>
<td valign="top">

POWER \(\*\*\)

</td>
<td valign="top">

Calculates a specified base number raised to the power of a specified exponent.

</td>
<td valign="top">

```
POWER( <base>,  <exponent>)
```



</td>
<td valign="top">

`POWER(2,10)` returns the value ***1024*** 

</td>
</tr>
<tr>
<td valign="top">

SQRT

</td>
<td valign="top">

Returns the square root of a number.

</td>
<td valign="top">

```
SQRT( <number>)
```



</td>
<td valign="top">

`SQRT(4)` returns 2

</td>
</tr>
<tr>
<td valign="top">

GrandTotal

</td>
<td valign="top">

Returns the grand total of all the values in the result set of the measure argument <measure\>.

</td>
<td valign="top">

```
GrandTotal(<measure>)
```



</td>
<td valign="top">

`GrandTotal(Sales)` returns the aggregated value of Sales.

</td>
</tr>
<tr>
<td valign="top">

PercentOfGrandTotal

</td>
<td valign="top">

Returns the percentage of Grand Total of all the values in the result set of the measure argument <measure\>.

</td>
<td valign="top">

```
PercentOfGrandTotal(<measure>)
```



</td>
<td valign="top">

`%GrandTotal(Sales)` returns the percentage of the grand total that each value represents.

</td>
</tr>
</table>



## Miscellaneous Functions


<table>
<tr>
<th valign="top">

Function

</th>
<th valign="top">

Description

</th>
<th valign="top">

Example

</th>
</tr>
<tr>
<td valign="top">

GREATEST \(MAX\)

</td>
<td valign="top">

Returns the largest of two or more numbers.

</td>
<td valign="top">

`MAX(10,20,15)` returns the value 20

</td>
</tr>
<tr>
<td valign="top">

LEAST \(MIN\)

</td>
<td valign="top">

Returns the smallest of two or more numbers.

</td>
<td valign="top">

`MIN(10,20,15)` returns the value 10

</td>
</tr>
</table>



## Date Type Conversion


<table>
<tr>
<th valign="top">

Function

</th>
<th valign="top">

Description

</th>
<th valign="top">

Example

</th>
</tr>
<tr>
<td valign="top">

TO\_DATE\(\)

</td>
<td valign="top">

Converts a date string into the DATE format.

</td>
<td valign="top">

`TO_DATE('2010-01-12', 'YYYY-MM-DD')` returns 2010-01-12 or another format such as Jan 12, 2010. The format depends on your date display settings.

</td>
</tr>
<tr>
<td valign="top">

TO\_DECIMAL \(DECFLOAT\)

</td>
<td valign="top">

Converts a value to a decimal data type.

</td>
<td valign="top">

`DECFLOAT("14.6")` returns 14.6

</td>
</tr>
<tr>
<td valign="top">

TO\_DOUBLE \(DOUBLE\)

</td>
<td valign="top">

Converts a value to a DOUBLE data type.

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

TO\_INT \(INT\)

</td>
<td valign="top">

Converts a value to an integer data type.

</td>
<td valign="top">

***INT\(9.5\)*** returns the value 9

</td>
</tr>
<tr>
<td valign="top">

TO\_INTEGER \(INT\)

</td>
<td valign="top">

Converts the ARG <value\>-ARG to an INTEGER data type.

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

TO\_REAL \(FLOAT\)

</td>
<td valign="top">

Converts a ARG <value\>-ARG to a REAL data type.

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

TO\_TIME\(\)

</td>
<td valign="top">

Converts a time string into a time format.

</td>
<td valign="top">

`ToTime(Sep 18, 2020 5:51:06 AM) returns 5:51:06 AM)` returns 5:51:06 AM

</td>
</tr>
<tr>
<td valign="top">

TO\_TIMESTAMP

</td>
<td valign="top">

Converts a date string to a TIMESTAMP data type.

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

TO\_VARCHAR

</td>
<td valign="top">

Converts a given value to a VARCHAR data type, with an option to format the output value.

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

CAST

</td>
<td valign="top">

Returns the value of an expression converted to a supplied data type.

</td>
<td valign="top">

 

</td>
</tr>
</table>



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

Example

</th>
</tr>
<tr>
<td valign="top">

DAYS\_BETWEEN

</td>
<td valign="top">

Computes the number of entire \(24 hour\) days between two dates.

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

MONTHS\_BETWEEN

</td>
<td valign="top">

Computes the number of seconds between two specified dates.

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

SECONDS\_BETWEEN

</td>
<td valign="top">

Computes the number of seconds between two specified dates.

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

YEARS\_BETWEEN

</td>
<td valign="top">

Computes the number of years between two specified dates.

</td>
<td valign="top">

 

</td>
</tr>
</table>

