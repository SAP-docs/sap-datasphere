<!-- loio32654ada324643b6a39690f673b92459 -->

# Column Properties and Profiling

To review the properties of a column and obtain profiling information for the data it contains, hover over a column in the list in the *Details* side panel, and click the *Details* icon.


<table>
<tr>
<th valign="top">

Property

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Column Details

</td>
<td valign="top">

Displays the name of the column that will be created. You can modify this name.

</td>
</tr>
<tr>
<td valign="top">

Data Type

</td>
<td valign="top">

Displays the data type of the column that will be created. The following data types are available:

-   Boolean
-   Integer
-   Number - Converted into `Decimal(38,19)` after import.
-   String - Converted into `String(5000)` after import.
-   Date
-   Time
-   Date and Time

> ### Note:  
> More advanced SAP HANA data types such as `ST_POINT` \(see [Column Data Types](column-data-types-7b1dc6e.md)\) are not supported here, but you can derive columns such as these in a view builder.

You can select a different data type from the list and validate the choice by clicking the *Validation* button. Invalid values are marked in red and will be imported as `NULL`.

</td>
</tr>
<tr>
<td valign="top">

Conversion Format

</td>
<td valign="top">

Displays the syntax for `Date`, `Time`, and `Date and Time` data:

-   `Date` data must include, as a minimum, a year in `YY` or `YYYY` format.
-   `Time` data must include, as a minimum, hours in `HH12`, `HH24` format. Click the *i* button for detailed format information.
-   `Date and Time` data must include, as a minimum, a date and hours in `YYYY-MM-DDTHH12` or `YYYY-MM-DDTHH24` format. Click the *i* button for detailed format information.



</td>
</tr>
<tr>
<td valign="top">

Set as Key

</td>
<td valign="top">

Select the checkbox to specify that the column acts as a primary key. Each row in a key column should contain a unique value.

</td>
</tr>
<tr>
<td valign="top">

Data Distribution

</td>
<td valign="top">

Displays profiling information for the data in the column textually and as a bar chart:

-   *Rows* / *Sampled Rows* - Displays the number of rows found in the file.
-   *Unique Values* - \[string columns\] - Displays the number of unique values found in the column, with each value having a bar in the chart sorted with the most common value at the top.

    Click a bar to select each row with that value in the data preview on the left.

-   *Number of Bars* - \[numeric columns\] Displays the number of ranges into which the values are divided, with each range having a bar in the chart. You can use the slider to control the number of bars displayed.

    Click a bar to display further statistical information below the chart and to select each row with that value in the data preview on the left.




</td>
</tr>
<tr>
<td valign="top">

Validation

</td>
<td valign="top">

Displays any issues detected in the data in the column.

</td>
</tr>
</table>

