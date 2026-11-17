<!-- loio3de7a48176b24ff98e88cc88ce0db777 -->

# SQL \(Apache Spark SQL\) Syntax Support in Transformation Flow Operators

Learn about the SQL \(Apache Spark SQL\) syntax elements and features supported by transformation flow operators, including supported statements, clauses, functions, and advanced capabilities.

Transformation flow operators use SQL \(Apache Spark SQL\) to enable powerful data transformations. Understanding the supported syntax elements helps you write effective queries for your data processing workflows. The table below provides a comprehensive overview of all supported SQL \(Apache Spark SQL\) features available in transformation flow operators.

For more information on SQL \(Apache Spark SQL\), see [SQL Reference Guide for Apache Spark](https://spark.apache.org/docs/3.5.6/sql-ref.html).


<table>
<tr>
<th valign="top">

Category

</th>
<th valign="top">

Supported

</th>
<th valign="top">

Details

</th>
</tr>
<tr>
<td valign="top">

Statements

</td>
<td valign="top">

SELECT queries only

</td>
<td valign="top">

Top-level statement must always be a SELECT query \(no DDL/DML\)

</td>
</tr>
<tr>
<td valign="top">

FROM Clause

</td>
<td valign="top">

Tables, views, subqueries, table-valued functions

</td>
<td valign="top">

Fully-qualified names \(catalog.db.table\), aliases

</td>
</tr>
<tr>
<td valign="top">

Joins

</td>
<td valign="top">

INNER, LEFT \[OUTER\], RIGHT \[OUTER\], FULL \[OUTER\], CROSS, LEFT SEMI, LEFT ANTI, NATURAL

</td>
<td valign="top">

Join conditions using ON or USING

</td>
</tr>
<tr>
<td valign="top">

Filtering

</td>
<td valign="top">

WHERE with boolean expressions

</td>
<td valign="top">

=, <, <=, <\>, !=, IN, BETWEEN, LIKE, IS NULL, EXISTS / NOT EXISTS, AND, OR, NOT

</td>
</tr>
<tr>
<td valign="top">

LIKE Predicate

</td>
<td valign="top">

\[NOT\] LIKE pattern \[ESCAPE char\]

</td>
<td valign="top">

% matches any sequence of characters, \_ matches any single character

</td>
</tr>
<tr>
<td valign="top">

Sorting & Pagination

</td>
<td valign="top">

ORDER BY, SORT BY, LIMIT

</td>
<td valign="top">

ASC/DESC, NULLS FIRST/LAST. ORDER BY: global sort. SORT BY: per-partition sort \(Spark-specific\)

</td>
</tr>
<tr>
<td valign="top">

Grouping & Aggregation

</td>
<td valign="top">

GROUP BY, HAVING, GROUPING SETS

</td>
<td valign="top">

Standard aggregate functions \(COUNT, SUM, AVG, MIN, MAX, ...\). SELECT aliases can be used in GROUP BY

</td>
</tr>
<tr>
<td valign="top">

Window Functions

</td>
<td valign="top">

func\(...\) OVER \(...\)

</td>
<td valign="top">

PARTITION BY, ORDER BY, ROWS/RANGE frames. Frame bounds: UNBOUNDED PRECEDING, N PRECEDING, CURRENT ROW, N FOLLOWING, UNBOUNDED FOLLOWING. Named window definitions: WINDOW w AS \(...\) reusable via OVER w

</td>
</tr>
<tr>
<td valign="top">

Expressions

</td>
<td valign="top">

Arithmetic, comparisons, logical, CASE, CAST, scalar subqueries

</td>
<td valign="top">

\+, -, \*, /, %. CASE WHEN ... THEN ... \[ELSE ...\] END. CAST\(expr AS type\) / TRY\_CAST\(expr AS type\). Nested expressions with parentheses

</td>
</tr>
<tr>
<td valign="top">

Identifiers

</td>
<td valign="top">

Unquoted or backtick-quoted

</td>
<td valign="top">

Backticks for reserved words or names with spaces/special characters

</td>
</tr>
<tr>
<td valign="top">

Literals

</td>
<td valign="top">

String, numeric, boolean, NULL, date, timestamp, interval

</td>
<td valign="top">

'string' \(single-quoted\), 42 \(INT\), 42L \(BIGINT\), 3.14 \(DECIMAL\), TRUE/FALSE, NULL, DATE '2024-01-31', TIMESTAMP '2024-01-31 10:00:00', INTERVAL 5 DAY, INTERVAL 1 YEAR 2 MONTHS

</td>
</tr>
<tr>
<td valign="top">

Set Operators

</td>
<td valign="top">

UNION, INTERSECT, EXCEPT, MINUS

</td>
<td valign="top">

Set operators combine two input relations into a single one. \[ALL\] preserves duplicates; without it, duplicates are removed. MINUS is a Spark alias for EXCEPT

</td>
</tr>
<tr>
<td valign="top">

Inline Table

</td>
<td valign="top">

VALUES

</td>
<td valign="top">

Inline table is a temporary table created using a VALUES clause. Example: VALUES \(v1, v2\), \(v3, v4\) AS alias \(col1, col2\)

</td>
</tr>
<tr>
<td valign="top">

Advanced

</td>
<td valign="top">

PIVOT, UNPIVOT, subqueries in FROM or WHERE

</td>
<td valign="top">

PIVOT: aggregate values based on specific column values. UNPIVOT: transform columns into rows \(reverse of PIVOT\). Subqueries as derived tables in FROM or as IN/EXISTS/scalar expressions

</td>
</tr>
<tr>
<td valign="top">

Hints

</td>
<td valign="top">

Partition hints, join type hints

</td>
<td valign="top">

Syntax: /\*+ hint \*/. Partition: COALESCE\(n\), REPARTITION\(n, col\), REBALANCE\(col\). Join type: BROADCAST\(t\), MERGE\(t\), SHUFFLE\_REPLICATE\_NL\(t\)

</td>
</tr>
</table>

