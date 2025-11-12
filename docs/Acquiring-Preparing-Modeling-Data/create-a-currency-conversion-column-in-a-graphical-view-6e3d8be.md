<!-- loio6e3d8bed7ece4c27ba10e2cc523915fe -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Create a Currency Conversion Column in a Graphical View

Convert values from one currency to another or harmonize values given in various currencies with a *Currency Conversion Column*, which uses the SAP `TCUR*` to perform the calculations.



<a name="loio6e3d8bed7ece4c27ba10e2cc523915fe__prereq_v3g_2kl_bhc"/>

## Prerequisites

To create a view with a currency conversion column, you must ensure that all of the required SAP `TCUR*` tables are present in \(or shared to\) your space, supplied with appropriate data, and encapsulated in views that have the *Expose For Consumption* switch enabled.

You can use the *Currency Conversion Views* dialog to provide these objects in your space for any of the following situations:

-   *<Connection\>* - Generate currency conversion tables and views in your space and bring data in from SAP S/4 HANA Cloud, SAP S/4 HANA On-Premise, or SAP ABAP connections.
-   *<Space Name\>* - Use currency conversion tables shared to your space and generate views to encapsulate them.
-   *Manual* - Generate currency conversion tables and views in your space and then manually maintain currency conversion data in them.

For more information, see [Enabling Currency Conversion with TCUR\* Tables and Views](Modeling-Data-in-the-Data-Builder/enabling-currency-conversion-with-tcur-tables-and-views-b462239.md)\).

> ### Note:  
> When sharing a view containing a currency conversion column to another space, you must share all of the entities referred to in the *Advanced Properties* section of the side panel \(generally the `SAP.CURRENCY.VIEW.*` views\) to the target space as well.

The full set of tables and views required is as follows:


<table>
<tr>
<th valign="top">

Table

</th>
<th valign="top">

View

</th>
</tr>
<tr>
<td valign="top">

Currency Codes / `SAP.CURRENCY.TABLE.TCURC`

</td>
<td valign="top">

Currency Codes View / `SAP.CURRENCY.VIEW.TCURC`

</td>
</tr>
<tr>
<td valign="top">

Conversion Factors / `SAP.CURRENCY.TABLE.TCURF`

</td>
<td valign="top">

Conversion Factors View / `SAP.CURRENCY.VIEW.TCURF`

</td>
</tr>
<tr>
<td valign="top">

Quotations / `SAP.CURRENCY.TABLE.TCURN`

</td>
<td valign="top">

Quotations View / `SAP.CURRENCY.VIEW.TCURN`

</td>
</tr>
<tr>
<td valign="top">

Exchange Rates / `SAP.CURRENCY.TABLE.TCURR`

</td>
<td valign="top">

Exchange Rates View / `SAP.CURRENCY.VIEW.TCURR`

</td>
</tr>
<tr>
<td valign="top">

Currency Text / `SAP.CURRENCY.TABLE.TCURT`

</td>
<td valign="top">

Currency Text View / `SAP.CURRENCY.VIEW.TCURT`

</td>
</tr>
<tr>
<td valign="top">

Exchange Rate Types / `SAP.CURRENCY.TABLE.TCURV`

</td>
<td valign="top">

Exchange Rate Types View / `SAP.CURRENCY.VIEW.TCURV`

</td>
</tr>
<tr>
<td valign="top">

Exchange Rate Type Text / `SAP.CURRENCY.TABLE.TCURW`

</td>
<td valign="top">

Exchange Rate Type Text View / `SAP.CURRENCY.VIEW.TCURW`

</td>
</tr>
<tr>
<td valign="top">

Decimal Places in Currencies / `SAP.CURRENCY.TABLE.TCURX`

</td>
<td valign="top">

Decimal Places in Currencies View / `SAP.CURRENCY.VIEW.TCURX`

</td>
</tr>
</table>

