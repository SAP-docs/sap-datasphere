<!-- loio6b2d0073a8684ee6a59d6f47d00ec895 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Monitoring Local Tables \(File\)

Monitor your local tables \(file\). Check how and when they were last updated and if new data has still to be merged.



<a name="loio6b2d0073a8684ee6a59d6f47d00ec895__section_hvj_5gb_t2c"/>

## Prerequisites

To monitor local tables \(file\), you must have a scoped role that grants you access to the space with the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Data Warehouse Data Integration* \(`-R------`\) - To view data integration task logs in the *Data Integration Monitor* app.

-   *Data Warehouse Data Integration* \(`--U-----`\) - To manually run data integration tasks.

-   *Data Warehouse Data Integration* \(`----E---`\) - To schedule data integration tasks.


The *DW Integrator* role template, for example, grants these privileges. For more information, see [Privileges and Permissions](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/d7350c6823a14733a7a5727bad8371aa.html "A privilege represents a task or an area in SAP Datasphere and can be assigned to a specific role. The actions that can be performed in the area are determined by the permissions assigned to a privilege.") :arrow_upper_right: and [Standard Roles Delivered with SAP Datasphere](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/a50a51d80d5746c9b805a2aacbb7e4ee.html "SAP Datasphere is delivered with several standard roles. A standard role includes a predefined set of privileges and permissions.") :arrow_upper_right:. 



<a name="loio6b2d0073a8684ee6a59d6f47d00ec895__section_jqp_rgb_t2c"/>

## Monitoring Local Tables \(File\)

> ### Note:  
> For additional information on working with data in the object store, see SAP note [3538038](https://me.sap.com/notes/3538038).

Local tables can be used as source data or target data by SAP Datasphere apps. As a Data Integrator you might want to monitor all local tables \(file\) deployed in your space and check how and when data has been last updated and if some data must still be merged.

Go to *Data Integration Monitor* \> *Local Tables \(Files\)*. All local tables \(file\) that have been created in the *Data Builder* are listed. For more information on local tables \(file\), see [Creating a Local Table (File)](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/d21881b121bc4703861be6ead4aea2ab.html "Create a local table (file) to store data in the object store. Load data to your local table (file) via replication flows and transform the data with transformation flows.") :arrow_upper_right:.

The monitor displays the following properties:


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

*Technical Name*or *Business Name*

</td>
<td valign="top">

Displays the technical name or the business name of the table, depending on how you have configured your UI settings in *Your Profile* \> *Settings*.

</td>
</tr>
<tr>
<td valign="top">

*Buffer Merge Status*

</td>
<td valign="top">

Status of the data merge.

Data updates are waiting in the Inbound Buffer until they are merged.

They can have the following status:

-   Running: a merge task is still running.
-   Failed: Last merge run task has failed. You might need to check the log for more details.
-   Merged: All data have been merged with the last merge task.
-   New Data: Data are waiting to be merged.
-   Empty: There is no new data waiting in the inbound buffer.



</td>
</tr>
<tr>
<td valign="top">

*Last updated*

</td>
<td valign="top">

Displays the timestamp when the local table \(file\) was last updated.

</td>
</tr>
<tr>
<td valign="top">

*Last updated by*

</td>
<td valign="top">

Indicates how the local table \(file\) was last updated. For example, name of the task chain that updated it.

</td>
</tr>
<tr>
<td valign="top">

*Buffer Last Updated*

</td>
<td valign="top">

Displays the timestamp when the inbound buffer was last updated by a replication flow or by an SAP BW data push.

</td>
</tr>
<tr>
<td valign="top">

*Buffer Last Updated by*

</td>
<td valign="top">

Indicates the name of the replication flow or the local table \(file\) generated from SAP BW that last updated the inbound buffer.

</td>
</tr>
<tr>
<td valign="top">

*Delta capture*

</td>
<td valign="top">

Indicates if the local table \(file\) allows delta capture. For more information, see [Capturing Delta Changes in Your Local Table](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/154bdffb35814d5481d1f6de143a6b9e.html "Track the changes that will be made later on your local table after you have deployed it.") :arrow_upper_right:.

</td>
</tr>
<tr>
<td valign="top">

*Partitions*

</td>
<td valign="top">

Indicates if the local table \(file\) contains partitions.

</td>
</tr>
<tr>
<td valign="top">

*Number of Active Records*

</td>
<td valign="top">

Displays the number of active records.

</td>
</tr>
<tr>
<td valign="top">

*Active Records File Storage \(MiB\)*

</td>
<td valign="top">

Displays the size used by the active records only.

</td>
</tr>
<tr>
<td valign="top">

*Total Storage \(MiB\)*

</td>
<td valign="top">

Displays the total size of the table. This includes files containing the active records, files from previous versions \(needed for delta processing\), and space required for administrative information. The size of the inbound buffer \(temporary storage of incoming data, usually empty\) is shown separately. The sum of both numbers is the actual size of the table. 

If you compare the size of a similar table that is stored in a space of type SAP HANA Database, you may get different figures: the compression rate to store the data on the object store is different from the compression rate used to store the data in a space of type SAP HANA Database. More important, having many previous versions available for your table, it can consume a lot of storage. This is why it's recommended to do permanent regular data deletion \(Vacuum\). For more information, see [Deleting Local Table (File) Records](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/6ec9b8a89dc64b5cac069cee81399c92.html "Delete records from a local table (File) and free up storage through housekeeping on obsolete or already processed data changes.") :arrow_upper_right:

</td>
</tr>
<tr>
<td valign="top">

*Previous Versions File Storage \(MiB\)*

</td>
<td valign="top">

Displays the size of previous versions of the table. This includes files of previous versions that are required for delta processing. Once the delta has been processed by consuming objects \(for example transformation flows\), previous versions can get removed by running *Delete previous versions \(vacuum\), which are older than the specified number of days* . For more information, see [Deleting Local Table (File) Records](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/6ec9b8a89dc64b5cac069cee81399c92.html "Delete records from a local table (File) and free up storage through housekeeping on obsolete or already processed data changes.") :arrow_upper_right:

</td>
</tr>
<tr>
<td valign="top">

*Buffer File Count*

</td>
<td valign="top">

Displays the number of files that are waiting in the buffer to be merged. You may need to manually trigger a merge task and explore why it’s still not merged if you have automated the merge task.

</td>
</tr>
<tr>
<td valign="top">

*Buffer File Size \(MiB\)*

</td>
<td valign="top">

Displays the estimation of the size of the files waiting for a merge in the buffer. This size will be added to the total size once the merge is complete.

</td>
</tr>
</table>

Click <span class="SAP-icons-V5"></span> \(Details\) to navigate to the details screen of the selected table. From the *Logs* tab, you can see the logs that relate on previous and running actions on your table. From the *Settings* tab you can change the default settings defined for the merge or optimize tasks. For more information see [Merge or Optimize Your Local Tables \(File\)](merge-or-optimize-your-local-tables-file-e533b15.md).

From the *Schedules* tab, you can see the schedules that have already been created to start tasks for your local tables \(files\). You can also create new schedules, or edit, or delete existing schedules.

> ### Note:  
> You can create several schedules to delete data, but only one for a merge or an optimize tasks. For more information on how to create schedule, see [Scheduling Data Integration Tasks](scheduling-data-integration-tasks-7fa0762.md).

