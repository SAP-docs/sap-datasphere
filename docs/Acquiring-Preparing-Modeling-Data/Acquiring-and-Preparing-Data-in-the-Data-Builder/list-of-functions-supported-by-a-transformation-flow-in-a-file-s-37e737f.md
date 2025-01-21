<!-- loio37e737fc0aee4ac7bcee4660d189dc26 -->

# List of Functions Supported by a Transformation Flow \(in a File Space\)

Review the list of functions supported by a graphical view transform of a tranformation flow in a file space.

A graphical view transform of a transformation flow created in a file space can support the following functions:



<a name="loio37e737fc0aee4ac7bcee4660d189dc26__section_bpk_cld_bdc"/>

## Aggregate Functions


<table>
<tr>
<th valign="top">

Functions

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

AVG

</td>
<td valign="top">

Returns the arithmetical mean of the expression. This function can also be used as a window function.

</td>
</tr>
<tr>
<td valign="top">

CORR

</td>
<td valign="top">

Computes the Pearson product momentum correlation coefficient between two columns. This function can also be used as a window function.

</td>
</tr>
<tr>
<td valign="top">

COUNT

</td>
<td valign="top">

Counts the number of rows returned by a query. This function can also be used as a window function.

</td>
</tr>
<tr>
<td valign="top">

NTH\_VALUE

</td>
<td valign="top">

Returns the value of an element at a specific position in an expression. This function can also be used as a window function.

</td>
</tr>
<tr>
<td valign="top">

FIRST\_VALUE

</td>
<td valign="top">

Returns the value of the first element of an expression. This function can also be used as a window function.

</td>
</tr>
<tr>
<td valign="top">

MAX

</td>
<td valign="top">

Returns the maximum value of the expression. This function can also be used as a window function.

</td>
</tr>
<tr>
<td valign="top">

MEDIAN

</td>
<td valign="top">

Finds the statistical median of an input expression with a numeric data type. This function can also be used as a window function.

</td>
</tr>
<tr>
<td valign="top">

MIN

</td>
<td valign="top">

Returns the minimum value of the expression. This function can also be used as a window function.

</td>
</tr>
<tr>
<td valign="top">

STDDEV

</td>
<td valign="top">

Returns the standard deviation of the given expression as the square root of the VAR function. This function can also be used as a window function.

</td>
</tr>
<tr>
<td valign="top">

STDDEV\_POP

</td>
<td valign="top">

Returns the standard deviation of a given expression as the square root of the VAR\_POP function.

</td>
</tr>
<tr>
<td valign="top">

STDDEV\_SAMP

</td>
<td valign="top">

Returns the standard deviation of the given expression as the square root of VAR\_SAMP function.

</td>
</tr>
<tr>
<td valign="top">

SUM

</td>
<td valign="top">

Returns the sum of the expression. This function can also be used as a window function.

</td>
</tr>
<tr>
<td valign="top">

VARIANCE\(EXPR\)

</td>
<td valign="top">

Returns the variance of the given expression as the square of the standard deviation.

> ### Note:  
> It corresponds to the function VAR for a transformation flow created in an SAP HANA space.



</td>
</tr>
<tr>
<td valign="top">

VAR\_POP

</td>
<td valign="top">

Returns the population variance of an expression.

</td>
</tr>
<tr>
<td valign="top">

VAR\_SAMP

</td>
<td valign="top">

Returns the sample variance of an expression.

</td>
</tr>
</table>



<a name="loio37e737fc0aee4ac7bcee4660d189dc26__section_ijf_w4d_bdc"/>

## Numeric Functions


<table>
<tr>
<th valign="top">

Functions

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

ABS

</td>
<td valign="top">

Returns the absolute value of a numeric argument.

</td>
</tr>
<tr>
<td valign="top">

ACOS

</td>
<td valign="top">

Returns the arc-cosine, in radians, of a numeric argument between -1 and 1.

</td>
</tr>
<tr>
<td valign="top">

BIT\_AND\(EXPR\)

</td>
<td valign="top">

Performs an AND operation on the bits of two arguments.

> ### Note:  
> It corresponds to the function BITAND\(value1, value2\) for a transformation flow created in an SAP HANA space.



</td>
</tr>
<tr>
<td valign="top">

BIT\_COUNT\(EXPR\)

</td>
<td valign="top">

Counts the number of set bits of an expression.

> ### Note:  
> It corresponds to the function BITCOUNT\(expr\) for a transformation flow created in an SAP HANA space.



