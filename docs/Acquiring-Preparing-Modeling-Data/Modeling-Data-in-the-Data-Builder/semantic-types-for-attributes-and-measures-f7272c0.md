<!-- loiof7272c0e8be34ce782d04304580c0243 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Semantic Types for Attributes and Measures

Specify semantic types to identify the type of data in your columns \(attributes and measures\). Semantic types include values, quantities, dates, and geo and textual information.

Semantic types are only available for measures and attributes in entities with a *Semantic Usage* of *Fact*, *Dimension* or *Text*.

To specify a semantic type, hover over the attribute or measure, and click <span class="FPA-icons"></span> \(Menu\)** \> *Semantic Type* \> **<Type\>**.


<table>
<tr>
<th valign="top">

Name



</th>
<th valign="top">

Description



</th>
</tr>
<tr>
<td valign="top">

Business Date - At



</td>
<td valign="top">

A key date.

> ### Note:  
> For information about SAP Datasphere support for time-dependent dimensions using *Business Date - At*, *Business Date - From*, and *Business Date - To* semantic types, see [Enable Time-Dependency for a Dimension or Text Entity](enable-time-dependency-for-a-dimension-or-text-entity-11b2ff4.md).



</td>
</tr>
<tr>
<td valign="top">

Business Date - From



</td>
<td valign="top">

A date timestamp or interval that defines the validity of the data of the database table record from a business point of view. Use *System Date - Created at* to represent the date when the record was created.



</td>
</tr>
<tr>
<td valign="top">

Business Date - To



</td>
<td valign="top">

A date timestamp or interval that defines the validity of the data of the database table record from a business point of view.



</td>
</tr>
<tr>
<td valign="top">

Calendar - Day of Month



</td>
<td valign="top">

A day number relative to a calendar month.

The number must be in the range `1 - 31`.



</td>
</tr>
<tr>
<td valign="top">

Calendar - Day of Year



</td>
<td valign="top">

A day number relative to a calendar year.

The number must be in the range `1 - 366`.



</td>
</tr>
<tr>
<td valign="top">

Calendar - Halfyear



</td>
<td valign="top">

A calendar halfyear number as a string following the logical pattern H consisting of a single digit.

The string must match the regex pattern `[1-2]`.



</td>
</tr>
<tr>
<td valign="top">

Calendar - Month



</td>
<td valign="top">

A calendar month number as a string following the logical pattern `MM` consisting of two digits.

The string must match the regex pattern `0[1-9]|1[0-2]`.



</td>
</tr>
<tr>
<td valign="top">

Calendar - Quarter



</td>
<td valign="top">

A calendar quarter number as a string following the logical pattern `Q` consisting of a single digit.

The string must match the regex pattern `[1-4]`.



</td>
</tr>
<tr>
<td valign="top">

Calendar - Week



</td>
<td valign="top">

A calendar week number as a string following the logical pattern `WW` consisting of two digits.

The string must match the regex pattern `0[1-9]|[1-4][0-9]|5[2-3]`.



</td>
</tr>
<tr>
<td valign="top">

Calendar - Year



</td>
<td valign="top">

A year number as a string following the logical pattern `(-?)YYYY(Y*)` consisting of an optional minus sign for years B.C., followed by at least four digits.

The string must match the regex pattern `-?([1-9][0-9]{3,}|0[0-9]{3})`.



</td>
</tr>
<tr>
<td valign="top">

Calendar - Year Halfyear



</td>
<td valign="top">

A calendar halfyear number as a string following the logical pattern `(-?)YYYY(Y*)H` consisting of an optional minus sign for years B.C., followed by at least five digits, where the last digit represents the halfyear.

The string must match the regex pattern `-?([1-9][0-9]{3,}|0[0-9]{3})[1-2]`.



</td>
</tr>
<tr>
<td valign="top">

Calendar - Year Month



</td>
<td valign="top">

A calendar year and month as a string following the logical pattern `(-?)YYYY(Y*)MM` consisting of an optional minus sign for years B.C., followed by at least six digits, where the last two digits represent the months January to December.

