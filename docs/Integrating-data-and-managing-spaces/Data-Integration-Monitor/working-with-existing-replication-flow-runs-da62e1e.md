<!-- loioda62e1ee746448e8bc043e1be4377cbe -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Working With Existing Replication Flow Runs

You can pause a replication flow run and resume it later, or stop it completely when it's no longer needed. You can also schedule, monitor premium outbound volume, and configure email notifications for replication flow failures. For more information on how to make changes to an existing replication flow in the *Data Builder*, see [Modify a Replication Flow](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/a24c71f3ba7548909534d4cb52cefbfc.html "Whether and how you can change the settings for a replication flow depends on several factors.") :arrow_upper_right:.



<a name="loioda62e1ee746448e8bc043e1be4377cbe__section_ReplFlow_Scheduling"/>

## Scheduling a Replication Flow

You can create a schedule for your replication flow and include your replication flow in a task chain if all objects in it have load type *Initial Only*.

To create a schedule for your replication flow, select the relevant flow and click *Schedule* \> *Create Schedule*.

For more information, see [Schedule a Data Integration Task \(Simple Schedule\)](schedule-a-data-integration-task-simple-schedule-7c11059.md) and [Creating a Task Chain](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/d1afbc2b9ee84d44a00b0b777ac243e1.html "Group multiple tasks into a task chain and run them manually once, or periodically, through a schedule.") :arrow_upper_right:.



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

If you do so, the flow run is stopped permanently in SAP Datasphere as well as in the source. You can still run it again, but it will then start from scratch \(rather than from where it left off when you stopped it\). If you stop a replication flow run because you don't need it anymore, you should also delete it so that it does not clutter your system. In addition, in the run log of the stopped replication flows, you can download the details information. For more information, see [Delete a Replication Flow](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/bdd81ec3fb144bdab7d3a7dc25947efe.html "You can delete a replication flow if you do not need it anymore and thus free up capacity.") :arrow_upper_right:.

To stop a replication flow run:

1.  Go to the *Data Integration* monitor.
2.  Select the relevant space.
3.  Navigate to the *Flows* monitor \(all flows created in the *Data Builder* are listed\) and select the relevant replication flow.
4.  Navigate to its details screen by clicking .<span class="SAP-icons-V5"></span> \(Details\)
5.  Click *Run* \> *Stop Run*.



<a name="loioda62e1ee746448e8bc043e1be4377cbe__section_ReplFlow_SpaceDeletion"/>

## Handling With Space Deletion

If you have replication flows in a space that is about to be deleted, make sure to stop your replication flows before space deletion starts. This helps to avoid issues during space deletion and makes it possible for you to start the replication flows again if the space gets restored at a later point in time.

When a space gets permanently deleted, all replication flows in it are deleted as well.

For more information about space deletion, see [Delete Your Space](../delete-your-space-3eb19b9.md).



<a name="loioda62e1ee746448e8bc043e1be4377cbe__section_ReplFlow_RemovingObjects"/>

## Adding or Removing Replication Objects

This can be done in the *Data Builder*, see [Modify a Replication Flow](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/a24c71f3ba7548909534d4cb52cefbfc.html "Whether and how you can change the settings for a replication flow depends on several factors.") :arrow_upper_right:.

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

This can be done in the *Data Builder*, see [Modify a Replication Flow](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/a24c71f3ba7548909534d4cb52cefbfc.html "Whether and how you can change the settings for a replication flow depends on several factors.") :arrow_upper_right:.



<a name="loioda62e1ee746448e8bc043e1be4377cbe__section_npd_zxq_dgc"/>

## Configuring Email Notification for Replication Flow Failure at Object Level

From the details screen of a replication flow run, you can set up email notification to be notified when the replication of an individual object fails in your replication flow:

1.  Go to *Data Integration Monitor* \> *Flows* monitor.
2.  Naviage to the details screen of your replication flow by clicking <span class="FPA-icons-V3"></span> at the end of the row of the relevant replication flow.
3.  Click *Runtime Email Notification* and configure the email. For more information on how to configure the e-mail, see [Configure Email Notification for Replication Flow Failure at Object Level](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/5dc4db23d3894b10aca6ade3c666554d.html "Set up email notifications to stay informed when individual replication objects fail in a running replication flow.") :arrow_upper_right:.



<a name="loioda62e1ee746448e8bc043e1be4377cbe__section_bqp_rm1_2gc"/>

## Editing the Run Settings

From the details screen of a replication flow run, you can change the run settings to adapt the parameters for your need.

> ### Note:  
> You must have the DW Integrator role and the replication flow must be deployed successfully.

1.  Go to *Data Integration Monitor* \> *Flows* monitor.
2.  Naviage to the details screen of your replication flow by clicking <span class="FPA-icons-V3"></span> at the end of the row of the relevant replication flow.
3.  Open the tab **Run Settings** and update as per your need:

    -   Source Thread Limit \(1-160\): It displays the number of replication threads that will be used by your replication flow to load the data from the source. The value that is entered here determines how many partitions can be processed in parallel during an initial data load. Default value is 16.
    -   Target Thread Limit \(1-160\): It displays the number of replication threads that will be used by your replication flow to write data to the target. The value that is entered here determines how many partitions can be processed in parallel during an initial data load to the target. Possible values are integers between 1 and 160, the default is 16.  
    -   Delta Load Frequency: \[only relevant for load type *Initial and Delta* and *Delta Only*\] Define the time interval for replicating changes from the source to the target.

    For more information, see [Configure a Replication Flow](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/3f5ba0c5ae3944c1b7279bb989a2a5b5.html "Define settings and properties for your replication flow and individual replication objects.") :arrow_upper_right:.


