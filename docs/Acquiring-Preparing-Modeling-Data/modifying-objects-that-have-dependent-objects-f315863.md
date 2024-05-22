<!-- loiof315863264db489593c7f54f1f7fd83e -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Modifying Objects That Have Dependent Objects

Once a table or view is created, it can be used as a source, or pointed to via an association by other objects. When a data access control is created it can be attached to one or more views to provide row level security. When you modify objects that have dependent objects, you may receive validation messages to warn you that your changes can impact these dependent objects.



<a name="loiof315863264db489593c7f54f1f7fd83e__steps_ywr_fdt_mpb"/>

## Procedure

1.  Open your table, view, or data access control to edit it in the usual way.

    You can see the objects that depend on your object by reviewing its *Dependent Objects* section \(see [Review the Objects That Depend on Your Table or View](review-the-objects-that-depend-on-your-table-or-view-ecac5fd.md)\).

2.  Make any appropriate changes. Certain changes may produce warning messages:


    <table>
    <tr>
    <th valign="top">

    Change
    
    </th>
    <th valign="top">

    Validation Message
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Add Column
    
    </td>
    <td valign="top">
    
    None.

    New columns are excluded by default from the output of dependent views and data flows and information messages are displayed.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Change Column Data Type
    
    </td>
    <td valign="top">
    
    Warning listing all dependent objects that use the column.

    > ### Note:  
    > You cannot change the data type of any columns that are used by a data access control \(see [Process Source Changes in the Data Access Control Editor](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/3c470e82554145658a5029d7a1dca4a0.html "If the permissions entity that is consumed by your data access control is modified, then the next time you open the data access control, you will be asked to process the changes. If the source change has generated warnings or errors in your data access control, its status will be updated and you will receive a notification inviting you to review the changes.") :arrow_upper_right:\).

    In the case of tables:

    -   You can always increase the length of a data type, but you can reduce it only if the change will not truncate any data currently held in the column. For example, if your column’s current data type is `string(256)` and the longest string contained in it is 200 characters, then you cannot reduce the length to less than `string(200)`.
    -   You can change the data type if the new type is compatible with the family of the old type and the data can be converted. For more information about data type conversions, see [Column Data Types](Acquiring-and-Preparing-Data-in-the-Data-Builder/column-data-types-7b1dc6e.md).

        > ### Note:  
        > You cannot change the data types of columns containing *ST\_POINT* or *ST\_GEOMETRY* data.



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Delete Column
    
    </td>
    <td valign="top">
    
    Warning listing all dependent objects that use the column.

    Column deletions will break dependent objects that use these columns. The last user to edit a dependent object will receive a notification inviting them to review the changes.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Add, Delete, or Change Data Type of Input Parameter
    
    </td>
    <td valign="top">
    
    Warning listing all dependent objects.

    All changes to input parameters must be processed in all dependent objects.

    > ### Note:  
    > You cannot add input parameters to views that are used as sources in data flows.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Change Business Properties
    
    </td>
    <td valign="top">
    
    None.

    Changes to the business name and other business properties of the object or its columns are propagated to dependent objects.
    
    </td>
    </tr>
    </table>
    
3.  Each time that you make a change, SAP Datasphere checks all dependent objects, generates a warning message if necessary, and updates the status of each object in the *Dependent Objects* list.

    For example there are ten views that use your view as a source, and which are listed in your view's *Dependent Objects* list. When you delete a column in your view, SAP Datasphere, checks to see which of the ten views use that column and, if one or more do, it generates a warning message and updates the status of each impacted object to *Design-Time Error*.

4.  When you have finished making changes, click *Save* to save your object.

    If any warnings have been generated, the *Validation Messages* dialog opens to allow you to review them. Click *Save Anyway* to save your changes and dismiss the warning messages.

    Notifications are sent to the last user who edited each of the dependent objects that now has a status of *Design-Time Error*, inviting them to review the changes. For more information, see:

    -   [Process Source Changes in the Table Editor](Acquiring-and-Preparing-Data-in-the-Data-Builder/process-source-changes-in-the-table-editor-622328b.md)
    -   [Process Source Changes in the Graphical View Editor](process-source-changes-in-the-graphical-view-editor-702350c.md)
    -   [Process Source Changes in the SQL View Editor](process-source-changes-in-the-sql-view-editor-f7e43ce.md)
    -   [Process Source/Target Changes in the Data Flow Editor](Acquiring-and-Preparing-Data-in-the-Data-Builder/process-source-target-changes-in-the-data-flow-editor-0af80aa.md)
    -   [Process Source Changes in the Data Access Control Editor](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/3c470e82554145658a5029d7a1dca4a0.html "If the permissions entity that is consumed by your data access control is modified, then the next time you open the data access control, you will be asked to process the changes. If the source change has generated warnings or errors in your data access control, its status will be updated and you will receive a notification inviting you to review the changes.") :arrow_upper_right:

5.  Click <span class="SAP-icons-V5"></span> \(Deploy\) to deploy your object.

    If any warnings have been generated, the *Validation Messages* dialog opens to allow you to review them. Click *Deploy Anyway* to deploy your changes and dismiss the warning messages.

    > ### Note:  
    > You should consider the impact of your object on its dependent objects before deploying it. If many objects or particularly important objects will be impacted, you should coordinate with the appropriate other users to deploy the source and its dependent objects together. You could create an ER model \(see [Creating an Entity-Relationship Model](creating-an-entity-relationship-model-a91c042.md)\) to contain the source and its dependent objects and use the ER model *Deploy* button to deploy them simultaneously once all the changes are processed.


