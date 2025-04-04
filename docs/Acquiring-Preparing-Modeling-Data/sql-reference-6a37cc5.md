<!-- loio6a37cc58322548a986496d5e139e9201 -->

# SQL Reference

SAP Datasphere views support a subset of the SQL syntax supported by SAP HANA Cloud.

This topic contains the following sections::

-   [The SAP HANA "SELECT" Statement](sql-reference-6a37cc5.md#loio6a37cc58322548a986496d5e139e9201__select)
-   [SQL Operators](sql-reference-6a37cc5.md#loio6a37cc58322548a986496d5e139e9201__operators)
-   [SQL Predicates](sql-reference-6a37cc5.md#loio6a37cc58322548a986496d5e139e9201__predicates)
-   [Expressions](sql-reference-6a37cc5.md#loio6a37cc58322548a986496d5e139e9201__expressions)

See also [SQL Functions Reference](sql-functions-reference-6d624a1.md).



<a name="loio6a37cc58322548a986496d5e139e9201__select"/>

## The SAP HANA "SELECT" Statement

SAP Datasphere primarily supports the SQL syntax listed in the `SELECT` statement.

In this example, a view is created in which:

-   Various columns are selected from the `Sales` and `Products` entities and given aliases via the `AS` keyword.
-   A new, calculated column, `Unit_Price` is created using the `ROUND()` function.
-   The `FROM` clause defines an `INNER JOIN` between the entities on their `Product_ID` columns.
-   The `WHERE` clause filters the results by the `Product_Line`, which must be `Electronics`.
-   The `ORDER BY` clause orders the results by the value of `Gross_Sales` in descending order.

```
SELECT
  "Sales"."Date" AS "Date",
  "Products"."Product_ID" AS "Product_ID",
  "Products"."Line" AS "Product_Line",
  "Products"."Category" AS "Product_Category",
  "Products"."Product" AS "Product",
  ROUND("Sales"."Gross_Sales" / "Sales"."Quantity", 2) AS "Unit_Price",
  "Sales"."Gross_Sales" AS "Gross_Sales"
FROM ("Sales" INNER JOIN "Products" ON "Sales"."Product_ID" = "Products"."Product_ID")
WHERE "Products"."Product_Line" = "Electronics"
ORDER BY "Gross_Sales" DESC
```

> ### Note:  
> -   If you define an alias in your `SELECT` statement, then you must use the alias \(rather than the source name\) consistently in all clauses in the statement.
> -   The `TOP` keyword is not supported in SAP Datasphere, but you can use the `LIMIT` keyword instead, at the end of your `ORDER BY` clause:
> 
>     ```
>     ORDER BY "Gross_Sales" DESC LIMIT 5
>     ```

For full documentation, see [SELECT Statement \(Data Manipulation\)](https://help.sap.com/viewer/c1d3f60099654ecfb3fe36ac93c121bb/cloud/en-US/20fcf24075191014a89e9dc7b8408b26.html) and related sections of the *SAP HANA Cloud, SAP HANA Database SQL Reference Guide*.



<a name="loio6a37cc58322548a986496d5e139e9201__section_cbg_kdc_r2c"/>

## SAP Datasphere Spaces and Schemas

Each SAP Datasphere space has its own schema, where the name of the schema is the *Space ID*.

To provide the name of an object with its schema, use the syntax <code><i class="varname">&lt;schema_name&gt;</i>.<i class="varname">&lt;object_name&gt;</i></code>. For example, to reference the `MySales` view in the `SALES` space, you should enter:

```
SALES.MySales
```

> ### Note:  
> When referencing objects shared to your space, the schema is the *Space ID* for the source space from which the object was shared.



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

