<!-- loio8bba251c78874736963703cff56b1b74 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Creating a Local Table from a CSV File

Import a `.csv` file to create a table and fill it with the data from the file.



<a name="loio8bba251c78874736963703cff56b1b74__prereq_emk_5ht_zgc"/>

## Prerequisites

To create local tables, you must have a scoped role that grants you access to a space with the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Data Warehouse Data Builder* \(`CRUD----`\) - To create, edit and delete *Data Builder* objects.
-   *Space Files* \(`CRUD----`\) - To create, read, update, and delete objects in your spaces.
-   *Data Warehouse Consumption* \(`-RU-----`\) - To upload data in a local table.

The *DW Modeler* role template, for example, grants these privileges. For more information, see [Privileges and Permissions](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/d7350c6823a14733a7a5727bad8371aa.html "A privilege represents a task or an area in SAP Datasphere and can be assigned to a specific role. The actions that can be performed in the area are determined by the permissions assigned to a privilege.") :arrow_upper_right: and [Standard Roles Delivered with SAP Datasphere](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/a50a51d80d5746c9b805a2aacbb7e4ee.html "SAP Datasphere is delivered with several standard roles. A standard role includes a predefined set of privileges and permissions.") :arrow_upper_right:. 



<a name="loio8bba251c78874736963703cff56b1b74__context_drj_k2f_ypb"/>

## Context

> ### Note:  
> This procedure explains how to upload a CSV file to create a new local table in SAP Datasphere with the possibility to perform some data transformations during the upload. To load data into an existing local table \(without transformations\), use the <span class="FPA-icons-V3"></span> \(Upload Data From CSV File\) tool in the table editor \(see [Creating a Local Table](creating-a-local-table-2509fe4.md)\).



## Procedure

1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(*Data Builder*\), select a space if necessary, and click *Import* \> *Import CSV File* to open the editor.

2.  Click *Select Source File*, navigate to, and select the CSV file you want to upload.

    > ### Note:  
    > The file must have the extension `*.csv` and contain Unicode text only. The file size must not exceed 25 MB.

    > ### Caution:  
    > If you have a source connected via a FlowAgent or an SAP HANA smart data integration connector, you may consider the following while loading a CSV file: Values that cannot be converted to their assigned datatype, such as numeric fields with leading zeroes, will be considered invalid by the service and will be replaced by null. If you are creating a flow, this does not prevent you to run and deploy it.
    > 
    > For scenarios where fields contain numeric values with leading zeros, you can follow these steps to import them successfully:
    > 
    > 1.  Ensure the field containing zero value is imported as a string type.
    > 2.  Connect the source operator to a projection operator.
    > 3.  In the projection operator, create a new calculated column.
    > 4.  Set the column’s properties to use the field with leading zeroes and set its type to "decimal" with appropriate precision/scale.
    > 5.  Map the projected column to the target table.
    > 6.  Validate the output using data preview before running the import.

3.  Review the following options, and then click *Upload* to open your file in SAP Datasphere:


    <table>
    <tr>
    <th valign="top">

    Option
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Use first row as column header.
    
    </td>
    <td valign="top">
    
    Select if your file contains column headers in its first line.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    CSV Delimiter
    
    </td>
    <td valign="top">
    
    Select the character used to signify the boundary between columns. In general, the default value, `Auto-detect` is sufficient.
    
    </td>
    </tr>
    </table>
    
    The preview page shows a data preview on the left and a side panel showing the properties of the file or of a selected column, on the right.

4.  \[optional\] In the side panel, review the list of columns to be created. Hover over a column in the list and click *Details* to view and modify the properties of the column \(see [Column Properties and Profiling](column-properties-and-profiling-32654ad.md)\).

    > ### Note:  
    > The values of a hana.REAL column are automatically converted when their format is invalid.
    > 
    > > ### Example:  
    > > The value `1.1` will be read and written as `1.100000023841858`.
    > 
    > This will cause issues if this column is used as a calculated column. In that case, avoid conversion by setting the column to another data type.

5.  \[optional\] Perform data preparation transformations to modify the list of columns to be created, to delete rows, and to modify data in cells \(see [Apply Data Transforms](apply-data-transforms-3f0d747.md)\).

6.  When you have performed all necessary transformations and validations, click *Deploy* to open the *Deploy Table* dialog.

7.  Enter a business and technical name for your table and click *Deploy* to create the table and deploy it with the imported data.

    You are returned to the *Data Builder* start page and will receive a notification when the deployment is complete and the table can be opened in the table editor.