</td>
</tr>
<tr>
<td valign="top">

~EXPR

</td>
<td valign="top">

Performs a bitwise NOT operation on the bits of an expression.

> ### Note:  
> It corresponds to the function BITNOT for a transformation flow created in an SAP HANA space.



</td>
</tr>
<tr>
<td valign="top">

BIT\_OR\(EXPR\)

</td>
<td valign="top">

This function performs an OR operation on the bits of two arguments.

> ### Note:  
> It corresponds to the function BITOR\(exp1, exp2\) for a transformation flow created in an SAP HANA space.



</td>
</tr>
<tr>
<td valign="top">

BIT\_XOR

</td>
<td valign="top">

Performs an XOR operation on the bits of two arguments.

> ### Note:  
> It corresponds to the function BITXOR for a transformation flow created in an SAP HANA space.



</td>
</tr>
<tr>
<td valign="top">

CEIL

</td>
<td valign="top">

Returns the first integer that is greater than or equal to the specified value.

</td>
</tr>
<tr>
<td valign="top">

COS

</td>
<td valign="top">

Returns the cosine of the angle, in radians, for the specified argument.

</td>
</tr>
<tr>
<td valign="top">

COSH

</td>
<td valign="top">

Computes the hyperbolic cosine of the specified argument.

</td>
</tr>
<tr>
<td valign="top">

COT

</td>
<td valign="top">

Computes the cotangent of a specified number.

</td>
</tr>
<tr>
<td valign="top">

EXP

</td>
<td valign="top">

Returns the result of the base of the natural logarithms e raised to the power of the specified argument.

</td>
</tr>
<tr>
<td valign="top">

FLOOR

</td>
<td valign="top">

Returns the largest integer that is not greater than the specified numeric argument.

</td>
</tr>
<tr>
<td valign="top">

LN

</td>
<td valign="top">

Returns the natural logarithm of a number.

</td>
</tr>
<tr>
<td valign="top">

LOG

</td>
<td valign="top">

Returns the natural logarithm of a specified number and base.

</td>
</tr>
<tr>
<td valign="top">

MOD

</td>
<td valign="top">

Returns the remainder of a specified number divided by a specified divisor.

</td>
</tr>
<tr>
<td valign="top">

POWER

</td>
<td valign="top">

Calculates a specified base number raised to the power of a specified exponent.

</td>
</tr>
<tr>
<td valign="top">

RAND

</td>
<td valign="top">

Returns a pseudo-random DOUBLE value.

</td>
</tr>
<tr>
<td valign="top">

ROUND

</td>
<td valign="top">

Rounds the specified argument to the specified amount of places after the decimal point.

</td>
</tr>
<tr>
<td valign="top">

SIGN

</td>
<td valign="top">

Returns the sign \(positive or negative\) of the specified numeric argument.

</td>
</tr>
<tr>
<td valign="top">

SIN

</td>
<td valign="top">

Returns the sine of an angle expressed in radians.

</td>
</tr>
<tr>
<td valign="top">

SINH

</td>
<td valign="top">

Returns the hyperbolic sine of an angle expressed in radians.

</td>
</tr>
<tr>
<td valign="top">

SQRT

</td>
<td valign="top">

Returns the square root of the specified argument.

</td>
</tr>
<tr>
<td valign="top">

TAN

</td>
<td valign="top">

Returns the tangent of a specified number, where the argument is an angle expressed in radians.

</td>
</tr>
<tr>
<td valign="top">

TANH

</td>
<td valign="top">

Returns the hyperbolic tangent of the specified numeric argument.

</td>
</tr>
<tr>
<td valign="top">

NEGATIVE\(EXPR\)

</td>
<td valign="top">

Returns the negated value of the specified numeric argument.

> ### Note:  
> It corresponds to the function UMINUS for a transformation flow created in an SAP HANA space.



</td>
</tr>
</table>



<a name="loio37e737fc0aee4ac7bcee4660d189dc26__section_ifx_krd_bdc"/>

## Date Time Functions


<table>
<tr>
<th valign="top">

Functions

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

DATE\_ADD , DATEADD

</td>
<td valign="top">

Computes the specified date, plus or minus the specified number of days.

> ### Note:  
> It corresponds to the function ADD\_DAYS for a transformation flow created in an SAP HANA space.



</td>
</tr>
<tr>
<td valign="top">

ADD\_MONTHS

