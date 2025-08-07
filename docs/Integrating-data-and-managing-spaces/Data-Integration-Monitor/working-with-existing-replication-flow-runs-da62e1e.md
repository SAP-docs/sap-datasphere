<!-- loioda62e1ee746448e8bc043e1be4377cbe -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Working With Existing Replication Flow Runs

You can pause a replication flow run and resume it at a later point in time, or you can stop it completely.

> ### Tip:  
> This text explains the options related to replication flow **runs** \(in the context of monitoring\). For information about how to make changes to an existing replication flow in the *Data Builder*, see [Modify a Replication Flow](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/a24c71f3ba7548909534d4cb52cefbfc.html "Whether and how you can change the settings for a replication flow depends on several factors.") :arrow_upper_right:.



<a name="loioda62e1ee746448e8bc043e1be4377cbe__section_ReplFlow_RunStatuses"/>

## Statuses for Replication Flow Runs

On the left of the monitoring screen, you find the aggregated status information for your replication flow. If the status for one or more objects in a run differs from the overall status, this is indicated by an additional status value in brackets.

As long as the status is *Running* or *Active*, you cannot start another run for the same replication flow.

In addition to the main statuses \(Running, Active, Completed, Paused, Failed\), and the standard substatuses \(see [Understanding Statuses and Substatuses](understanding-statuses-and-substatuses-19cb5bd.md)\), additional substatuses can be combined at the replication flow level or on the object level.



### Combination of Statuses and Substatuses for a Replication Flow Running With Load Type: Initial Only


<table>
<tr>
<th valign="top">

Statuses \(Substatuses\)

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Running \(Failed / Paused / Retrying Objects\)

</td>
<td valign="top">

The data is being loaded, but one or more objects have errors, and the user has paused one or more objects. Furthermore, one or more objects could not be loaded, and a new attempt is planned.

</td>
</tr>
<tr>
<td valign="top">

Running \(Failed / Paused Objects\)

</td>
<td valign="top">

The data is being loaded, but one or more objects have errors, and the user has paused one or more objects.

</td>
</tr>
<tr>
<td valign="top">

Running \(Failed objects\)

</td>
<td valign="top">

The data is being loaded, but one or more objects have errors.

</td>
</tr>
<tr>
<td valign="top">

Running \(Paused / Retrying Objects\)

</td>
<td valign="top">

The data is being loaded, but the user has paused one or more objects, or one or more objects could not be loaded \(error or data not ready\). A new attempt is planned.

</td>
</tr>
<tr>
<td valign="top">

Running \(Paused Objects\)

</td>
<td valign="top">

The data is being loaded, but the user has paused one or more objects.

</td>
</tr>
<tr>
<td valign="top">

Running \(Retrying Objects\)

</td>
<td valign="top">

The data is being loaded, but one or more objects could not be loaded. A new attempt is planned.

</td>
</tr>
</table>



### Combination of Statuses and Substatuses for a Replication Flow Running with Load Type: Initial and Delta or Delta Only


<table>
<tr>
<th valign="top">

Statuses \(Substatuses\)

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Active \(Failed Objects\)

</td>
<td valign="top">

The data will be loaded according to the schedule \(delta load interval\), but one or more objects have errors.

</td>
</tr>
<tr>
<td valign="top">

Active \(Failed / Paused / Retrying Objects\)

</td>
<td valign="top">

The data will be loaded according to the schedule \(delta load interval\), but one or more objects have errors, and a user has paused one or more objects. Furthermore, one or more objects could not be loaded. A new attempt is planned.

</td>
</tr>
<tr>
<td valign="top">

Active \(Failed / Paused Objects\)

</td>
<td valign="top">

The data will be loaded according to the schedule \(delta load interval\), but one or more objects have errors, and a user has paused one or more objects.

</td>
</tr>
<tr>
<td valign="top">

Active \(Paused / Retrying Objects\)

</td>
<td valign="top">

The data will be loaded according to the schedule \(delta load interval\), but one or more objects have been paused by a user, or one or more objects could not be loaded \(error or data not ready yet\). A new attempt is planned.

