<!-- loioec00efb338f3421a87dab4006d7ce6c8 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Create a Currency Conversion Measure

With a currency conversion measure, you can convert currencies.



<a name="loioec00efb338f3421a87dab4006d7ce6c8__prereq_nqr_5rf_mxb"/>

## Prerequisites

The tables and view containing currencies and exchange rates `SAP.CURRENCY.TABLE.TCUR*` are available in the current space.

You can create these tables in the *Data Builder* \(see [Enabling Currency Conversion with TCUR\* Tables and Views](../Creating-Finding-Sharing-Objects/enabling-currency-conversion-with-tcur-tables-and-views-b462239.md)\).



## Procedure

1.  You are in the editor of your analytic model. You can create a new currency conversion measure by clicking the background of the canvas and choosing <span class="FPA-icons-V3"></span> Add Measure in the properties panel. Choose *Currency Conversion Measure*.

2.  Edit the following properties:


    <table>
    <tr>
    <th valign="top">

    Property
    
    </th>
    <th valign="top">

    Desription
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Business Name
    
    </td>
    <td valign="top">
    
    Enter a descriptive name to help users identify the object. This name can be changed at any time.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Technical Name
    
    </td>
    <td valign="top">
    
    Displays the name used in scripts and code, synchronized by default with the *Business Name*.

    To override the default technical name, enter a new one in the field. Technical names can contain only alphanumeric characters and underscores.

    > ### Note:  
    > Once the object is saved, the technical name can no longer be modified.


    
    </td>
    </tr>
    </table>
    
3.  Edit the following properties:


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
    
    Source Measure
    
    </td>
    <td valign="top">
    
    The source measure has to be a fact source and has to refer to a measure in the underlying fact with semantic type *Amount with Currency*. The measure in the fact has to have an assigned currency field.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Target Currency
    
    </td>
    <td valign="top">
    
    The target currency can be specified as:

    -   a constant value

    -   a reference to a dimension that is mapped to an attribute of the fact with semantic type *Currency Code*.

    -   a variable. For more information, see [Use Variables for Currency Conversion](use-variables-for-currency-conversion-0379a7c.md).


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Reference Date
    
    </td>
    <td valign="top">
    
    The reference date can be:

    -   the current date
    -   a constant value, with a fixed date

    -   a reference to a dimension with data type *Date*
    -   a variable. For more information, see [Use Variables for Currency Conversion](use-variables-for-currency-conversion-0379a7c.md).


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Exchange Rate Type
    
    </td>
    <td valign="top">
    
    The exchange rate types are predefined.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Client
    
    </td>
    <td valign="top">
    
    The currency conversion tables have a client field, which you can enter here.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Error
    
    </td>
    <td valign="top">
    
    Select the error handling method. This defines how the system reacts when a value cannot be converted. Possible values are:

    -   Set to null

    -   Fail on error

    -   Keep unconverted



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Settings
    
    </td>
    <td valign="top">
    
    Decide whether your measure should be an *Auxiliary Measure*.An auxiliary measure can be used for further calculation but it will be hidden in the story in SAP Analytics Cloud.
    
    </td>
    </tr>
    </table>
    