</td>
<td valign="top">

Computes the specified date plus the specified number of months.

</td>
</tr>
<tr>
<td valign="top">

CURRENT\_DATE

</td>
<td valign="top">

Returns the current local system date.

</td>
</tr>
<tr>
<td valign="top">

CURRENT\_TIMESTAMP

</td>
<td valign="top">

Returns the current local system timestamp information.

</td>
</tr>
<tr>
<td valign="top">

LOCALTIMESTAMP

</td>
<td valign="top">

Returns the local system time.

> ### Note:  
> It corresponds to the function CURRENT\_TIME for a transformation flow created in an SAP HANA space.



</td>
</tr>
<tr>
<td valign="top">

DAYOFMONTH

</td>
<td valign="top">

Returns the day of the month for the specified date.

</td>
</tr>
<tr>
<td valign="top">

DAYOFYEAR

</td>
<td valign="top">

Returns an integer representation of the day of the year for the specified date.

</td>
</tr>
<tr>
<td valign="top">

DATE\_DIFF\(ENDDATE,STARTDATE\)

</td>
<td valign="top">

Computes the number of entire \(24 hour\) days between two dates.

> ### Note:  
> It corresponds to the function DAYS\_BETWEEN for a transformation flow created in an SAP HANA space.



</td>
</tr>
<tr>
<td valign="top">

EXTRACT

</td>
<td valign="top">

Returns the requested portion of a specified date.

</td>
</tr>
<tr>
<td valign="top">

HOUR

</td>
<td valign="top">

Returns an integer representation of the hour portion of the specified time.

</td>
</tr>
<tr>
<td valign="top">

LAST\_DAY

</td>
<td valign="top">

Returns the date of the last day of the month that contains the specified date.

</td>
</tr>
<tr>
<td valign="top">

TO\_UTC\_TIMESTAMP\(TIMESTAMP,TIMEZONE\)

</td>
<td valign="top">

A timestamp parameter holding the time to be converted between UTC and local time.

> ### Note:  
> It corresponds to the function LOCALTOUTC for a transformation flow created in an SAP HANA space.



</td>
</tr>
<tr>
<td valign="top">

MINUTE

</td>
<td valign="top">

Returns an integer representation of the minute for the specified time.

</td>
</tr>
<tr>
<td valign="top">

MONTH

</td>
<td valign="top">

Returns the number of the month from the specified date.

</td>
</tr>
<tr>
<td valign="top">

MONTHS\_BETWEEN

</td>
<td valign="top">

Computes the number of months between two dates.

</td>
</tr>
<tr>
<td valign="top">

NOW

</td>
<td valign="top">

Returns the current timestamp.

</td>
</tr>
<tr>
<td valign="top">

SECOND

</td>
<td valign="top">

Returns the second portion of a specified time.

</td>
</tr>
<tr>
<td valign="top">

WEEKOFYEAR\(DATE\)

</td>
<td valign="top">

Returns a week number between 1 and 54 for the specified date.

> ### Note:  
> It corresponds to the function WEEK for a transformation flow created in an SAP HANA space.



</td>
</tr>
<tr>
<td valign="top">

WEEKDAY

</td>
<td valign="top">

Returns the day of the week for the specified date.

</td>
</tr>
<tr>
<td valign="top">

YEAR

</td>
<td valign="top">

Returns the year number of a specified date.

</td>
</tr>
<tr>
<td valign="top">

FROM\_UTC\_TIMESTAMP\(TIMESTAMP,TIMEZONE\)

</td>
<td valign="top">

Converts the specified timestamp between UTC and local time.

> ### Note:  
> It corresponds to the function UTCTOLOCAL for a transformation flow created in an SAP HANA space.



</td>
</tr>
<tr>
<td valign="top">

QUARTER\(DATE\) - returns a number in range \(1,4\)

</td>
<td valign="top">

Returns the quarter for the specified date. Returns a number in range \(1,4\).

> ### Note:  
> It corresponds to the function QUARTER\(DATE,START\_MONTH\) for a transformation flow created in an SAP HANA space.



</td>
</tr>
</table>



<a name="loio37e737fc0aee4ac7bcee4660d189dc26__section_mgx_btd_bdc"/>

## Miscellaneous Functions


<table>
<tr>
<th valign="top">

Functions

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

COALESCE

</td>
<td valign="top">

Returns the first non-NULL expression from a specified list.

</td>
</tr>
<tr>
<td valign="top">

