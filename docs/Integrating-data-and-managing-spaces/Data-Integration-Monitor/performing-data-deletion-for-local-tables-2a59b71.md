<!-- loio2a59b7142e1b4d478b0bf4063084261e -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Performing Data Deletion for Local Tables

Delete records for local tables, on-demand, using filter conditions or using a schedule.

Table records can consume a lot of memory and you might need to do a cleanup of unused records. Especially for tables where delta capture is enabled, as when you delete records, they are not physically deleted but marked as deleted to allow other apps to propagate the changes to the different objects that consume it in delta mode. For more information, see [Capturing Delta Changes in Your Local Table](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/154bdffb35814d5481d1f6de143a6b9e.html "Track the changes that will be made later on your local table after you have deployed it.") :arrow_upper_right:. As these records continue to consume memory until they are physically deleted from SAP Datasphere, you must clean up your data regularly.

From the *Data Integration Monitor* \(<span class="FPA-icons-V3"></span> \), go to the *Local Tables* monitor. Navigate to the details screen of the local table you want to perform the data deletion.

The header of the screen displays metrics on the local table:


<table>
<tr>
<th valign="top">

Metric

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Used Disk* 

</td>
<td valign="top">

Displays the size used by the local table if it is stored on the disk.

</td>
</tr>
<tr>
<td valign="top">

*Used In-Memory \(MiB\)* 

</td>
<td valign="top">

