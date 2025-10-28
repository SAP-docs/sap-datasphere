<!-- loio4bd5e641be48409c8c79336df0c4a3c7 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Maintain Local Table Data

Use the *Data Editor* to add, delete, duplicate, or update records in local tables. You can also sort, filter, reorder, and replace data.

This topic contains the following sections:

-   [Prerequisites](maintain-local-table-data-4bd5e64.md#loio4bd5e641be48409c8c79336df0c4a3c7__section_prerequisites)
-   [Open the Data Editor](maintain-local-table-data-4bd5e64.md#loio4bd5e641be48409c8c79336df0c4a3c7__section_open)
-   [Add a Record](maintain-local-table-data-4bd5e64.md#loio4bd5e641be48409c8c79336df0c4a3c7__section_create)
-   [Edit a Record](maintain-local-table-data-4bd5e64.md#loio4bd5e641be48409c8c79336df0c4a3c7__section_edit)
-   [Duplicate a Record](maintain-local-table-data-4bd5e64.md#loio4bd5e641be48409c8c79336df0c4a3c7__section_duplicate)
-   [Delete a Record](maintain-local-table-data-4bd5e64.md#loio4bd5e641be48409c8c79336df0c4a3c7__section_delete)
-   [Find and Replace Data](maintain-local-table-data-4bd5e64.md#loio4bd5e641be48409c8c79336df0c4a3c7__section_replace)
-   [Sort Data](maintain-local-table-data-4bd5e64.md#loio4bd5e641be48409c8c79336df0c4a3c7__section_sort)
-   [Filter Data](maintain-local-table-data-4bd5e64.md#loio4bd5e641be48409c8c79336df0c4a3c7__section_filter)
-   [Choose Columns to Display](maintain-local-table-data-4bd5e64.md#loio4bd5e641be48409c8c79336df0c4a3c7__section_columns)
-   [Save Data Changes](maintain-local-table-data-4bd5e64.md#loio4bd5e641be48409c8c79336df0c4a3c7__section_save)



<a name="loio4bd5e641be48409c8c79336df0c4a3c7__section_prerequisites"/>

## Prerequisites

To edit local table data in the *Data Editor*, you must have a scoped role that grants you the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Space Files* \(`CRUD----`\) - To create, read, update, and delete objects in your spaces.
-   *Data Warehouse Data Builder* \(`-RU-----`\) - To access the local table *Data Editor* screen in the *Data Builder*.
-   *Data Warehouse Consumption* \(`-RU-E---`\) - To add and delete data in a local table.

The *DW Modeler* role template, for example, grants these privileges. For more information, see [Privileges and Permissions](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/d7350c6823a14733a7a5727bad8371aa.html "A privilege represents a task or an area in SAP Datasphere and can be assigned to a specific role. The actions that can be performed in the area are determined by the permissions assigned to a privilege.") :arrow_upper_right: and [Standard Roles Delivered with SAP Datasphere](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/a50a51d80d5746c9b805a2aacbb7e4ee.html "SAP Datasphere is delivered with several standard roles. A standard role includes a predefined set of privileges and permissions.") :arrow_upper_right:. 

You can only maintain data in local tables that:

-   Have status of *Deployed*.
-   Include at least one key column \(which does not have a data type of *cds.Binary* or *cds.hana.BINARY*\).
-   Do not contain binary \(hana.BINARY, Binary, LargeBinary\) or geo \(abap.geom\_ewkb, hana.ST\_POINT, hana.ST\_GEOMETRY\) columns that have the *Not Null* property set or binary columns containing *NULL* values.
-   Do not contain SAP-managed data \(for example, generated time tables, see [Create Time Data and Dimensions](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/c5cfce4d22b04650b2fd6078762cdeb9.html "Create a time table and dimension views in your space to provide standardized time data for your analyses. The time table contains a record for each day in the specified period (by default from 1900 to 2050), and the dimension views allow you to work with this date data at a granularity of day, week, month, quarter, and year, and to drill down and up in hierarchies.") :arrow_upper_right:\).

> ### Note:  
> Using values like `1.1`in hana.REAL columns may store them as `1.100000023841858.` This can cause issues in calculations. Use DECIMAL or for precise values.



<a name="loio4bd5e641be48409c8c79336df0c4a3c7__section_open"/>

## Open the Data Editor

To open the *Data Editor* for a local table:

1.  In the *Data Builder* start page, click the local table whose data you want to edit.
2.  Click the*Data Editor* button.

    > ### Note:  
    > You can open the data editor directly by saving the URL as a favorite in your browser.

3.  The following tools are available in the *Data Editor* toolbar:


    <table>
    <tr>
    <th valign="top">

    Tool
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Add
    
    </td>
    <td valign="top">
    
    See [Add a Record](maintain-local-table-data-4bd5e64.md#loio4bd5e641be48409c8c79336df0c4a3c7__section_create).

    This tool is not available if any key column \(or Not Null column without a default value\) is hidden.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Delete
    
    </td>
    <td valign="top">
    
    See [Delete a Record](maintain-local-table-data-4bd5e64.md#loio4bd5e641be48409c8c79336df0c4a3c7__section_delete).

    This tool is not available if you have unsaved changes.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Duplicate
    
    </td>
    <td valign="top">
    
    See [Duplicate a Record](maintain-local-table-data-4bd5e64.md#loio4bd5e641be48409c8c79336df0c4a3c7__section_duplicate).

    This tool is not available if any key column \(or Not Null column without a default value\) is hidden.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Restore
    
    </td>
    <td valign="top">
    
    Undo all edits and return to previously saved values.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Insert Missing String Value as
    
    </td>
    <td valign="top">
    
    Specify how empty string cells are interpreted when adding a record. Select from:

    -   NULL \(default\)
    -   Empty value


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Column settings \(:gear:\)
    
    </td>
    <td valign="top">
    
    See [Choose Columns to Display](maintain-local-table-data-4bd5e64.md#loio4bd5e641be48409c8c79336df0c4a3c7__section_columns).
    
    </td>
    </tr>
    </table>
    



<a name="loio4bd5e641be48409c8c79336df0c4a3c7__section_create"/>

## Add a Record

To create a new data record:

1.  Click the *Add* button.

    An empty row will appear at the top of the table.

2.  Enter values in the appropriate cells.

    The data in each cell must comply with the data type and other properties of the column. In particular:

    -   Each key value must be unique.
    -   Each Not Null field must contain an appropriate value.

    If warnings or errors are shown, click the <span class="FPA-icons-V3"></span> \(Validation Messages\) for details.




<a name="loio4bd5e641be48409c8c79336df0c4a3c7__section_edit"/>

## Edit a Record

To edit a record:

1.  \(optional\) Filter or sort data to find the record you want to edit.

    See [Filter Data](maintain-local-table-data-4bd5e64.md#loio4bd5e641be48409c8c79336df0c4a3c7__section_filter) and [Sort Data](maintain-local-table-data-4bd5e64.md#loio4bd5e641be48409c8c79336df0c4a3c7__section_sort).

2.  Click in the cell you want to edit and enter a new value.

    The data in each cell must comply with the data type and other properties of the column. In particular:

    -   Each key value must be unique.
    -   Each Not Null field must contain an appropriate value.

    If warnings or errors are shown, click the <span class="FPA-icons-V3"></span> \(Validation Messages\) for details.

    > ### Note:  
    > Columns with the data types Binary, hana.BINARY, LargeBinary, hana.ST\_GEOMETRY, and hana.ST\_POINT, are read-only and can't be edited.




<a name="loio4bd5e641be48409c8c79336df0c4a3c7__section_duplicate"/>

## Duplicate a Record

> ### Note:  
> This tool is not available if any key column \(or Not Null column without a default value\) is hidden.

To duplicate records:

1.  Select one or more records.
2.  Click the *Duplicate* button.
3.  Edit the duplicated values as necessary.

    The data in each cell must comply with the data type and other properties of the column. In particular:

    -   Each key value must be unique.
    -   Each Not Null field must contain an appropriate value.

    If warnings or errors are shown, click the <span class="FPA-icons-V3"></span> \(Validation Messages\) for details.




<a name="loio4bd5e641be48409c8c79336df0c4a3c7__section_delete"/>

## Delete a Record

> ### Note:  
> This tool is not available if you have unsaved changes.

To delete a record:

1.  Select one or more records.
2.  Click the*Delete* button.

    > ### Note:  
    > If *Delta Capture* is enabled, the records are simply marked as deleted, but will not be removed \(see [Controlling Deletion of Local Table Records](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/2a59b7142e1b4d478b0bf4063084261e.html "Delete records for local tables, on-demand, using filter conditions or using a schedule.") :arrow_upper_right:.




<a name="loio4bd5e641be48409c8c79336df0c4a3c7__section_replace"/>

## Find and Replace Data

To find \(or find and replace\) data in text columns:

1.  Click the header of the column you want to search in and select *Find and Replace*.
2.  In the dialog, complete the settings as follows:


    <table>
    <tr>
    <th valign="top">

    Setting
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Find
    
    </td>
    <td valign="top">
    
    Enter the value to search for.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Replace By
    
    </td>
    <td valign="top">
    
    \(optional\) Enter a replacement value.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Match Case
    
    </td>
    <td valign="top">
    
    Select to make your search case-sensitive.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Match Entire Field
    
    </td>
    <td valign="top">
    
    Select to ignore partial matches.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Show Occurrence Count
    
    </td>
    <td valign="top">
    
    Select to return the number of records. In large tables, enabling this feature may reduce performance.
    
    </td>
    </tr>
    </table>
    



<a name="loio4bd5e641be48409c8c79336df0c4a3c7__section_sort"/>

## Sort Data

> ### Note:  
> This tool is not available if you have unsaved changes.

You can sort the data in the following ways:

-   Click a column header and then click <span class="SAP-icons-V5"></span> \(Sort Ascending\) or <span class="SAP-icons-V5"></span> \(Sort Descending\).
-   Click :gear: to open the *View Settings* dialog, and then click the *Sort* tab. Select the columns to sort by, whether to sort each one by ascending or descending order, and click *OK* to update the viewer.



<a name="loio4bd5e641be48409c8c79336df0c4a3c7__section_filter"/>

## Filter Data

> ### Note:  
> This tool is not available if you have unsaved changes.

To filter the data:

1.  Click a column header and then <span class="FPA-icons-V3"></span> \(Filter\) to open the *Define Filter* dialog, or click :gear: and then click the *Filter* tab.
2.  Choose the appropriate section for your filter:
    -   *Include* - Enter one or more filter conditions that must be met in order to display a row.
    -   *Exclude* - Enter one or more filter conditions that must be met in order to hide a row.

3.  Select a column to filter on, an operator, and a value.

    For example, to filter the data to see only employees born between 1960 and 1969:

    -   Select the `Birth Date` column.
    -   Select the *between* operator.
    -   Select `Jan 1, 1960` in the *From* field and `Dec 31, 1969` in the *To* field.

4.  \[optional\] Click <span class="FPA-icons-V3"></span> \(Add Filter\) to add further conditions in either the *Include* or *Exclude* section.

    > ### Note:  
    > -   The filtering options available depend on the data type of the column you filter on.
    > -   Filters applied to text columns are case-sensitive.
    > -   You can combine *Include* and *Exclude* conditions
    > -   Using the *Filter* and *Sort* tabs in the *View Settings* dialog allows you to combine filtering and sorting by multiple columns.
    > -   The filtering option *empty* takes into account both empty and *NULL* values.

5.  Click *OK* to apply the filters.

    The current filter conditions are displayed in a strip across the top of the panel. Click *Clear Filter* to remove them.




<a name="loio4bd5e641be48409c8c79336df0c4a3c7__section_columns"/>

## Choose Columns to Display

> ### Note:  
> This tool is not available if you have unsaved changes.

To reorder the columns, click and drag a column header to left or right and drop it in its new position.

To display, hide, or reorder columns, click :gear: to open the *View Settings* dialog. On the *Columns* tab:

-   Select a checkbox to display a column or unselect it to hide a column.
-   Click a column name to select it and then use the arrow buttons to move it up or down in the list.
-   Use the *Show Selected*/*Show All* button to toggle between the two different lists.
-   Use the *Sort* and *Filter* tabs

Click *OK* to update the columns or *Cancel* to undo your changes. To return to the default columns, click *Reset*.



<a name="loio4bd5e641be48409c8c79336df0c4a3c7__section_save"/>

## Save Data Changes

To save the changes you have made to the data:

1.  Click *Save* in the main tool bar.
2.  To exit the *Data Editor*, click the *Table Editor* button or close your browser tab.