CONCAT

</td>
<td valign="top">

Returns a combined string consisting of two specified strings.

</td>
</tr>
<tr>
<td valign="top">

CURRENT\_SCHEMA

</td>
<td valign="top">

Returns a string containing the current schema name.

</td>
</tr>
<tr>
<td valign="top">

CURRENT\_USER

</td>
<td valign="top">

Returns the current user name at the current statement context.

</td>
</tr>
<tr>
<td valign="top">

GREATEST

</td>
<td valign="top">

Returns the greatest value among the specified arguments.

</td>
</tr>
<tr>
<td valign="top">

GROUPING

</td>
<td valign="top">

Determines whether a specified column is used in grouping.

</td>
</tr>
<tr>
<td valign="top">

GROUPING\_ID

</td>
<td valign="top">

Returns an integer value to identify which grouping set each row belongs to.

</td>
</tr>
<tr>
<td valign="top">

IFNULL

</td>
<td valign="top">

Returns the first non-NULL input expression.

</td>
</tr>
<tr>
<td valign="top">

LEAST

</td>
<td valign="top">

Returns the lesser value of two specified arguments.

</td>
</tr>
<tr>
<td valign="top">

NULLIF

</td>
<td valign="top">

Determines whether two expressions are equal.

</td>
</tr>
<tr>
<td valign="top">

UUID\(\)

</td>
<td valign="top">

Returns a new universally unique identifier that is generated by the connected SAP HANA instance.

> ### Note:  
> It corresponds to the function SYSUUID for a transformation flow created in an SAP HANA space.



</td>
</tr>
<tr>
<td valign="top">

WIDTH\_BUCKET

</td>
<td valign="top">

Returns the bucket number that has been assigned to the result of a specified expression.

</td>
</tr>
</table>



<a name="loio37e737fc0aee4ac7bcee4660d189dc26__section_etz_ntd_bdc"/>

## String Functions


<table>
<tr>
<th valign="top">

Functions

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

ASCII

</td>
<td valign="top">

Returns the integer ASCII value of the first character in a specified string.

</td>
</tr>
<tr>
<td valign="top">

ASIN

</td>
<td valign="top">

Returns the arc-sine, in radians, of a numeric argument.

</td>
</tr>
<tr>
<td valign="top">

ATAN

</td>
<td valign="top">

Returns the arc-tangent, in radians, of a numeric argument.

</td>
</tr>
<tr>
<td valign="top">

ATAN2

</td>
<td valign="top">

Returns the arc-tangent, in radians, of the ratio of two numbers.

</td>
</tr>
<tr>
<td valign="top">

HEX\(<EXPR\>\)

</td>
<td valign="top">

Converts a binary string to an NVARCHAR hexadecimal value.

> ### Note:  
> It corresponds to the function BINTOHEX for a transformation flow created in an SAP HANA space.



</td>
</tr>
<tr>
<td valign="top">

CHAR

</td>
<td valign="top">

Returns the character that has the ASCII value of the specified number.

</td>
</tr>
<tr>
<td valign="top">

UNHEX\(EXPR\)

</td>
<td valign="top">

Converts a string of hexadecimal characters to a VARBINARY value.

> ### Note:  
> It corresponds to the function HEXTOBIN\(<hexadecimal\_string\>\) for a transformation flow created in an SAP HANA space.



</td>
</tr>
<tr>
<td valign="top">

INITCAP

</td>
<td valign="top">

Converts the first character of each word in a specified string to uppercase and converts remaining characters to lowercase.

</td>
</tr>
<tr>
<td valign="top">

LCASE

</td>
<td valign="top">

Converts all characters in a string to lowercase.

</td>
</tr>
<tr>
<td valign="top">

LEFT

</td>
<td valign="top">

Returns the specified number of characters or bytes of a string, starting from the left side.

</td>
</tr>
<tr>
<td valign="top">

LENGTH

</td>
<td valign="top">

Returns the number of characters in a string.

</td>
</tr>
<tr>
<td valign="top">

LOCATE

</td>
<td valign="top">

Returns the position of a substring within a string.

</td>
</tr>
<tr>
<td valign="top">

REGEXPR\_INSTR\(STR,REGEXPR\)

</td>
<td valign="top">

Searches a string for a regular expression pattern and returns an integer indicating the beginning position, or the ending position plus 1, of one occurrence of the matched substring.

