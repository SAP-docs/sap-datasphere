<!-- loiob338e4aa7e7e494eb68c383720ebfd3a -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Viewing Object Data

You can, at any time, view the data contained in \(or output by\) your tables, views, and other *Data Builder* objects. When working in the graphical view editor, you can view the data output by each node in the diagram.

This topic contains the following sections:

-   [Prerequisites](viewing-object-data-b338e4a.md#loiob338e4aa7e7e494eb68c383720ebfd3a__section_prerequisites)
-   [Open the Data Viewer](viewing-object-data-b338e4a.md#loiob338e4aa7e7e494eb68c383720ebfd3a__section_open)
-   [Sort Data](viewing-object-data-b338e4a.md#loiob338e4aa7e7e494eb68c383720ebfd3a__section_sort)
-   [Filter Data](viewing-object-data-b338e4a.md#loiob338e4aa7e7e494eb68c383720ebfd3a__section_filter)
-   [Choose Columns to Display](viewing-object-data-b338e4a.md#loiob338e4aa7e7e494eb68c383720ebfd3a__section_columns)
-   [View Data as a Different User](viewing-object-data-b338e4a.md#loiob338e4aa7e7e494eb68c383720ebfd3a__section_impersonation)
-   [Preview Data in Data Flows](viewing-object-data-b338e4a.md#loiob338e4aa7e7e494eb68c383720ebfd3a__section_preview)



<a name="loiob338e4aa7e7e494eb68c383720ebfd3a__section_prerequisites"/>

## Prerequisites

To view the data contained in the *Data Builder* objects, you must have a scoped role that grants you access to a space with the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Space Files* \(`-R------`\) - To read objects in your spaces.
-   *Data Warehouse Data Builder* \(`-R------`\) - To open *Data Builder* objects.
-   *Data Warehouse Consumption*- To view data in the *Data Viewer* panel. Two levels of access are available:
    -   *Data Warehouse Consumption* \(`-R------`\) - To view only data output by views with the *Expose for Consumption* switch enabled.

        The *DW Viewer* role template, for example, grants this privilege.

    -   *Data Warehouse Consumption* \(`----E---`\) - To view data from any object or diagram node \(where this is supported\).

        The *DW Modeler* role template, for example, grants this privilege.



For more information, see [Privileges and Permissions](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/d7350c6823a14733a7a5727bad8371aa.html "A privilege represents a task or an area in SAP Datasphere and can be assigned to a specific role. The actions that can be performed in the area are determined by the permissions assigned to a privilege.") :arrow_upper_right: and [Standard Roles Delivered with SAP Datasphere](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/a50a51d80d5746c9b805a2aacbb7e4ee.html "SAP Datasphere is delivered with several standard roles. A standard role includes a predefined set of privileges and permissions.") :arrow_upper_right:. 



<a name="loiob338e4aa7e7e494eb68c383720ebfd3a__section_open"/>

## Open the Data Viewer

You can view data in the table, graphical view, SQL view, E/R model, analytic model, and transformation flow editors. The analytic model has an additional analytic data viewer \(see [Preview Data in an Analytic Model](Modeling-Data-in-the-Data-Builder/preview-data-in-an-analytic-model-9f1fa73.md)\). The data flow editor provides a limited data preview \(see [Preview Data in Data Flows](viewing-object-data-b338e4a.md#loiob338e4aa7e7e494eb68c383720ebfd3a__section_preview)\). 

> ### Note:  
> Users with the standard *DW Modeler* role can preview data in any object in their space. Users with the *DW Viewer* role can only preview data output by views with the *Expose for Consumption* switch enabled. For more information, see [Roles and Privileges by App and Feature](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/2d8b7d04dcae402f911d119437ce0a74.html "Review the standard roles and the privileges needed to access apps, tools, and other features of SAP Datasphere.") :arrow_upper_right:.

1.  To open the *Data Viewer* panel
    -   In the main toolbar, or in a diagram symbol menu, click <span class="SAP-icons-V5"></span> \(Data Viewer\), or
    -   In the Source Browser, click *More* \> *Show Data Preview*.

2.  If the object contains one or more input parameters, the *Input Parameters* dialog opens. You can accept the default value, if one is provided, or enter a value for each input parameter. If a value help is available, click <span class="SAP-icons-V5"></span> \(Value Help\) to select from a list of available values, and then click *OK*.

    The values are applied to the data and are displayed on a strip above the table. You can edit the values at any time by clicking the strip to re-open the dialog.

3.  The data is displayed, and the panel header shows the number of rows that are available.

    A maximum of 1,000 rows can be shown. If the records you want to see are not shown, then apply filters to find them.

    > ### Note:  
    > -   When viewing data in a graphical view, the panel will update as you select different nodes in the diagram, so that it is also showing data from the currently selected diagram node.
    > -   The *Data Viewer* will time out and display an error on the *Errors* tab if it is unable to load data in under three minutes. If you experience timeouts or slow performance and some or all of the data you want to view is not replicated to SAP Datasphere, consider replicating it \(see [Replicate Remote Table Data](Acquiring-and-Preparing-Data-in-the-Data-Builder/replicate-remote-table-data-7e258a7.md)\).
    > -   If a column has a *HANA Numeric* data type its data cannot be shown. Consider, changing the data type to one supported by SAP Datasphere \(see [Column Data Types](Acquiring-and-Preparing-Data-in-the-Data-Builder/column-data-types-7b1dc6e.md)\).
    > -   If a column has *Binary*, *Large Binary*, *ST\_Point*, and *ST\_Geometry* set as data type, the data viewer is unavailable and records are shown as *Cannot be shown*. If no data can be found, the data viewer shows it as *NULL*.
    > -   When viewing data in a persisted view, the data is read from the view's persistence table, unless the view has a status of *Changes to Deploy*, in which case the view is run and the results displayed. Note also that changes and redeployment can impact the data persistence. For more information, see [Persist Data in a Graphical or SQL View](persist-data-in-a-graphical-or-sql-view-9bd12cf.md) and [Process Source Changes in a Graphical View](process-source-changes-in-a-graphical-view-702350c.md).

4.  The following tools are available in the panel toolbar:


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
    
    <span class="SAP-icons-V5"></span> \(Refresh\)
    
    </td>
    <td valign="top">
    
    Refresh the data displayed in the panel.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    <span class="SAP-icons-V5"></span> \(Preview SQL\)
    
    </td>
    <td valign="top">
    
    \[graphical views\] Preview the SQL generated for the selected node. Use the *Copy* button to copy the SQL code for pasting into the SQL view editor or elsewhere.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    <span class="SAP-icons-V5"></span> \(Export Support Information\)
    
    </td>
    <td valign="top">
    
    Download a file containing technical information to send to SAP support.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    <span class="SAP-icons-V5"></span> \(Preview as User\)
    
    </td>
    <td valign="top">
    
    \[views\] Open the *Preview as User* dialog to select another user to preview the data with their permissions and see which records will be visible to them. Select a space user from the list or enter any other user identifier \(see [View Data as a Different User](viewing-object-data-b338e4a.md#loiob338e4aa7e7e494eb68c383720ebfd3a__section_impersonation)\).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    :gear:
    
    </td>
    <td valign="top">
    
    Open the *Settings* dialog \(see [Choose Columns to Display](viewing-object-data-b338e4a.md#loiob338e4aa7e7e494eb68c383720ebfd3a__section_columns)\).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    :x:
    
    </td>
    <td valign="top">
    
    Close the panel.
    
    </td>
    </tr>
    </table>
    



<a name="loiob338e4aa7e7e494eb68c383720ebfd3a__section_sort"/>

## Sort Data

You can sort the data in the following ways:

-   Click a column header and then click <span class="SAP-icons-V5"></span> \(Sort Ascending\) or <span class="SAP-icons-V5"></span> \(Sort Descending\).
-   Click :gear: to open the *View Settings* dialog, and then click the *Sort* tab. Select the columns to sort by, whether to sort each one by ascending or descending order, and click *OK* to update the viewer.

> ### Note:  
> When viewing SQL view data, any `ORDER BY` clause in the SQL code is ignored.



<a name="loiob338e4aa7e7e494eb68c383720ebfd3a__section_filter"/>

## Filter Data

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




<a name="loiob338e4aa7e7e494eb68c383720ebfd3a__section_columns"/>

## Choose Columns to Display

To display, hide, or reorder columns, click :gear: to open the *View Settings* dialog. On the *Columns* tab:

-   Select a checkbox to display a column or unselect it to hide a column.
-   Click a column name to select it and then use the arrow buttons to move it up or down in the list.
-   Use the *Show Selected*/*Show All* button to toggle between the two different lists.
-   Use the *Sort* and *Filter* tabs



<a name="loiob338e4aa7e7e494eb68c383720ebfd3a__section_impersonation"/>

## View Data as a Different User

You can review the effects of any data access controls you apply to a view by checking the records that another user will be allowed to see:

1.  Click <span class="SAP-icons-V5"></span> \(View as User\) to open the *View as User* dialog.
2.  Select a space user from the list or enter any other user identifier and then click *View*.

    The data viewer updates to show only the records visible to the selected user.

    > ### Note:  
    > *View as User* is only available in the graphic view, SQL view, and analytic model editors, and can only simulate data access controls that are applied in the current space and which have a status of *Deployed*. If the data access controls affecting your object were last deployed before your tenant was updated to version 2024.15 on July 16, 2024, you must re-deploy them.
    > 
    > In addition, if the view:
    > 
    > -   Is shared from another space then *View as User* is not supported.
    > -   Has one or more sources shared from other spaces, then a warning is shown to indicate that you may not see exactly the same records as the user you are impersonating.


For more information about data access controls, see [Securing Data with Data Access Controls](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/a032e51c730147c7a1fcac125b4cfe14.html "Users with a space administrator role can create data access controls to allow modelers to apply row-level security to Data Builder and Business Builder objects. Once a data access control is applied to an object, any user viewing its data either directly or via an object using it as a source, will see only those records they are authorized to view, based on the specified criteria.") :arrow_upper_right:.



<a name="loiob338e4aa7e7e494eb68c383720ebfd3a__section_preview"/>

## Preview Data in Data Flows

You can preview data for any source or output of a data flow \(intermediate nodes do not support data preview\), but the following limitations apply:

-   The preview can only show the first 1,000 records retrieved from the object, and any filters are only applied on these 1,000 records.
-   The complex filtering available in *Define Filter* dialog is not available. You can only filter only on simple values by clicking a column header and selecting <span class="FPA-icons-V3"></span> \(Filter\).
-   The *View Settings* dialog is not available. Use the *Columns* dialog to choose columns to display.

