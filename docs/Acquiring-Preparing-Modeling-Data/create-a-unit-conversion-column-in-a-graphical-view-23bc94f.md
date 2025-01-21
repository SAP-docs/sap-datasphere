<!-- loio23bc94f6269c43a89d0ef5e4180811ba -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Create a Unit Conversion Column in a Graphical View

You can convert unit values into another unity using a calculated column containing the `CONVERT_UNIT` function. For example, you may want to convert inches to centimetres or pounds to kilograms.



## Context

To do unit conversion, the following tables must be available in your space:

-   `T006`
-   `T006D`

These tables should be imported from an SAP system via flows or as remote tables \(see [Acquiring Data in the Data Builder](Acquiring-and-Preparing-Data-in-the-Data-Builder/acquiring-data-in-the-data-builder-1f15a29.md)\).

> ### Note:  
> If `T006` and `T006D` are shared to your space, you must wrap each table in a view before it can be used for unit conversion in SAP Analytics Cloud.

For more information and examples, see the blog [SAP Datasphere Unit Conversion](https://community.sap.com/t5/technology-blogs-by-sap/sap-datasphere-unit-conversion/ba-p/13567259) \(published in August 2023\).



## Procedure

1.  In a *Calculated Columns* node, click <span class="FPA-icons-V3"></span> \(Add New Calculated Column\) to create a new column.

2.  Enter a *Business Name* and a *Technical Name* for the column, and specify an appropriate numerical *Data Type*.

3.  Enter the `CONVERT_UNIT` function into the expression field:

    ```
    CONVERT_UNIT("QUANTITY"=>"<Quantity>", 
        "SOURCE_UNIT" =>'<Source_Unit>', 
        "SCHEMA" => '<Space>', 
        "TARGET_UNIT" => '<Target_Unit>', 
        "ERROR_HANDLING"=>'<Error_Handling>', 
        "CLIENT" => '<Client>')
    ```

    For detailed information, see [CONVERT\_UNIT Function \(Miscellaneous\)](https://help.sap.com/docs/HANA_SERVICE_CF/7c78579ce9b14a669c1f3295b0d8ca16/f43ae7bb6f5b1014a345adb9db626de0.html) in the SAP HANA documentation.

    Complete the values as follows:


    <table>
    <tr>
    <th valign="top">

    Parameter
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Quantity
    
    </td>
    <td valign="top">
    
    Enter the column to convert.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Source Unit
    
    </td>
    <td valign="top">
    
    Enter one of the following:

    -   The technical name of the column containing the source unit.
    -   The value of the code for the source unit, as given in the *Unit of Measurement* column \(`MSEHI`\) in table `T006`. For example:
        -   `IN` - Inches
        -   `CM` - Centimetres
        -   `LB` - Pounds
        -   `KG` - Kilograms



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Schema
    
    </td>
    <td valign="top">
    
    Enter the technical name of your space.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Target Unit
    
    </td>
    <td valign="top">
    
    Enter one of the following:

    -   The technical name of the column containing the target unit.
    -   The value of the code for the target unit.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Error Handling
    
    </td>
    <td valign="top">
    
    Enter one of the following:

    -   `fail on error` \[default\] - Return an error.
    -   `set to null` - Set the target value to `NULL`.
    -   `keep unconverted` - Set the target value to the unconverted source value.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Client
    
    </td>
    <td valign="top">
    
    Enter the value of your SAP client.

    If you are unsure of the value to set, review the *Client* column \(`MANDT`\) in table `T006`.
    
    </td>
    </tr>
    </table>
    
4.  Click <span class="FPA-icons-V3"></span> \(Preview Data\) to open the *Data Preview* panel and review the data output by the column.