> ### Note:  
> It corresponds to the function LOCATE\_REGEXPR for a transformation flow created in an SAP HANA space.



</td>
</tr>
<tr>
<td valign="top">

LOWER

</td>
<td valign="top">

Converts all characters in a string to lowercase.

</td>
</tr>
<tr>
<td valign="top">

LPAD

</td>
<td valign="top">

Left-pads a string with spaces, or a specified pattern, to make a string of a specified number of characters in length.

</td>
</tr>
<tr>
<td valign="top">

LTRIM

</td>
<td valign="top">

Returns a string, trimmed of all leading spaces.

</td>
</tr>
<tr>
<td valign="top">

HEX\(EXPR\)

</td>
<td valign="top">

Converts a numeric value to a hexadecimal value.

> ### Note:  
> It corresponds to the function NUMTOHEX for a transformation flow created in an SAP HANA space.



</td>
</tr>
<tr>
<td valign="top">

REGEXPR\_COUNT\(STR,REGEXPR\)

</td>
<td valign="top">

Returns the number of matches of a regular expression search within a string.

> ### Note:  
> It corresponds to the function OCCURRENCES\_REGEXPR for a transformation flow created in an SAP HANA space.



</td>
</tr>
<tr>
<td valign="top">

REPLACE

</td>
<td valign="top">

Searches within a string for all occurrences of a specified string and replaces them with another specified string.

</td>
</tr>
<tr>
<td valign="top">

REGEXPR\_REPLACE\(STR,REGEXPR,REPLACE,POSITION\)

</td>
<td valign="top">

Searches a string for a regular expression pattern and returns the string with either one or every occurrence of the regular expression pattern that is replaced using a replacement string.

> ### Note:  
> It corresponds to the function REPLACE\_REGEXPR for a transformation flow created in an SAP HANA space.



</td>
</tr>
<tr>
<td valign="top">

RIGHT

</td>
<td valign="top">

Returns the specified number of characters/bytes of a string, starting from the right side.

</td>
</tr>
<tr>
<td valign="top">

RPAD

</td>
<td valign="top">

Right-pads a string with spaces or a specified pattern to make a string that is a specified number of characters in length.

</td>
</tr>
<tr>
<td valign="top">

RTRIM

</td>
<td valign="top">

Returns a string trimmed of all trailing spaces.

</td>
</tr>
<tr>
<td valign="top">

SOUNDEX

</td>
<td valign="top">

Converts alphabet characters into a sound code that represents their sound.

</td>
</tr>
<tr>
<td valign="top">

TO\_BINARY\(STR,FMT\)

</td>
<td valign="top">

Converts all characters in a string into a binary encoding using the specified codepage.

> ### Note:  
> It corresponds to the function STRTOBIN for a transformation flow created in an SAP HANA space.



</td>
</tr>
<tr>
<td valign="top">

TRIM

</td>
<td valign="top">

Returns a string after removing leading and trailing spaces.

</td>
</tr>
<tr>
<td valign="top">

UCASE

</td>
<td valign="top">

Converts all characters in the specified string to uppercase.

</td>
</tr>
<tr>
<td valign="top">

UPPER

</td>
<td valign="top">

Converts all characters in a string to uppercase.

</td>
</tr>
<tr>
<td valign="top">

SUBSTRING

</td>
<td valign="top">

Returns a substring from an input value, starting from a specified position within the input value.

</td>
</tr>
<tr>
<td valign="top">

REGEXPR\_SUBSTR\(STR, REGEXPR\)

</td>
<td valign="top">

Searches a string for a regular expression pattern and returns one occurrence of the matching substring.

> ### Note:  
> It corresponds to the function SUBSTRING\_REGEXPR for a transformation flow created in an SAP HANA space.



</td>
</tr>
</table>



<a name="loio37e737fc0aee4ac7bcee4660d189dc26__section_akw_c12_bdc"/>

## Data Type Conversion Functions


<table>
<tr>
<th valign="top">

Functions

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

CAST

</td>
<td valign="top">

Returns the value of an expression converted to a supplied data type.

</td>
</tr>
<tr>
<td valign="top">

BIGINT\(EXPR\)

</td>
<td valign="top">

Converts a value to a BIGINT data type.

> ### Note:  
> It corresponds to the function TO\_BIGINT for a transformation flow created in an SAP HANA space.



</td>
</tr>
<tr>
<td valign="top">

BINARY\(EXPR\)

</td>
<td valign="top">