> ### Note:  
> You can use these same entities with a `CONVERT_CURRENCY` function in a standard calculated column or in an SQL view \(see [CONVERT\_CURRENCY](https://help.sap.com/viewer/7c78579ce9b14a669c1f3295b0d8ca16/Cloud/en-US/d22d746ed2951014bb7fb0114ffdaf96.html) in the *SAP HANA* documentation\).



<a name="loio6e3d8bed7ece4c27ba10e2cc523915fe__steps_xtp_xjr_2rb"/>

## Procedure

1.  In a *Calculated Columns* node, click <span class="FPA-icons-V3"></span> \(Add New Calculated Column\) \> <span class="SAP-icons-V5"></span> \(Currency Conversion Column\) to create a new *Currency Conversion* column.

    The new column properties are displayed in the side panel.

2.  Enter a *Business Name* and a *Technical Name* for the column, and specify an appropriate numerical *Data Type*.

3.  Use the *Currency Properties*section to set the properties of your source and target currencies.


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
    
    Source Amount Column
    
    </td>
    <td valign="top">
    
    Select the column identifier containing the values to be converted.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Steps
    
    </td>
    <td valign="top">
    
    Define the steps that should be included in the conversion process:

    -   *Shift* - enables a decimal shift according to the source currency selected.
    -   *Convert* - triggers the actual conversion from the source to the target currency.
    -   *Round* - rounds the converted value to the number of digits of the target currency. Use this step carefully if subsequent aggregations take place on the number, as rounding errors could accumulate.
    -   *Shift Back* - while shift changes the decimals from two to the configured precision of the source currency, *Shift Back* changes them back to two, but from the target currency. If error handling is set to keep unconverted the output currency might be the source instead of the target currency. In case of an error, the rounding and the *Shift Back* are done with respect to the source currency and the conversion is dropped. This renders all steps redundant, and yields the input value again.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Source Currency
    
    </td>
    <td valign="top">
    
    Select the column describing the input unit. Click <span class="SAP-icons-V5"></span> and choose a type:

    -   *Column* - Select a column and click *Select*.

    -   *Fixed Value* - Select a fixed value and click *Select*. A fixed value is a constant of the type string.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Target Currency
    
    </td>
    <td valign="top">
    
    Select the column describing the target unit. Click <span class="SAP-icons-V5"></span> and choose a type:

    -   *Column* - Select a column and click *Select*.

    -   *Fixed Value* - Select a fixed value and click *Select*. A fixed value is a constant of the type string.
    -   *Input Parameter* - Select an Input Parameter and click *Select*. You can also directly enter the technical name in the currency conversion column's properties panel.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Reference Date
    
    </td>
    <td valign="top">
    
    Enter the column describing the currency reference date. Click <span class="SAP-icons-V5"></span> and choose a type:

    -   *Column* - Select a column and click *Select*.

    -   *Fixed Date* - Select a date on the calendar or enter it in the format YEAR-MONTH-DAY. For example, for the 1st of December 2021, enter 2021-12-01.
    -   *Input Parameter* - Select an Input Parameter and click *Select*. You can also directly enter the technical name in the currency conversion column's properties panel.
    -   *Expression* - Enter a SQL expression into the *Expression* field. Browse, select a category, or filter available *Date & Time Functions* \(see [SQL Functions Reference](sql-functions-reference-6d624a1.md)\).


    
    </td>
    </tr>
    </table>
    
4.  Use the *Conversion Properties* section to refer to table columns for the conversion.


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
    
    Client
    
    </td>
    <td valign="top">
    
    Enter a three character string that is used to separate tenants within ERP system tables.

    This parameter should normally be set to `000`.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Conversion Type
    
    </td>
    <td valign="top">
    
    Define the conversion type as stored in the conversion tables. The conversion types available in your system vary according to the setup of your ERP system. In general, these are either M or EURX. Contact your system administrator for the details of your specific table configuration.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Error Handling
    
    </td>
    <td valign="top">
    
    Select a value to define how the system handles a situation where a row could not be converted. All mandatory values must be provided beforehand:

    -   **Fail on Error** - the conversion fails with an error.
    -   **Set to Null** - the output from the row that caused the error is set to NULL.
    -   **Keep Unconverted** - the input value is returned.


    
    </td>
    </tr>
    </table>
    
5.  Use the *Advanced Properties* section to define constant parameter values used in the conversion.


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
    
    Lookup
    
    </td>
    <td valign="top">
    
    Define the type of lookup to be performed:

    -   **Regular** - a regular conversion is performed.
    -   **Reverse** - performs a conversion with the input units swapped.



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Accuracy
    
    </td>
    <td valign="top">
    
    Defines the rounding behavior of the system:

    -   **Compatibility** - mimics ERP behavior by rounding the result.

    -   **Highest** - keeps as many digits as possible in the result.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Date Format
    
    </td>
    <td valign="top">
    
    Defines the format in which the reference date is presented:

    -   **Auto Detect** - attempt automatic detection of the date format.

    -   **Normal** - date is provided in a regular format.
    -   **Inverted** - date is provided in inverted SAP legacy format.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Precision Entity
    
    </td>
    <td valign="top">
    
    Select the entity to provide decimal precisions.

    Default: `SAP.CURRENCY.VIEW.TCURX`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Configuration Entity
    
    </td>
    <td valign="top">
    
    Select the entity to provide conversion type configuration.

    Default: `SAP.CURRENCY.VIEW.TCURV`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Prefactors Entity
    
    </td>
    <td valign="top">
    
    Select the entity to provide conversion factors.

    Default: `SAP.CURRENCY.VIEW.TCURF`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Rates Entity
    
    </td>
    <td valign="top">
    
    Select the entity to provide conversion rates entity.

    Default: `SAP.CURRENCY.VIEW.TCURR`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Notations Entity
    
    </td>
    <td valign="top">
    
    Select the entity to provide notations.

    Default: `SAP.CURRENCY.VIEW.TCURN`
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Currency Code Entity
    
    </td>
    <td valign="top">
    
    Select the entity to provide currency codes.

    Default: `SAP.CURRENCY.VIEW.TCURC`
    
    </td>
    </tr>
    </table>
    
6.  Click *Validate* once all properties are set to check if they are correct, and fix any error signaled. When you are satisfied, open or refresh the *Data Preview* panel to review the results of your currency conversion in your new column.


