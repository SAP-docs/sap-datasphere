<!-- loio4bd5e641be48409c8c79336df0c4a3c7 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Maintain Local Table Data

Maintain data stored in a local table in the table editor by clicking the *Data Editor* button. You can add, edit, duplicate, and delete records.



## Context

> ### Note:  
> Users with the standard *DW Modeler* role can edit data in this screen. For more information, see [Roles and Privileges by App and Feature](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/2d8b7d04dcae402f911d119437ce0a74.html "Review the standard roles and the privileges needed to access apps, tools, and other features of SAP Datasphere.") :arrow_upper_right:.

You can maintain data in local tables that:

-   Have a status *Deployed*.
-   Have at least one key column. Tables with binary key columns can't be updated in the *Data Editor*.

> ### Note:  
> You cannot edit the data in the generated time table \(see [Create Time Data and Dimensions](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/c5cfce4d22b04650b2fd6078762cdeb9.html "Create a time table and dimension views in your space to provide standardized time data for your analyses. The time table contains a record for each day in the specified period (by default from 1900 to 2050), and the dimension views allow you to work with this date data at a granularity of day, week, month, quarter, and year, and to drill down and up in hierarchies.") :arrow_upper_right:\).



## Procedure

1.  In the *Data Builder Entry Page*, click a local table to open your table's data for editing.

2.  Click *Data Editor*.

    > ### Tip:  
    > Directly open an object in its data editor by pasting its URL in your browser's address bar.

    You can sort, reorder, filter, or replace your data:

    -   **Reorder** - Drag and drop your columns to reorder them.
    -   **Sort** - Click on the column header and click <span class="SAP-icons-V5"></span> \(Sort Ascending\) or <span class="SAP-icons-V5"></span> \(Sort Descending\).
    -   **Filter** - Click on the column header and <span class="FPA-icons-V3"></span> \(Filter\) to open the *Define Filter* dialog. Click <span class="FPA-icons-V3"></span> \(Add Filter\), select a column to filter on, a filtering option, and a value. You can apply several filters.
    -   **Find and Replace** - Click on the column header and <span class="SAP-icons-V5"></span> \(Find and Replace\) to open the *Find and Replace* dialog. You can find and replace string values that aren't key columns or delta table columns. Enter a string value or select *Empty* or *Null* values in the *Find* and *Replace* fields. Check *Match Case* or *Match Entire Field* in the *Settings* sections. \(optional\) Toggle on the occurrence count.
    -   **Control the previewed columns** - Click <span class="FPA-icons-V3"></span> \(Columns Settings\) and select the columns to show in the preview.

    > ### Note:  
    > -   The values of a hana.REAL column are automatically overwritten when their format is invalid.
    > 
    >     > ### Example:  
    >     > The value `1.1` is incorrectly formatted and will be overwritten as `1.100000023841858`.
    > 
    >     This will cause issues if this column is used as a calculated column. In that case, avoid conversion by setting the column to another data type.
    > 
    > -   Opening the data editor isn't be possible if:
    >     -   A key column has its data type set to*cds.Binary* or *cds.hana.BINARY*.
    >     -   A binary column has records appearing as *empty* and *empty* records set as *NULL*.
    >     -   A *Not Null* column has its data type is set to one of the following types:
    >         -   hana.BINARY
    >         -   Binary
    >         -   LargeBinary
    >         -   abap.geom\_ewkb
    >         -   hana.ST\_POINT
    >         -   hana.ST\_GEOMETRY

3.  Update the table data as appropriate. You can:

    -   **Add a record** - Click *Add* to create a blank record and fill the cells as appropriate.
    -   **Edit a record** - Click in the cell you want to edit and enter a new value.

        > ### Note:  
        > Columns with the data types Binary, hana.BINARY, LargeBinary, hana.ST\_GEOMETRY, and hana.ST\_POINT, are read-only and can't be updated.

    -   **Duplicate a record** - Select one or more records to duplicate and click *Duplicate*. Update cells as appropriate. You must enter a new, unique value in key columns.
    -   **Delete a record** - Select one or more records and click *Delete*. For local table with delta capture enabled, the record is not physically deleted but only marked as "Deleted".

        > ### Caution:  
        > To physically delete a record, you also need the role *DW Integrator* or *DW Administrator*. For more information, see [Load or Delete Local Table Data](load-or-delete-local-table-data-870401f.md) and [Capturing Delta Changes in Your Local Table](capturing-delta-changes-in-your-local-table-154bdff.md)

    -   **Restore last saved values** - Click *Restore*. All unsaved changes will be lost.
    -   **Define a default value for empty strings** - Next to *Insert missing string value as*, select *Empty value* or *NULL* before adding a record. All new empty string cells are automatically filled in with the selected value.

    > ### Note:  
    > -   *Add* and *Duplicate* tools are restricted when a Key column or a Not Null column without a set default value are hidden. Show these columns to enable all tools.
    > -   *Filter*, *Sort*, *Delete*, and *Column Settings* tools are disabled by unsaved changes. Save your changes to enable them.
    > -   When invalid values are added to or duplicated in the table, a red or yellow frame appears to let you know where changes are required. Frames appear when:
    > 
    >     -   An invalid value is added.
    > 
    >     -   A key value is duplicated and must be edited to be unique.
    >     -   The value's format is invalid.
    >     -   A field cannot be left empty.
    > 
    >     Click <span class="FPA-icons-V3"></span> \(Validation Messages\) on the top right corner of your screen to get guidance on how to solve your issue.

    > ### Caution:  
    > If you have enabled *Delta Capture* for your local table, changes are tracked with 2 columns, *Change Type* and *Change Date*. Deleting a record will not physically delete it, but will set the change type to "D" \(Delete\). Therefore, you can't add a new record with a key that already exists, even if the record has the change type set to "D". For more information, see [Capturing Delta Changes in Your Local Table](capturing-delta-changes-in-your-local-table-154bdff.md)

4.  Click <span class="FPA-icons-V3"></span> \(Save\) to save your changes and click *Table Editor* to close the *Data Editor* and return to the *Table Editor*.


