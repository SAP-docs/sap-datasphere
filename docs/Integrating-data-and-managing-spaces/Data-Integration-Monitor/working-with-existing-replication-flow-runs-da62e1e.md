<!-- loioda62e1ee746448e8bc043e1be4377cbe -->

# Working With Existing Replication Flow Runs

You can pause a replication flow run and resume it at a later point in time, or you can stop it completely.

> ### Tip:  
> This text explains the options related to replication flow **runs** \(in the context of monitoring\). For information about how to make changes to an existing replication flow in the *Data Builder*, see [Modify a Replication Flow](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/a24c71f3ba7548909534d4cb52cefbfc.html "Whether and how you can change the settings for a replication flow depends on several factors.") :arrow_upper_right:.

This topic contains the following sections:

-   [Statuses for Replication Flow Runs](working-with-existing-replication-flow-runs-da62e1e.md#loioda62e1ee746448e8bc043e1be4377cbe__section_ReplFlow_RunStatuses) 
-   [Scheduling a Replication Flow](working-with-existing-replication-flow-runs-da62e1e.md#loioda62e1ee746448e8bc043e1be4377cbe__section_ReplFlow_Scheduling) 
-   [Pausing and Resuming a Replication Flow Run](working-with-existing-replication-flow-runs-da62e1e.md#loioda62e1ee746448e8bc043e1be4377cbe__section_ReplFlow_Pausing) 
-   [Monitoring Premium Outbound Volume](working-with-existing-replication-flow-runs-da62e1e.md#loioda62e1ee746448e8bc043e1be4377cbe__section_ReplFlow_POI) 
-   [Stopping a Replication Flow Run](working-with-existing-replication-flow-runs-da62e1e.md#loioda62e1ee746448e8bc043e1be4377cbe__section_ReplFlow_Stopping) 
-   [Space Deletion](working-with-existing-replication-flow-runs-da62e1e.md#loioda62e1ee746448e8bc043e1be4377cbe__section_ReplFlow_SpaceDeletion) 
-   [Adding or Removing Replication Objects](working-with-existing-replication-flow-runs-da62e1e.md#loioda62e1ee746448e8bc043e1be4377cbe__section_ReplFlow_RemovingObjects) 
-   [Changing the Delta Interval for a Replication Flow](working-with-existing-replication-flow-runs-da62e1e.md#loioda62e1ee746448e8bc043e1be4377cbe__section_ReplFlow_ChangeDeltaInterval) 



<a name="loioda62e1ee746448e8bc043e1be4377cbe__section_ReplFlow_RunStatuses"/>

## Statuses for Replication Flow Runs

On the left of the monitoring screen, you find the aggregated status information for your replication flow. If the status for one or more objects in a run differs from the overall status, this is indicated by an additional status value in brackets.

As long as the status is *Running* or *Active*, you cannot start another run for the same replication flow.



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



<a name="loioda62e1ee746448e8bc043e1be4377cbe__section_ReplFlow_POI"/>

## Monitoring Premium Outbound Volume

When you open the *Flows* monitor for a replcation flow with premium outbound integration, a value called *Used Premium Outbound Data Volume* is shown in the overview panel on the left. This is the total volume for all replication flow runs with premium outbound integration \(replication to a non-SAP target\) in this tenant during the last 360 days.

> ### Note:  
> -   The value may change significantly from one day to the other, for example when you run an initial load for a replication flow, or when an initial load drops out of the statistics because it happened more than 360 days ago.
> 
> -   The retention period has been increased from 90 days to 360 days starting as of July 11, 2024, so depending on when you access this feature you may see the data for less than 360 days.

The value is updated once per hour.



<a name="loioda62e1ee746448e8bc043e1be4377cbe__section_ReplFlow_Stopping"/>

## Stopping a Replication Flow Run

If you do so, the flow run is stopped permanently in SAP Datasphere as well as in the source. You can still run it again, but it will then start from scratch \(rather than from where it left off when you stopped it\). If you stop a replication flow run because you don't need it anymore, you should also delete it so that it does not clutter your system. In addition, in the run log of the stopped replication flows, you can download the details information. For more information, see [Delete a Replication Flow](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/bdd81ec3fb144bdab7d3a7dc25947efe.html "You can delete a replication flow if you do not need it anymore and thus free up capacity.") :arrow_upper_right:.



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



<a name="loioda62e1ee746448e8bc043e1be4377cbe__section_ReplFlow_ChangeDeltaInterval"/>

## Changing the Delta Interval for a Replication Flow

This can be done in the *Data Builder*, see [Modify a Replication Flow](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/a24c71f3ba7548909534d4cb52cefbfc.html "Whether and how you can change the settings for a replication flow depends on several factors.") :arrow_upper_right:.