</td>
</tr>
<tr>
<td valign="top">

Active \(Paused Objects\)

</td>
<td valign="top">

The data will be loaded according to the schedule \(delta load interval\), but a user has paused one or more objects.

</td>
</tr>
<tr>
<td valign="top">

Active \(Retrying Objects\)

</td>
<td valign="top">

The data will be loaded according to the schedule \(delta load interval\), but one or more objects could not be loaded. A new attempt is planned.

</td>
</tr>
</table>



### Statuses at Object Level


<table>
<tr>
<th valign="top">

Statuses

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Created

</td>
<td valign="top">

The replication task for the object is created in the runtime, but has not started yet.

</td>
</tr>
<tr>
<td valign="top">

Completed

</td>
<td valign="top">

The replication task for the object has successfully transferred the data to the target

</td>
</tr>
<tr>
<td valign="top">

Failed

</td>
<td valign="top">

The replication task for the object has failed during the transfer of data

</td>
</tr>
<tr>
<td valign="top">

Retrying

</td>
<td valign="top">

The replication task for the object is in retrying state, due to temporary errors, or waiting for delta data from the source system

</td>
</tr>
<tr>
<td valign="top">

Deleting

</td>
<td valign="top">

The replication task for the object is getting cleaned up or removed by the runtime.

</td>
</tr>
<tr>
<td valign="top">

Paused

</td>
<td valign="top">

The replication task for the object has been paused by the user

</td>
</tr>
<tr>
<td valign="top">

Pausing

</td>
<td valign="top">

The replication task for the object is in the process of being paused

</td>
</tr>
<tr>
<td valign="top">

Running, Initial Running, Delta Running

</td>
<td valign="top">

The replication task for the object is currently transferring data to the target object.

</td>
</tr>
<tr>
<td valign="top">

Restarting

</td>
<td valign="top">

The replication task for the object is re-initializing

</td>
</tr>
</table>



<a name="loioda62e1ee746448e8bc043e1be4377cbe__section_ReplFlow_Scheduling"/>

## Scheduling a Replication Flow

You can create a schedule for your replication flow and include your replication flow in a task chain if all objects in it have load type *Initial Only*. For more information, see [Schedule a Data Integration Task \(Simple Schedule\)](schedule-a-data-integration-task-simple-schedule-7c11059.md) and [Creating a Task Chain](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/d1afbc2b9ee84d44a00b0b777ac243e1.html "Group multiple tasks into a task chain and run them manually once, or periodically, through a schedule.") :arrow_upper_right:.



<a name="loioda62e1ee746448e8bc043e1be4377cbe__section_ReplFlow_Pausing"/>

## Pausing and Resuming a Replication Flow Run

You may want to pause a replication flow run, for example, while a system update is running.

> ### Caution:  
> You must always stop or pause a running replication flow before a source system downtime.

When you do so, the flow is stopped in SAP Datasphere, but not in the source. Consequently, the system still keeps track of changes in the source, but does not copy them to the target.

> ### Note:  
> If you have many data changes in your source, and if you pause the replication flow for a longer time \(such as several hours\), the logging tables can become quite big.

To pause a replication flow that has a **schedule**, you need to pause the schedule. \(Pausing the replication flow run itself is not possible in this case.\)

When you resume the flow, the system replicates all source data changes that happened while the replication flow was paused, which means that the first replication flow run after a pause can take considerably longer than usual.

To pause, resume or restart a replication flow:

1.  Go to the *Data Integration* monitor,
2.  Select the relevant space
3.  Navigate to the *Flows* monitor. All flows that have been created in the *Data Builder* are listed.
4.  Select the relevant replication flow
5.  Navigate to its details screen by clicking <span class="SAP-icons-V5"></span> \(Details\)
6.  Click *Run* \> *Pause Run* or *Run* \> *Resume Run* depending the action you want to apply.



<a name="loioda62e1ee746448e8bc043e1be4377cbe__section_ReplFlow_POI"/>

## Monitoring Premium Outbound Volume

