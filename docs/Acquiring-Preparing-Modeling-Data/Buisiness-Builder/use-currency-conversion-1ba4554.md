<!-- loio1ba4554f0aaf40f7b5c0e430eb2da510 -->

# Use Currency Conversion

You can convert currency values into another currency.



<a name="loio1ba4554f0aaf40f7b5c0e430eb2da510__prereq_rvn_gc4_3tb"/>

## Prerequisites

To enable currency conversion, you create the necessary objects in your space. For more information, see [Enabling Currency Conversion with TCUR\* Tables and Views](../Creating-Finding-Sharing-Objects/enabling-currency-conversion-with-tcur-tables-and-views-b462239.md).



## Context

Currency conversion on calculated measures enables you to have a common currency for reporting, e.g. company code or cost area currency.

You can use currency conversion for measures in a business entity or a consumtion model.



## Procedure

1.  Go to the *Measures* tab. Define your measure.

2.  Set the properties for your source in the *Source* section.


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
    
    Measure Type
    
    </td>
    <td valign="top">
    
    Choose *Converted Currency*.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Source Measure
    
    </td>
    <td valign="top">
    
    Select the *Source Measure*. It has to have the type *Amount with Currency*.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Client ID
    
    </td>
    <td valign="top">
    
    Enter a three character string that is used to separate tenants within ERP system tables. This is used in the conversion tables to select the correct rows for each user.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Target Currency
    
    </td>
    <td valign="top">
    
    Select your target currency.
    
    </td>
    </tr>
    </table>
    
3.  Set the properties in the *Reference Date* section.


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
    
    Current Date
    
    </td>
    <td valign="top">
    
    The current date is used.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Constant Value
    
    </td>
    <td valign="top">
    
    Select a date on the calendar.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Field Reference
    
    </td>
    <td valign="top">
    
    This is a reference to a field in the row indicating which date to use.
    
    </td>
    </tr>
    </table>
    
4.  Select the *Conversion Type*. The conversion types have been defined in your source system. Contact your system administrator for details, if you are unsure which one to take.

5.  Select the *Error Handling* method you would like to have applied when a row could not be converted.

    You have the following options:


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
    
    Set to null
    
    </td>
    <td valign="top">
    
    If any error happens during the currency conversion, the target value is set to NULL.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Fail on error
    
    </td>
    <td valign="top">
    
    The conversion fails with an error.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Keep unconverted
    
    </td>
    <td valign="top">
    
    The input value is returned.
    
    </td>
    </tr>
    </table>
    
6.  You can open or refresh the Data Preview panel to review the results of your currency conversion.




<a name="loio1ba4554f0aaf40f7b5c0e430eb2da510__result_u3s_3xj_jtb"/>

## Results

When you use the measure with currency conversion in a consumption model, you can see the converted currency in a story in SAP Analytics Cloud.