> ### Note:  
> It corresponds to the function TO\_BINARY for a transformation flow created in an SAP HANA space.



</td>
</tr>
<tr>
<td valign="top">

BOOLEAN\(EXPR\)

</td>
<td valign="top">

> ### Note:  
> It corresponds to the function TO\_BOOLEAN for a transformation flow created in an SAP HANA space.



</td>
</tr>
<tr>
<td valign="top">

DATE\(EXPR\)

</td>
<td valign="top">

> ### Note:  
> It corresponds to the function TO\_DATE for a transformation flow created in an SAP HANA space.



</td>
</tr>
<tr>
<td valign="top">

DECIMAL\(EXPR\)

</td>
<td valign="top">

> ### Note:  
> It corresponds to the function TO\_DECIMAL for a transformation flow created in an SAP HANA space.



</td>
</tr>
<tr>
<td valign="top">

DOUBLE\(EXPR\)

</td>
<td valign="top">

> ### Note:  
> It corresponds to the function TO\_DOUBLE for a transformation flow created in an SAP HANA space.



</td>
</tr>
<tr>
<td valign="top">

INT\(EXPR\)

</td>
<td valign="top">

> ### Note:  
> It corresponds to the function TO\_INT for a transformation flow created in an SAP HANA space.



</td>
</tr>
<tr>
<td valign="top">

SAMLLINT\(EXPR\)

</td>
<td valign="top">

> ### Note:  
> It corresponds to the function TO\_SAMLLINT for a transformation flow created in an SAP HANA space.



</td>
</tr>
<tr>
<td valign="top">

TINYINT\(EXPR\)

</td>
<td valign="top">

> ### Note:  
> It corresponds to the function TO\_TINYINT for a transformation flow created in an SAP HANA space.



</td>
</tr>
<tr>
<td valign="top">

TIMESTAMP\(EXPR\)

</td>
<td valign="top">

> ### Note:  
> It corresponds to the function TO\_TIMESTAMP for a transformation flow created in an SAP HANA space.



</td>
</tr>
</table>



<a name="loio37e737fc0aee4ac7bcee4660d189dc26__section_jh2_qg2_bdc"/>

## Window Functions


<table>
<tr>
<th valign="top">

Functions

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

CUME\_DIST

</td>
<td valign="top">

Returns the relative rank of a row.

</td>
</tr>
<tr>
<td valign="top">

DENSE\_RANK

</td>
<td valign="top">

Performs the same ranking operation as the RANK function, except that rank numbering does not skip when ties are found.

</td>
</tr>
<tr>
<td valign="top">

LAG

</td>
<td valign="top">

Returns the value of the offset rows before the current row.

</td>
</tr>
<tr>
<td valign="top">

LEAD

</td>
<td valign="top">

Returns the offset of rows after the current row. The <offset\> should be non-negative and its default is 1.

</td>
</tr>
<tr>
<td valign="top">

NTILE

</td>
<td valign="top">

Distributes rows into a specified number of buckets and assigns the bucket number starting from 1 to each row in the bucket.

</td>
</tr>
<tr>
<td valign="top">

PERCENT\_RANK

</td>
<td valign="top">

Calculates the percentage of values that are either less than or greater than the current value, per the ORDER BY specification for the window.

</td>
</tr>
<tr>
<td valign="top">

RANK

</td>
<td valign="top">

Returns rank of a row within a partition, starting from 1.

</td>
</tr>
<tr>
<td valign="top">

ROW\_NUMBER

</td>
<td valign="top">

Sequentially numbers the rows within a partition of a result set, with the first row of each partition assigned as 1.

</td>
</tr>
</table>



<a name="loio37e737fc0aee4ac7bcee4660d189dc26__section_n1w_ch2_bdc"/>

## Array Functions


<table>
<tr>
<th valign="top">

Functions

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

GET\(ARRAY,INDEX\)

</td>
<td valign="top">

Returns values from a specified array position.

> ### Note:  
> It corresponds to the function MEMBER\_AT for a transformation flow created in an SAP HANA space.



</td>
</tr>
<tr>
<td valign="top">

SLICE\(ARRAY,START,LENGHT\)

</td>
<td valign="top">

Returns a subset of values from the specified array beginning from the specified start position.

> ### Note:  
> It corresponds to the function SUBARRAY for a transformation flow created in an SAP HANA space.



</td>
</tr>
</table>

> ### Note:  
> You can't select an unsupported function.