When you open the *Flows* monitor for a replication flow with premium outbound integration, a value called *Used Premium Outbound Data Volume* is shown in the overview panel on the left. This is the total volume for all replication flow runs with premium outbound integration \(replication to a non-SAP target\) in this tenant during the last 360 days.

> ### Note:  
> -   The value may change significantly from one day to the other, for example when you run an initial load for a replication flow, or when an initial load drops out of the statistics because it happened more than 360 days ago.
> 
> -   The retention period has been increased from 90 days to 360 days starting as of July 11, 2024, so depending on when you access this feature you may see the data for less than 360 days.

The value is updated once per hour.



<a name="loioda62e1ee746448e8bc043e1be4377cbe__section_ReplFlow_Stopping"/>

## Stopping a Replication Flow Run

If you do so, the flow run is stopped permanently in SAP Datasphere as well as in the source. You can still run it again, but it will then start from scratch \(rather than from where it left off when you stopped it\). If you stop a replication flow run because you don't need it anymore, you should also delete it so that it does not clutter your system. In addition, in the run log of the stopped replication flows, you can download the details information. For more information, see [Delete a Replication Flow](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/bdd81ec3fb144bdab7d3a7dc25947efe.html "You can delete a replication flow if you do not need it anymore and thus free up capacity.") :arrow_upper_right:.

To stop a replication flow run:

1.  Go to the *Data Integration* monitor,
2.  Select the relevant space
3.  Navigate to the *Flows* monitor \(all flows created in the *Data Builder* are listed\) and select the relevant replication flow
4.  Navigate to its details screen by clicking <span class="SAP-icons-V5"></span> \(Details\)
5.  Click *Run* \> *Stop Run*.



<a name="loioda62e1ee746448e8bc043e1be4377cbe__section_ReplFlow_SpaceDeletion"/>

## Space Deletion

If you have replication flows in a space that is about to be deleted, make sure to stop your replication flows before space deletion starts. This helps to avoid issues during space deletion and makes it possible for you to start the replication flows again if the space gets restored at a later point in time.

When a space gets permanently deleted, all replication flows in it are deleted as well.

For more information about space deletion, see [Delete Your Space](../delete-your-space-3eb19b9.md).



<a name="loioda62e1ee746448e8bc043e1be4377cbe__section_ReplFlow_RemovingObjects"/>

## Adding or Removing Replication Objects

This can be done in the *Data Builder*, see [Modify a Replication Flow](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/a24c71f3ba7548909534d4cb52cefbfc.html "Whether and how you can change the settings for a replication flow depends on several factors.") :arrow_upper_right:.

> ### Note:  
> Adding or removing objects without stopping the replication flow first is only possible for replication flows in status *Active*.



<a name="loioda62e1ee746448e8bc043e1be4377cbe__section_bvl_xyg_1fc"/>

## Pausing, Resuming or Restarting a Replication Flow Run Object

To pause, resume or restart a replication flow:

1.  Go to the *Data Integration* monitor,
2.  Select the relevant space
3.  Navigate to the *Flows* monitor. All flows that have been created in the *Data Builder* are listed.
4.  Select the relevant replication flow
5.  Navigate to its details screen by clicking <span class="SAP-icons-V5"></span> \(Details\)
6.  In the *Object* list, select the relevant object and click *Object* \> *Pause Object* or *Object* \> *Resume Object* or *Object* \> *Restart Object* depending the action you want to perform.

> ### Note:  
> When you pause an object flow run, the flow is stopped in SAP Datasphere for this object only, but not in the source. Consequently, the system still keeps track of changes in the source, but does not copy them to the target. The other objects contain in the replication flow are not paused and are being replicated.
> 
> When you resume the object flow run, the system replicates all source data changes that happened while the object flow run was paused.
> 
> When you restart an object flow run, the replication restarts from the beginning.



<a name="loioda62e1ee746448e8bc043e1be4377cbe__section_ReplFlow_ChangeDeltaInterval"/>

## Changing the Delta Interval for a Replication Flow

This can be done in the *Data Builder*, see [Modify a Replication Flow](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/a24c71f3ba7548909534d4cb52cefbfc.html "Whether and how you can change the settings for a replication flow depends on several factors.") :arrow_upper_right:.

