<!-- loio6a37cc58322548a986496d5e139e9201 -->

# SQL Reference

SAP Datasphere views support a subset of the SQL syntax supported by SAP HANA Cloud.

SAP Datasphere primarily supports the SQL syntax listed in the `SELECT` statement \(see [SELECT Statement \(Data Manipulation\)](https://help.sap.com/viewer/c1d3f60099654ecfb3fe36ac93c121bb/cloud/en-US/20fcf24075191014a89e9dc7b8408b26.html) and related sections of the *SAP HANA Cloud, SAP HANA Database SQL Reference Guide*.

SAP Datasphere supports the following:

-   Operators \(see [SQL Operators](sql-reference-6a37cc5.md#loio6a37cc58322548a986496d5e139e9201__operators)\)
-   Predicates \(see [SQL Predicates](sql-reference-6a37cc5.md#loio6a37cc58322548a986496d5e139e9201__predicates)\)
-   Expressions \(see [Expressions](sql-reference-6a37cc5.md#loio6a37cc58322548a986496d5e139e9201__expressions)\)
-   Functions \(see [SQL Functions Reference](sql-functions-reference-6d624a1.md)\)

> ### Tip:  
> An alternative to using `TOP`, which is not supported in SAP Datasphere is to use `limit`.
> 
> So, instead of using:
> 
> ```
> SELECT TOP 3 "SMALL_INT" FROM "ALLDATASV0" ORDER BY "SMALL_INT" DESC
> ```
> 
> You can use:
> 
> ```
> SELECT  "SMALL_INT" FROM "ALLDATASV0" ORDER BY "SMALL_INT" DESC limit 3
> ```



<a name="loio6a37cc58322548a986496d5e139e9201__operators"/>

## SQL Operators

SAP Datasphere supports the following operators:


<table>
<tr>
<th valign="top">

Operator

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

`+`

</td>
<td valign="top">

Addition

</td>
</tr>
<tr>
<td valign="top">

`-`

</td>
<td valign="top">

Subtraction

</td>
</tr>
<tr>
<td valign="top">

`*`

</td>
<td valign="top">

Multiplication

</td>
</tr>
<tr>
<td valign="top">

`/`

</td>
<td valign="top">

Division

</td>
</tr>
<tr>
<td valign="top">

`AND`

</td>
<td valign="top">

Logical conjunction

</td>
</tr>
<tr>
<td valign="top">

`OR`

</td>
<td valign="top">

Logical disjunction

</td>
</tr>
<tr>
<td valign="top">

`NOT`

</td>
<td valign="top">

Logical negation

</td>
</tr>
<tr>
<td valign="top">

`||`

</td>
<td valign="top">

Concatenation

</td>
</tr>
<tr>
<td valign="top">

`<`

</td>
<td valign="top">

Less than

</td>
</tr>
<tr>
<td valign="top">

`>`

</td>
<td valign="top">

Greater than

</td>
</tr>
<tr>
<td valign="top">

`=`

</td>
<td valign="top">

Equal

</td>
</tr>
<tr>
<td valign="top">

`!=`

</td>
<td valign="top">

Not equal

</td>
</tr>
<tr>
<td valign="top">

`<=`

</td>
<td valign="top">

Less than or equal

</td>
</tr>
<tr>
<td valign="top">

`>=`

</td>
<td valign="top">

Greater than or equal

</td>
</tr>
<tr>
<td valign="top">

`LIKE`

</td>
<td valign="top">

Value similar to

</td>
</tr>
<tr>
<td valign="top">

`IS NULL`

</td>
<td valign="top">

Value does not exist

</td>
</tr>
<tr>
<td valign="top">

`BETWEEN`

</td>
<td valign="top">

Value between two other values

</td>
</tr>
<tr>
<td valign="top">

`()`

</td>
<td valign="top">

Parentheses

</td>
</tr>
</table>

For more information, see [Operators](https://help.sap.com/viewer/c1d3f60099654ecfb3fe36ac93c121bb/latest/en-US/20a380977519101494ceddd944e87527.html) in the *SAP HANA Cloud, SAP HANA Database SQL Reference Guide*.



<a name="loio6a37cc58322548a986496d5e139e9201__predicates"/>

## SQL Predicates

SAP Datasphere supports the following predicates:


<table>
<tr>
<th valign="top">

Predicate

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

`ANY`, `SOME`, `ALL`

</td>
<td valign="top">

Compares values using the specified comparison operator and returns true, false, or unknown.

</td>
</tr>
<tr>
<td valign="top">

`BETWEEN`

</td>
<td valign="top">

Compares a value with a list of values within the specified range and returns true or false.

</td>
</tr>
<tr>
<td valign="top">

`CONTAINS`

</td>
<td valign="top">

Matches a search string with the results of a subquery.

</td>
</tr>
<tr>
<td valign="top">

`EXISTS`

</td>
<td valign="top">

Tests for the presence of a value in a set and returns either true or false.

</td>
</tr>
<tr>
<td valign="top">

`IN`

</td>
<td valign="top">

Searches for a value in a set of values and returns true or false.

</td>
</tr>
<tr>
<td valign="top">

`LIKE`

</td>
<td valign="top">

Performs a comparison to see if a character string matches a specified pattern.

</td>
</tr>
<tr>
<td valign="top">

`MEMBER OF`

</td>
<td valign="top">

Determines whether a value is a member of an array.

</td>
</tr>
<tr>
<td valign="top">

`NULL`

</td>
<td valign="top">

Performs a comparison of the value of an expression with NULL.

</td>
</tr>
</table>

For more information, see [Predicates](https://help.sap.com/docs/hana-cloud-database/sap-hana-cloud-sap-hana-database-sql-reference-guide/predicates) in the *SAP HANA Cloud, SAP HANA Database SQL Reference Guide*.



<a name="loio6a37cc58322548a986496d5e139e9201__expressions"/>

## Expressions

SAP Datasphere supports the `CASE` expression:


<table>
<tr>
<th valign="top">

Expression

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

`CASE WHEN THEN ELSE END`

</td>
<td valign="top">

Provides if, then, else logic.

</td>
</tr>
</table>

For more information, see [Expressions](https://help.sap.com/viewer/c1d3f60099654ecfb3fe36ac93c121bb/cloud/en-US/20a4389775191014b5a6bf2ccc0df2ed.html) in the *SAP HANA Cloud, SAP HANA Database SQL Reference Guide*.

