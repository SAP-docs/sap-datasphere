<!-- loio965ce56c835b4e4aaf8712c106d91719 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Create a Conversion Measure for Units

With a conversion measure, you can convert units into a target unit.



<a name="loio965ce56c835b4e4aaf8712c106d91719__prereq_svp_3jj_kfc"/>

## Prerequisites

To prepare for unit conversion, you must import the ***T006*** and ***T006D*** tables to your space from your SAP system \(or have these tables shared to your space from another space\). See [Enabling Unit Conversion with T006\* Tables and Views](enabling-unit-conversion-with-t006-tables-and-views-15e095d.md).



## Context

Unit conversion allows you to convert measures with units that have different units of measure in the source system into a uniform unit of measure in SAP Datasphere to enable a proper data analysis. You can only convert values within a unit of measurement, for example 1 m into 100 cm, 1 kg into 1000 g.



## Procedure

1.  You are in the editor of your analytic model. You can create a new conversion measure by clicking the background of the canvas and choosing <span class="FPA-icons-V3"></span> Add Measure in the properties panel. Choose *Conversion Measure*.

2.  Edit the following properties:


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
    > If you change the technical name after saving the model, this might affect existing stories or dependent analytic models.


    
    </td>
    </tr>
    </table>
    
3.  Select the source measure. The source measure has to be a fact source and has to refer to a measure in the underlying fact with semantic type *Weight* or *Quantity*. The measure in the fact has to have an assigned unit field.

4.  Define the unit properties:


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
    
    Target Unit
    
    </td>
    <td valign="top">
    
    The target unit can be specified as:

    -   a constant value. The available values are provided by the table T006 with unit texts from tableT006D.

    -   a reference to a dimension that is mapped to an attribute of the fact with semantic type *Quantity with Unit* or *Unit*.

    -   a variable. You can use an existing variable or you can create a variable for the target unit.


    
    </td>
    </tr>
    </table>
    
5.  Define further properties:


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
    
    The conversion tables have a client field, which you can enter here.
    
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
    
    Formatting
    
    </td>
    <td valign="top">
    
    You can change the format of a measure in an analytic model. You can change the scale \(Thousand, Million, Billion, Percent\) and the number of decimal places.

    > ### Example:  
    > A value of a measure with the formatting settings *Scale: Unformatted* and *Decimal Places: 3*will be displayed as 200, 200.000$
    > 
    > A value of a measure with the formatting settings *Scale: Million*and *Decimal Places: 2* will be displayed as 200.00Million$


    
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
    