Displays the size used by the table, if it is stored in-memory. For more information, see [Accelerate Table Data Access with In-Memory Storage](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/407d1dff76a842699ea08c17eb8748dd.html "By default, table data is stored on disk. You can improve performance by enabling in-memory storage.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

*Number of Records* 

</td>
<td valign="top">

Displays the current number of records in the table.

</td>
</tr>
<tr>
<td valign="top">

*Delta Capture* 

</td>
<td valign="top">

Indicates if the table tracks the changes made on your local table after you have deployed it. For more information, see [Capturing Delta Changes in Your Local Table](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/154bdffb35814d5481d1f6de143a6b9e.html "Track the changes that will be made later on your local table after you have deployed it.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

*In-Memory Storage* 

</td>
<td valign="top">

Indicates if the table is stored in-memory.

</td>
</tr>
</table>



<a name="loio2a59b7142e1b4d478b0bf4063084261e__section_bqs_k1m_ncc"/>

## The Data Deletion Tab

From the *Data Deletion* tab, you define criteria to delete the records:


<table>
<tr>
<th valign="top">

Type of Deletion

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*All Records* 

</td>
<td valign="top">

You want to delete all records contained in the local table. Note that in case of tables with delta capture enabled, all records will be marked as deleted but will not be deleted physically. For more information, see [Capturing Delta Changes in Your Local Table](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/154bdffb35814d5481d1f6de143a6b9e.html "Track the changes that will be made later on your local table after you have deployed it.") :arrow_upper_right: 

</td>
</tr>
<tr>
<td valign="top">

*Filter* 

</td>
<td valign="top">

You define a filter and based on this filter, the records will be deleted. Note that for tables with delta capture enabled the records will be marked as deleted but will not be physically deleted.

> ### Restriction:  
> SQL based selection criteria are not supported.

> ### Note:  
> Click *Show Preview* to preview records that match the filter criteria and will be deleted. You must have the role *DW Integrator* or *DW Modeler* to preview the data.



</td>
</tr>
<tr>
<td valign="top">

*Record marked as "Deleted"* 

</td>
<td valign="top">

This option will appear only if your table is a delta capture table. With this option, you can physically delete records marked as deleted and that have already been successfully processed by other apps that consume them. You can define a period of deletion. For example, records older than 30 days.

> ### Note:  
> Data deletion preview is not supported for records marked as "deleted", as the data editor does not support the switch between active records and delta capture records.



</td>
</tr>
</table>

In the *Preview* section, in addition to previewing the data to be deleted when supported, you can see 2 additional metrics:


<table>
<tr>
<th valign="top">

Metric

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Number of Deletable records* 

</td>
<td valign="top">

Displays the number of records that will be deleted based on your previous selection.

</td>
</tr>
<tr>
<td valign="top">

*Size of Deletable Records* 

</td>
<td valign="top">

Displays the size of the records that will be deleted based on your previous selection.

</td>
</tr>
</table>

Click *Delete Records* to delete records based on your selection.

> ### Note:  
> Ensure that flows that consume the table are not affected.



<a name="loio2a59b7142e1b4d478b0bf4063084261e__section_gkg_3cm_ncc"/>

## Data Deletion Schedules

From the *Data Deletion Schedules* tab, you can automate data deletion with a schedule.

To create a schedule, click *Create*.

The *Schedule Data Deletion* window opens:

1.  Define the settings of the schedule: Give a business name and a technical name to your schedule, and select the type of deletion you would like to apply.
2.  Define the *Frequency* and *Time Range* for your schedule. For more information, see [Scheduling Data Integration Tasks](scheduling-data-integration-tasks-7fa0762.md).
3.  Click *Next Step*.
4.  Review your settings and click *Create Schedule*.

From this tab, you can also change or delete a schedule, and monitor the existing schedules with the available metrics:


<table>
<tr>
<th valign="top">

Metric

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Type* 

</td>
<td valign="top">

Displays the type of deletion you applied on your table.

</td>
</tr>
<tr>
<td valign="top">

*Name* 

</td>
<td valign="top">

Displays the business name or technical name of the schedule. Technical or Business Name is displayed, depending on how you have configured your UI settings in *Profile* \> *Settings*.

</td>
</tr>
<tr>
<td valign="top">

*Frequency* 

</td>
<td valign="top">

Displays the frequency of the schedule.

> ### Note:  
> *Paused* is displayed in the case the schedule has been paused.



</td>
</tr>
<tr>
<td valign="top">

*Last Run Start* 

</td>
<td valign="top">

Displays when the last scheduled run has started \(date and time\).

</td>
</tr>
<tr>
<td valign="top">

*Last Run End* 

</td>
<td valign="top">

Displays when the last scheduled run has ended \(date and time\).

</td>
</tr>
<tr>
<td valign="top">

*Status* 

</td>
<td valign="top">

Displays the status of your scheduled run.

</td>
</tr>
<tr>
<td valign="top">

*Records \(Last Run\)* 

</td>
<td valign="top">

Number of records deleted with the last scheduled run.

</td>
</tr>
</table>



<a name="loio2a59b7142e1b4d478b0bf4063084261e__section_zxh_hfm_ncc"/>

## Data Deletion Logs

From the *Data Deletion Logs* tab, you can monitor how the deletion task runs:


<table>
<tr>
<th valign="top">

Metric

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Start* 

</td>
<td valign="top">

Displays the date and time when the deletion task started.

</td>
</tr>
<tr>
<td valign="top">

*Duration* 

</td>
<td valign="top">

Displays how long the task ran to delete all records.

</td>
</tr>
<tr>
<td valign="top">

*Object Type* 

</td>
<td valign="top">

Displays the type of object that contains the records to be deleted.

</td>
</tr>
<tr>
<td valign="top">

*Activity* 

</td>
<td valign="top">

Displays what type of activity the task runs.

</td>
</tr>
<tr>
<td valign="top">

*User* 

</td>
<td valign="top">

Displays who initiates the deletion task.

</td>
</tr>
<tr>
<td valign="top">

*Number of records* 

</td>
<td valign="top">

Displays the number of records that have been deleted, or marked for deletion in case of local table with delta capture enabled.

</td>
</tr>
<tr>
<td valign="top">

*Status* 

</td>
<td valign="top">

Displays the status of the deletion task.

</td>
</tr>
</table>

