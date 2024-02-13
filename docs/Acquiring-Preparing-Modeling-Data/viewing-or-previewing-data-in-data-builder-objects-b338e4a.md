<!-- loiob338e4aa7e7e494eb68c383720ebfd3a -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Viewing or Previewing Data in Data Builder Objects

View the data contained in your tables and views and, when working in the graphical view editor, the data output by each of the nodes in the diagram. Preview the data contained in your tables and views when working in the E/R modeler or data flow.

This topic contains the following sections:

-   [Viewing Data in Data Builder Objects](viewing-or-previewing-data-in-data-builder-objects-b338e4a.md#loiob338e4aa7e7e494eb68c383720ebfd3a__section_viewing) in the graphical view editor, table editor, and SQL editor
-   [Previewing Data in Data Flows and E/R Models](viewing-or-previewing-data-in-data-builder-objects-b338e4a.md#loiob338e4aa7e7e494eb68c383720ebfd3a__section_previewing) in the E/R modeler and data flow

> ### Note:  
> Users with the standard *DW Modeler* role can preview data in any object in their space. Users with the *DW Viewer* role can only preview data output by views with the *Expose for Consumption* switch enabled. For more information, see [Roles and Privileges by App and Feature](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/2d8b7d04dcae402f911d119437ce0a74.html "Review the standard roles and the privileges needed to access apps, tools, and other features of SAP Datasphere.") :arrow_upper_right:.



<a name="loiob338e4aa7e7e494eb68c383720ebfd3a__section_viewing"/>

## Viewing Data in Data Builder Objects

You can view the data contained in tables, views, and graphical view output nodes when working in the graphical view editor, table editor, and SQL editor.



### Open the Data Viewer

You can view data in the following contexts in the data layer:

-   Table editor - View the data stored in a local table, a remote table, or an Open SQL/HDI Schema.
-   SQL view editor - View the SQL view output.
-   Graphical view editor - Click on any diagram symbol \(sources, intermediate nodes, or the output node\).
-   *Repository* tab of the *Source Browser* - Click on any entity to view its data before adding it to your diagram.

To open the *Data Viewer* panel, click <span class="SAP-icons"></span> \(Show or hide data viewer\)in a data object context menu, in the main toolbar, or in a diagram symbol toolbar.

> ### Note:  
> -   In the table editor or the view editor, the *Input Parameters* dialog appears if the remote table or the view contains one or more input parameters \(see [Create an Input Parameter](create-an-input-parameter-53fa99a.md)\). A value might already appear if the input parameter has a predefined default value. You can edit values at any moment by clicking the input parameter strip and entering a new value or get access to a list of predefined values with the *Value Help Dialog* if your input parameter has a predefined default value.
> 
>     > ### Note:  
>     > Previewing a SQL view isn't possible if one of the view's objects is shared from another space and has an input parameter.
> 
> -   If a column has *Binary*, *Large Binary*, *ST\_Point*, and *ST\_Geometry* set as data type, the data viewer is unavailable and records are shown as *Cannot be shown*. If no data can be found, the data viewer shows it as *NULL*.

The viewer headers indicate the total number of rows that can be displayed by scrolling down.

> ### Caution:  
> If you view data of a view that is persisted, the data is read from the corresponding persistency table of this view. In case the view is changed in the editor and not yet deployed, the data preview bypasses the persistency table and reads data form the view definition.



### Sort Data

You can control the data viewer in the following ways:

-   Reorder your columns in the panel by drag and drop.
-   Sort on a column by clicking the column header and then clicking <span class="SAP-icons"></span> \(Sort Ascending\) or <span class="SAP-icons"></span> \(Sort Descending\).
-   Filter on a column. For more information, see the **Filter Data** section below.



### Filter Data

Filter on a column by clicking the column header, clicking <span class="FPA-icons"></span> \(Filter\) to open the *Define Filter* dialog. The advanced filtering options are available:

1.  Choose the appropriate section for your filter. If your filter is meant to include data in the Data Viewer \(you could say "I want my Data Viewer to show"\), add your filter in the *Include* section. If your filter is meant to exclude data from the Data Viewer \(you could say "I want my Data Viewer to hide"\), add your filter in the *Exclude* section. When in the appropriate section, click <span class="FPA-icons"></span> \(Add Filter\) to add a filter.
2.  Select a column to filter on, a filtering option, and a value. You can add several filters. Click *OK* to apply the filter\(s\). The currently applied filters are displayed above the table.

    > ### Example:  
    > To only see senior employees born between 1960 and 1969, select the column containing birth dates, the filtering value *between*, and the earliest and latest dates needed. Once applied, the filter will be displayed in a strip above the table as following: `Birth Date ( Jan 1, 1960...Dec 31, 1969 )`.

    > ### Note:  
    > -   The filtering options available depend on the data type of the column you filter on.
    > -   The filtering option *empty* takes into account both empty and *NULL* values.
    > -   Filters applied to text columns are case-sensitive.
    > -   You can enter filter or sort values in multiple columns.

3.  Click *Clear Filter* in the filter strip or <span class="FPA-icons"></span> \(Remove Filter\)in the *Define Filter* dialog to remove the filter.



### Choose Columns to Display

Show, hide, sort, and filter on multiple columns by clicking :gear: to open the *View Settings* dialog. Three tabs allow you to change your data viewer:

-   **Columns** - select columns as appropriate and click *OK*.

-   **Sort** - select the column\(s\) to sort and if you want them sorted in and ascending or descending order.
-   **Filter** - filter on columns.

When you're done, click *OK* to update the viewer or *Cancel* to erase your changes. To return to the default data viewer columns, click *Reset*.

-   Refresh the data viewer at any time by clicking <span class="SAP-icons"></span> \(Refresh\).
-   Close the data viewer by clicking :x:.
-   In the *Graphical View* editor, preview the SQL generated for the node by clicking <span class="SAP-icons"></span> \(Preview SQL\). Click *Copy* to copy the SQL code for pasting into the *SQL View editor* or elsewhere.

> ### Note:  
> The data view may not be fully displayed:
> 
> -   If your data object is or relies on a remote table, viewing data may take a long time to load or cannot succeed. The data viewer also has a timeout limit of three minutes and will display an error on the *Errors* tab if it is unable to return data in that time. The restrictions inherent to remote tables are passed along to the output view. Replicate the remote table data to avoid long loading times and view instantly. For more information, see [Replicate Remote Table Data](Acquiring-and-Preparing-Data-in-the-Data-Builder/replicate-remote-table-data-7e258a7.md).
> -   Your data object data type is a *HANA Numeric* data type and cannot be viewed. In such cases, change the data type of your object to the corresponding one supported by SAP Datasphere. For more information, see [Column Data Types](Acquiring-and-Preparing-Data-in-the-Data-Builder/column-data-types-7b1dc6e.md).



<a name="loiob338e4aa7e7e494eb68c383720ebfd3a__section_previewing"/>

## Previewing Data in Data Flows and E/R Models

You can preview data contained in tables or views when working in the E/R modeler or data flow. Previewing and viewing data work in similar ways, except for the limitations listed below.



### Open the Data Preview

You can preview data in the following contexts in the data layer:

-   Data flow editor - Click on source or output symbols \(intermediate nodes do not support data preview\).
-   E/R model editor - Click on any diagram symbol \(tables and views\).

For more information, see the **Open the Data Viewer** section above.



### Working with the data preview

-   Sort data like in the data viewer. For more information, see the **Sort Data** section above.
-   Filter on a column by clicking the column header, clicking <span class="FPA-icons"></span> \(Filter\), and entering a value to filter on.
-   Select columns to display as appropriate in the *Columns* dialog. For more information, see the **Choose Columns to Display** section above.

> ### Restriction:  
> Contrarily to the data viewer, the data preview has the following restrictions:
> 
> -   The preview is limited to the first 1000 rows.
> -   The *Define Filter* dialog is unavailable.
> -   The *View Settings* dialog is unavailable. Only the viewer's *Columns* tab is available as the preview's *Columns* dialog.

