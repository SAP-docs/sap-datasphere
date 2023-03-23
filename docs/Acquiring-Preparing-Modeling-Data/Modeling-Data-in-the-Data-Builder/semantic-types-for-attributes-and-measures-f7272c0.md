<!-- loiof7272c0e8be34ce782d04304580c0243 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Semantic Types for Attributes and Measures

Specify semantic types to identify the type of data in your columns \(attributes and measures\) in analytical datasets, dimensions, and text entities. Semantic types are used by the core engines for data processing, analytics, and data consumption.

Semantic types identify that a column contains a value, a quantity, a date, geo or textual information, or another kind of semantic information.

> ### Note:  
> In order to add semantic types, you must:
> 
> -   Set the *Semantic Usage* of your view or table to *Analytical Dataset*, *Dimension* or *Text*.

You can then select a semantic type for a column \(attribute or measure\) by clicking <span class="FPA-icons"></span> \(Menu\)** \> *Semantic Type* \> **<Type\>**.

> ### Note:  
> SAP Datasphere does not currently support time-dependent dimensions, where dimension members vary over time. You can select the *Business Date - At*, *Business Date - From*, and *Business Date - To* semantic types for information purposes, but the values in these columns are not used to calculate the inclusion or exclusion of a record when generating visualizations in SAP Analytics Cloud.


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

The field indicates that the column contains the key dates and not intervals.



</td>
</tr>
<tr>
<td valign="top">

Business Date - From



</td>
<td valign="top">

The field is the date timestamp or interval that defines the validity of the data of the database table record from a business point of view.

Technical validity: The `from date` is different from the point in time when the record was created. The dates are not to be confused with dates contained in the data part.



</td>
</tr>
<tr>
<td valign="top">

Business Date - To



</td>
<td valign="top">

The field is the date timestamp or interval that defines the validity of the data of the database table record from a business point of view.

Technical validity: The `from date` is different from the point in time when the record was created. The dates are not to be confused with dates contained in the data part.



</td>
</tr>
<tr>
<td valign="top">

Calendar - Day of Month



</td>
<td valign="top">

The value of the field is a day number relative to a calendar month.

> ### Example:  
> 1 - 31

.



</td>
</tr>
<tr>
<td valign="top">

Calendar - Day of Year



</td>
<td valign="top">

The value of the field is a day number relative to a calendar year.

> ### Example:  
> 1 - 366



</td>
</tr>
<tr>
<td valign="top">

Calendar - Halfyear



</td>
<td valign="top">

 



</td>
</tr>
<tr>
<td valign="top">

Calendar - Month



</td>
<td valign="top">

The value of the field encodes a calendar month number as a string following the logical pattern `MM` consisting of two digits.

> ### Example:  
> The string matches the regex pattern `0[1-9]|1[0-2]`



</td>
</tr>
<tr>
<td valign="top">

Calendar - Quarter



</td>
<td valign="top">

The value of the field encodes a calendar quarter number as a string following the logical pattern `Q` consisting of a single digit.

> ### Example:  
> The string matches the regex pattern `[1-4]`



</td>
</tr>
<tr>
<td valign="top">

Calendar - Week



</td>
<td valign="top">

The value of the field encodes a calendar week number as a string following the logical pattern `WW` consisting of two digits.

> ### Example:  
> The string matches the regex pattern `0[1-9]|[1-4][0-9]|5[2-3]`



</td>
</tr>
<tr>
<td valign="top">

Calendar - Year



</td>
<td valign="top">

The value of the field encodes a year number as a string following the logical pattern `(-?)YYYY(Y*)` consisting of an optional minus sign for years B.C., followed by at least four digits.

> ### Example:  
> The string matches the regex pattern `-?([1-9][0-9]{3,}|0[0-9]{3})`



</td>
</tr>
<tr>
<td valign="top">

Calendar - Year Halfyear



</td>
<td valign="top">

 



</td>
</tr>
<tr>
<td valign="top">

Calendar - Year Month



</td>
<td valign="top">

The value of the field encodes a calendar year and month as a string following the logical pattern `(-?)YYYY(Y*)MM` consisting of an optional minus sign for years B.C., followed by at least six digits, where the last two digits represent the months January to December.

> ### Example:  
> The string matches the regex pattern `-?([1-9][0-9]{3,}|0[0-9]{3})(0[1-9]|1[0-2])`



</td>
</tr>
<tr>
<td valign="top">

Calendar - Year Quarter



</td>
<td valign="top">

The value of the field encodes a calendar year and quarter as a string following the logical pattern `(-?)YYYY(Y*)Q` consisting of an optional minus sign for years B.C., followed by at least five digits, where the last digit represents the quarter.