The string must match the regex pattern `-?([1-9][0-9]{3,}|0[0-9]{3})(0[1-9]|1[0-2])`.



</td>
</tr>
<tr>
<td valign="top">

Calendar - Year Quarter



</td>
<td valign="top">

A calendar year and quarter as a string following the logical pattern `(-?)YYYY(Y*)Q` consisting of an optional minus sign for years B.C., followed by at least five digits, where the last digit represents the quarter.

The string must match the regex pattern `-?([1-9][0-9]{3,}|0[0-9]{3})[1-4]`.



</td>
</tr>
<tr>
<td valign="top">

Calendar - Year Week



</td>
<td valign="top">

A calendar year and week as a string following the logical pattern `(-?)YYYY(Y*)WW` consisting of an optional minus sign for years B.C., followed by at least six digits, where the last two digits represent week number in the year.

The string must match the regex pattern `-?([1-9][0-9]{3,}|0[0-9]{3})(0[1-9]|[1-4][0-9]|5[2-3])`.



</td>
</tr>
<tr>
<td valign="top">

Currency code



</td>
<td valign="top">

A currency code.

This can be either an [ISO code](http://www.currency-iso.org/dl_iso_table_a1.xml) or an SAP currency code \(data type `CUKY`\).



</td>
</tr>
<tr>
<td valign="top">

Fiscal - Period



</td>
<td valign="top">

A fiscal period as a string following the logical pattern `PPP` consisting of three digits. This fiscal period usually is a quarter of a year.

A fiscal period is covered by financial reports, for example, an annual report covers a fiscal period of one year, but a quarterly report includes accounting data for three months.

The string must match the regex pattern `[0-9]{3}`.



</td>
</tr>
<tr>
<td valign="top">

Fiscal - Year



</td>
<td valign="top">

A fiscal year number as a string following the logical pattern `YYYY` consisting of four digits.

The string must match the regex pattern `[1-9][0-9]{3}`.



</td>
</tr>
<tr>
<td valign="top">

Fiscal - Year Period



</td>
<td valign="top">

A fiscal year and period as a string following the logical pattern `YYYYPPP` consisting of seven digits. The last three digits represent the fiscal period in the year.

The string must match the regex pattern `([1-9][0-9]{3})([0-9]{3})`.



</td>
</tr>
<tr>
<td valign="top">

Fiscal - Year Variant



</td>
<td valign="top">

A fiscal year variant, which describes the number of periods in a fiscal year and how they match the calendar year.



</td>
</tr>
<tr>
<td valign="top">

Geolocation - Cartoid



</td>
<td valign="top">

A geographical point.

> ### Note:  
> Not supported in SAP Analytics Cloud.



</td>
</tr>
<tr>
<td valign="top">

Geolocation - Latitude



</td>
<td valign="top">

A latitude value for a city or other geographical point.



</td>
</tr>
<tr>
<td valign="top">

Geolocation - Longitude



</td>
<td valign="top">

A longitude value for a city or other geographical point.



</td>
</tr>
<tr>
<td valign="top">

Geolocation - Normalized Name



</td>
<td valign="top">

A readable name for a city or other geographical point.

> ### Note:  
> Not supported in SAP Analytics Cloud.



</td>
</tr>
<tr>
<td valign="top">

Image URL



</td>
<td valign="top">

A URL pointing to an image file. The image will be displayed when the attribute is shown in an SAP Analytics Cloud table.



</td>
</tr>
<tr>
<td valign="top">

Language



</td>
<td valign="top">

A language code.



</td>
</tr>
<tr>
<td valign="top">

System Date - Created at



</td>
<td valign="top">

A timestamp for when the database record was created.



</td>
</tr>
<tr>
<td valign="top">

System Date - Last changed at



</td>
<td valign="top">

A timestamp for when the database record was last changed.



</td>
</tr>
<tr>
<td valign="top">

Text



</td>
<td valign="top">

A human-readable text that is not necessarily language-dependent.



</td>
</tr>
<tr>
<td valign="top">

Unit of measure



</td>
<td valign="top">

A unit of measure.



</td>
</tr>
</table>

