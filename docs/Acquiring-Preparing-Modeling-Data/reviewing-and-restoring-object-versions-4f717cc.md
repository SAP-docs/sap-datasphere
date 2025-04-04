<!-- loio4f717cc0d90e4453a072b37f6b043593 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Reviewing and Restoring Object Versions

Each time you deploy your object, a new version is created in the repository. You can review previous versions of an object at any time and choose to restore a previous version.

This topic contains the following sections:

-   [Introduction to Object Versioning](reviewing-and-restoring-object-versions-4f717cc.md#loio4f717cc0d90e4453a072b37f6b043593__section_intro)
-   [View Object Version History](reviewing-and-restoring-object-versions-4f717cc.md#loio4f717cc0d90e4453a072b37f6b043593__section_review)
-   [Export a Version to File](reviewing-and-restoring-object-versions-4f717cc.md#loio4f717cc0d90e4453a072b37f6b043593__section_download)
-   [Restore a Version](reviewing-and-restoring-object-versions-4f717cc.md#loio4f717cc0d90e4453a072b37f6b043593__section_restore)



<a name="loio4f717cc0d90e4453a072b37f6b043593__section_intro"/>

## Introduction to Object Versioning

Object versioning allows you to review the history of changes to your objects and, for certain types of objects, to restore a previous version. The following objects support versioning:


<table>
<tr>
<th valign="top">

Object Type

</th>
<th valign="top">

View/Export Versions

</th>
<th valign="top">

Restore Versions

</th>
</tr>
<tr>
<td valign="top">

Graphical views

See [Creating a Graphical View](creating-a-graphical-view-27efb47.md).

</td>
<td valign="top">

Yes

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

SQL views

See [Creating an SQL View](creating-an-sql-view-81920e4.md).

</td>
<td valign="top">

Yes

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

Analytic models

See [Creating an Analytic Model](Modeling-Data-in-the-Data-Builder/creating-an-analytic-model-e5fbe9e.md).

</td>
<td valign="top">

Yes

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

Local tables

See [Creating a Local Table](Acquiring-and-Preparing-Data-in-the-Data-Builder/creating-a-local-table-2509fe4.md).

</td>
<td valign="top">

Yes

</td>
<td valign="top">

Yes, with restrictions:

-   Any partitions must be deleted before you can restore to a previous version \(see [Partitioning Local Tables](Acquiring-and-Preparing-Data-in-the-Data-Builder/partitioning-local-tables-03191f3.md)\).
-   If your table is created from sources of type Open SQL Schema or HDI Container, restore is not supported \(see [Importing Tables and Views from Sources](Acquiring-and-Preparing-Data-in-the-Data-Builder/importing-tables-and-views-from-sources-7c4acd3.md)\).
-   Restore is not supported for generated time tables \(see [Create Time Data and Dimensions](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/c5cfce4d22b04650b2fd6078762cdeb9.html "Create a time table and dimension views in your space to provide standardized time data for your analyses. The time table contains a record for each day in the specified period (by default from 1900 to 2050), and the dimension views allow you to work with this date data at a granularity of day, week, month, quarter, and year, and to drill down and up in hierarchies.") :arrow_upper_right:\).



</td>
</tr>
<tr>
<td valign="top">

Local tables \(File\)

See [Creating a Local Table \(File\)](Acquiring-and-Preparing-Data-in-the-Data-Builder/creating-a-local-table-file-d21881b.md).

</td>
<td valign="top">

Yes

</td>
<td valign="top">

Yes, with restrictions:

-   If your table contains data, restore is not possible as physical deletion of data is not supported.
-   If your table is empty, restore is supported.



</td>
</tr>
<tr>
<td valign="top">

Remote tables

See [Importing Tables and Views from Sources](Acquiring-and-Preparing-Data-in-the-Data-Builder/importing-tables-and-views-from-sources-7c4acd3.md).

</td>
<td valign="top">

Yes

</td>
<td valign="top">

Not supported

</td>
</tr>
<tr>
<td valign="top">

E/R models

See [Creating an Entity-Relationship Model](creating-an-entity-relationship-model-a91c042.md).

</td>
<td valign="top">

Yes

</td>
<td valign="top">

Not supported

</td>
</tr>
<tr>
<td valign="top">

Transformation flows

See [Creating a Transformation Flow](creating-a-transformation-flow-f7161e6.md).

</td>
<td valign="top">

Yes

</td>
<td valign="top">

Not supported

</td>
</tr>
<tr>
<td valign="top">

Replication flows

See [Creating a Replication Flow](Acquiring-and-Preparing-Data-in-the-Data-Builder/creating-a-replication-flow-25e2bd7.md).

</td>
<td valign="top">

Yes

</td>
<td valign="top">

Not supported

</td>
</tr>
<tr>
<td valign="top">

Task chains

See [Creating a Task Chain](Acquiring-and-Preparing-Data-in-the-Data-Builder/creating-a-task-chain-d1afbc2.md).

</td>
<td valign="top">

Yes

</td>
<td valign="top">

Not supported

</td>
</tr>
<tr>
<td valign="top">

Data access controls

​See [Securing Data with Data Access Controls](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/a032e51c730147c7a1fcac125b4cfe14.html "Users with a space administrator role can create data access controls to allow modelers to apply row-level security to Data Builder and Business Builder objects. Once a data access control is applied to an object, any user viewing its data either directly or via an object using it as a source, will see only those records they are authorized to view, based on the specified criteria.") :arrow_upper_right:.

</td>
<td valign="top">

Yes

</td>
<td valign="top">

Yes

</td>
</tr>
<tr>
<td valign="top">

Packages

See [Creating Packages to Export](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/24aba84ceeb3416881736f70f02e3a0a.html "Users with the DW Space Administrator role can create packages to model groups of related objects for transport between tenants. Modelers can add objects to packages via the Package field, which appears in editors when a package is created in their space. Once a package is complete and validated, the space administrator can export it to the Content Network. The structure of your package is preserved and, as the objects it contains evolve, you can easily export updated versions of it.") :arrow_upper_right:.

</td>
<td valign="top">

Yes

</td>
<td valign="top">

Not supported

</td>
</tr>
</table>



<a name="loio4f717cc0d90e4453a072b37f6b043593__section_review"/>

## View Object Version History

To view the version history of an object:

1.  Open the object in its editor and click the *Versions* button in the toolbar.

    The *Version History* dialog opens, listing up to the last 500 versions of the object in reverse order.

2.  You can use the *Search* field to filter the list on any column.

    Versions can have the following types:

    -   *Deployment* - Created by a user deploying the object.
    -   *Move to Recycle Bin* - Created by a user deleting the space \(see [Delete Your Space](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/3eb19b96e6ba41dfbffd759c5c8370bb.html "Delete a space if you are sure that you no longer need any of its content or data. The space is moved to the recycle bin, from which it can either be restored or permanently deleted from the database.") :arrow_upper_right:\).
    -   *Restore from Recycle Bin* - Created by a user restoring the space.

3.  You can perform the following actions on an object version:
    -   *Open in New Tab* - Open the version to review it in its editor.
    -   *Export to CSN/JSON File* - Download the version to a CSN/JSON file \(see [Export a Version to File](reviewing-and-restoring-object-versions-4f717cc.md#loio4f717cc0d90e4453a072b37f6b043593__section_download)\).




<a name="loio4f717cc0d90e4453a072b37f6b043593__section_download"/>

## Export a Version to File

To export a version of an object:

1.  Open the object in its editor and click the *Versions* button in the toolbar.

    The *Version History* dialog opens, listing up to the last 500 versions of the object in reverse order.

2.  Find the version you want to export and click <span class="FPA-icons-V3"></span> \(More\)*Export to CSN/JSON File*.

    The contents of the editor are exported to <code><i class="varname">&lt;Object_Name&gt;</i>.json</code> and downloaded to your browser. For information about working with these files, see [Importing and Exporting Objects in CSN/JSON Files](Creating-Finding-Sharing-Objects/importing-and-exporting-objects-in-csn-json-files-f8ff062.md).




<a name="loio4f717cc0d90e4453a072b37f6b043593__section_restore"/>

## Restore a Version

If your object type supports restoring a previous version \(see [Introduction to Object Versioning](reviewing-and-restoring-object-versions-4f717cc.md#loio4f717cc0d90e4453a072b37f6b043593__section_intro)\):

1.  Open the object in its editor and click the *Versions* button in the toolbar.

    The *Version History* dialog opens, listing up to the last 500 versions of the object in reverse order.

2.  Find the version you want to restore and click <span class="FPA-icons-V3"></span> \(More\)*Open in New Tab*.

    The version opens in read-only format in a new tab, allowing you to review it in detail.

    > ### Note:  
    > No validation rules are applied and certain features, such as impact and lineage analysis and data preview are not supported.

3.  When you have decided to restore the version, click *Versions* \> *Restore*.

    The version becomes editable and the standard validation rules are applied.

4.  Review any validation errors and warnings and correct issues as far as possible.

    > ### Note:  
    > If the object has a *Release State* of *Released* or *Deprecated*, you must provide all the existing output columns as specified at the time of release \(see [Releasing Stable Views for Consumption](releasing-stable-views-for-consumption-5b99e9b.md)\).

5.  Click *Save* or *Deploy* to complete the restore.