> ### Example:  
> The string matches the regex pattern `-?([1-9][0-9]{3,}|0[0-9]{3})[1-4]`



</td>
</tr>
<tr>
<td valign="top">

Calendar - Year Week



</td>
<td valign="top">

The value of the field encodes a calendar year and week as a string following the logical pattern `(-?)YYYY(Y*)WW` consisting of an optional minus sign for years B.C., followed by at least six digits, where the last two digits represent week number in the year.

> ### Example:  
> The string matches the regex pattern `-?([1-9][0-9]{3,}|0[0-9]{3})(0[1-9]|[1-4][0-9]|5[2-3])`



</td>
</tr>
<tr>
<td valign="top">

Currency code



</td>
<td valign="top">

This type tags a field containing a currency code

This can be either an [ISO code](http://www.currency-iso.org/dl_iso_table_a1.xml) or an SAP currency code \(data type `CUKY`\).

**Scope:** \[ELEMENT\]

**Evaluation Runtime \(Engine\):** Interpreted by **ABAP** Runtime Environment



</td>
</tr>
<tr>
<td valign="top">

Fiscal - Period



</td>
<td valign="top">

A fiscal period is covered by financial reports, for example, an annual report covers a fiscal period of one year, but a quarterly report includes accounting data for three months.

The value of the field encodes a fiscal period as a string following the logical pattern `PPP` consisting of three digits. This fiscal period usually is a quarter of a year.

> ### Example:  
> The string matches the regex pattern \[0-9\]\{3\}



</td>
</tr>
<tr>
<td valign="top">

Fiscal - Year



</td>
<td valign="top">

The value of the field encodes a fiscal year number as a string following the logical pattern `YYYY` consisting of four digits.

> ### Example:  
> The string matches the regex pattern \[1-9\]\[0-9\]\{3\}



</td>
</tr>
<tr>
<td valign="top">

Fiscal - Year Period



</td>
<td valign="top">

The value of the field encodes a fiscal year and period as a string following the logical pattern `YYYYPPP` consisting of seven digits. The last three digits represent the fiscal period in the year.

> ### Example:  
> The string matches the regex pattern \(\[1-9\]\[0-9\]\{3\}\)\(\[0-9\]\{3\}\)



</td>
</tr>
<tr>
<td valign="top">

Fiscal - Year Variant



</td>
<td valign="top">

The value of the field encodes a fiscal year variant, which describes the number of periods in a fiscal year and how they match the calendar year.



</td>
</tr>
<tr>
<td valign="top">

Geolocation - Cartoid



</td>
<td valign="top">

> ### Note:  
> Stories don't support geographical information from semantic labels.



</td>
</tr>
<tr>
<td valign="top">

Geolocation - Latitude



</td>
<td valign="top">

The value of the field specifies the latitude of the location such as a city.

> ### Note:  
> Stories don't support geographical information from semantic labels.



</td>
</tr>
<tr>
<td valign="top">

Geolocation - Longitude



</td>
<td valign="top">

The value of the field specifies the longitude of the location such as a city.

> ### Note:  
> Stories don't support geographical information from semantic labels.



</td>
</tr>
<tr>
<td valign="top">

Geolocation - Normalized Name



</td>
<td valign="top">

The value of the field contains the readable name of the location.

> ### Note:  
> Stories don't support geographical information from semantic labels.



</td>
</tr>
<tr>
<td valign="top">

Language



</td>
<td valign="top">

This type identifies a language.

**Scope:** \[ELEMENT, PARAMETER\]

**Evaluation Runtime \(Engine\):** **SADL**: Translates CDS types into the corresponding OData types



</td>
</tr>
<tr>
<td valign="top">

System Date - Created at



</td>
<td valign="top">

Timestamps when database record was created.



</td>
</tr>
<tr>
<td valign="top">

System Date - Last changed at



</td>
<td valign="top">

Timestamp when database record was last changed.



</td>
</tr>
<tr>
<td valign="top">

Text



</td>
<td valign="top">

This type identifies a human-readable text that is not necessarily language-dependent.

**Scope:** \[ELEMENT, PARAMETER\]

**Evaluation Runtime \(Engine\):** **SADL**: Translates CDS types into the corresponding OData types



</td>
</tr>
<tr>
<td valign="top">

Unit of measure



</td>
<td valign="top">

This type tags a field as containing a unit of measure.

> ### Note:  
> There seems to be currently no internationally recognized standard list for units of measure available.

**Scope:** \[ELEMENT, PARAMETER\]

**Evaluation Runtime \(Engine\):** 



</td>
</tr>
</table>

