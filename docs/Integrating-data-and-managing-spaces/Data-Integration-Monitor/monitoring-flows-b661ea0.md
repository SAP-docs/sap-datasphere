<!-- loiob661ea0766a24c7d839df950330a89fd -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Monitoring Flows

In the *Flows* monitor, you can find all the deployed flows per space.



<a name="loiob661ea0766a24c7d839df950330a89fd__prereq_sj1_njx_cpb"/>

## Prerequisites

To run and schedule flows in the *Flows* monitor, you must have a scoped role that grants you access to a space with the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Data Warehouse Data Integration* \(`-RU-E---`\) - To run and schedule a flow. The *DW Integrator* role template, for example, grants this privilege.

For more information, see [Privileges and Permissions](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/d7350c6823a14733a7a5727bad8371aa.html "A privilege represents a task or an area in SAP Datasphere and can be assigned to a specific role. The actions that can be performed in the area are determined by the permissions assigned to a privilege.") :arrow_upper_right: and [Standard Roles Delivered with SAP Datasphere](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/a50a51d80d5746c9b805a2aacbb7e4ee.html "SAP Datasphere is delivered with several standard roles. A standard role includes a predefined set of privileges and permissions.") :arrow_upper_right:. 



<a name="loiob661ea0766a24c7d839df950330a89fd__context_ev4_2dg_k4b"/>

## Context

In the *Flows* monitor, you can find all the deployed flows \(data flows, replication flows, and transformation flows\) per space. Here, you can run the deployed flows, and you can view and monitor the execution details of the flows.

> ### Note:  
> For optimal performance, it is recommended that you consider staggering the scheduled run time of tasks such as data flows or task chains that may contain these tasks. Make sure to distribute your work such as scheduling and running tasks. There isn't a specific numerical limit on how many tasks can be scheduled. There could be a resource distribution issue caused by too many tasks running at once. Check your system monitor to look at your workload distribution. For more information see, [Monitoring SAP Datasphere](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/28910cded17a42a0bf16225309cb8bf6.html "Users with an administrator role have access to various monitoring logs and views and can, if necessary, create database analysis users to help troubleshoot issues.") :arrow_upper_right: or [Persisted Views and Memory Consumption](persisted-views-and-memory-consumption-e3d0495.md).

For more information and points to consider when using replication flows, see also SAP Note [3297105](https://me.sap.com/notes/3297105).



<a name="loiob661ea0766a24c7d839df950330a89fd__steps_nfv_52s_knb"/>

## Procedure

1.  In the SAP Datasphere, navigate to *Data Integration Monitor* \> *Flows*.

    You can find all the deployed flows per space. You can run the deployed flows under *Run*, and you can view and monitor the execution details of the flows. For some flows, you can create, edit, delete, pause or resume a schedule, or assign a schedule to your name under *Schedule*, and you can select several data flows to group the scheduling actions. For more information about scheduling, see [Schedule a Data Integration Task \(Simple Schedule\)](schedule-a-data-integration-task-simple-schedule-7c11059.md).

    The list of deployed flows shows the following information:


    <table>
    <tr>
    <th valign="top">

    Column
    
    </th>
    <th valign="top">

    Information
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Technical Name* or *Business Name*
    
    </td>
    <td valign="top">
    
    Name of the flow. Technical or Business Name is displayed, depending on how you have configured your UI settings in *Your Profile* \> *Settings*
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Status*
    
    </td>
    <td valign="top">
    
    Indicates the status of the last run of the flow:

    -   *Running*: The flow is currently running.
    -   *Active*: \[Replication Flow only\] A replication flow that contains objects with load type *Initial and Delta* does not have an end date. Once started, it remains in status Active until it is stopped or paused or an issue occurs.
    -   *Completed*: The flow is completed successfully.
    -   *Failed*: Something goes wrong during the flow run and it could not be completed. Go to the details screen of your flow and check the logs to identify to issue.
    -   *Stopped*: The flow has been stopped by a user.

    All these statuses can be combined with a sub-status. For more information on sub-statuses, see [Understanding Statuses and Substatuses](understanding-statuses-and-substatuses-19cb5bd.md).

    > ### Note:  
    > If the status of a flow is empty, it means that the flow has not run yet. The status is updated every 10 minutes for replication flow \(except when it is run via a task chain: It updates every 2 minutes\), and every 1 minute for a transformation flow or a data flow. To get an immediate updated status, navigate to the run details page.

    For more information on specifics for replication flow runs, see [Working With Existing Replication Flow Runs](working-with-existing-replication-flow-runs-da62e1e.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Type*
    
    </td>
    <td valign="top">
    
    Indicates the type of flow: data flow, transformation flow or replication flow.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Frequency*
    
    </td>
    <td valign="top">
    
    Indicates if a schedule is defined for a data flow or a transformation flow. :

    -   *Scheduled*: A schedule task is defined for this flow. If you click on *Scheduled*, you get detailed information on the schedule. You can update the schedule options at any time from *Schedule* \> *Edit Schedule*, or delete the schedule from *Schedule* \> *Delete Schedule*
    -   *Paused*: A schedule task is defined for this flow but is currently paused. To resume the task, select *Schedule* \> *Resume*


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Duration*
    
    </td>
    <td valign="top">
    
    Provides information on the total execution time of the last flow run.

    > ### Note:  
    > The initialization time for executing a flow takes an average of 20 seconds even with smaller data loads, causing longer runtime for the flow. It is calculated using the task start time and task end time. For replication flow, it does not depend on the initial load duration.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Last Run Start*
    
    </td>
    <td valign="top">
    
    Provides information on when the last run of the flow started.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Last Run End*
    
    </td>
    <td valign="top">
    
    Provides information on when the last run of the flow ended.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Next Run*
    
    </td>
    <td valign="top">
    
    If a schedule is set for a flow, you can see here by when the next run is scheduled.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Schedule Owner* 
    
    </td>
    <td valign="top">
    
    Displays the name of the current schedule owners when a schedule is defined for a flow.
    
    </td>
    </tr>
    </table>
    
    You can personalize the columns you want to display clicking on :gear:

    > ### Note:  
    > Parallel execution is not supported: You can't run two identical flows at the same time. You need to wait until the first run is completed before you can launch another one. Otherwise your second run gets the status *Failed \(Run Already in Progress\)*.

2.  To see the run details of a flow, click <span class="SAP-icons-V5"></span> \(Details\) for the relevant flow.

    The run details page opens. It shows the runs of the flow in the left panel and their corresponding messages in the right panel. Here, you can use the *Stop Run* \(for *Replication Flow* and *Data Flow*\) or *Cancel Run* \(for *Transformation Flow*\) buttons to stop a run that is currently running. The buttons are available until the run ends.

    > ### Note:  
    > For *Data flow*, if the *Stop Run* does not work properly, or if the flow seems to be blocked at the current step, you can click on *Set to failed*.

    For transformation flows, the following tabs are available:

    -   *Logs* shows activities related to previous and running actions on your flow run. You can see a run *Start* date and time, *Activity*, and *Status*. Click \> to show the run details.
    -   *Delta Capture Settings* tracks the data that has been transferred when running a transformation flow that loads delta changes to a target table. You can see the source table technical name and watermark. Click *Reset Watermark* to transfer all data to the target table the next time the transformation flow runs \(using the load type Initial and Delta\). For more information, see [Watermarks](watermarks-890897f.md).
    -   *Settings* shows which options are available for *Run Mode*:
        -   Transformation flow: *Performance-Optimized \(Recommended\)* or *Memory-Optimized*.
        -   Transformation flow in a File space:*Apache Spark Settings* can be set to *Use Space Default* settings or *Define New Settings for this Flow*.


3.  Select a flow run in the left panel to view its details. The run details contain messages for all runs and metrics for the current run.

    -   Messages:

        For failed runs, click *View Details* besides the error message to see more information about the error.

    -   Metrics:

        For successful runs, the metrics provide the record count for the source and target tables used in the flow.

        > ### Note:  
        > -   It takes a while to load the metrics once the flow run is completed.
        > -   If the flow run has been optimized for better performance, no record count information is shown.
        > -   For historical runs of a flow, metrics can’t be retrieved.
        > -   \[Replication Flow\]: Additional information is available under *View Details* in the replication flow metrics or in the replication flow object metrics.

        > ### Restriction:  
        > For data flows, the logs messages and metrics are only displayed in English.

        For more information, see [Metrics for Transformation Flows](metrics-for-transformation-flows-b42fa5b.md).


4.  If your flow failed, you can use the following tools from the details page of the flow run to analyze and solve your issue:

    -   \[Data Flow and Replication Flow\] You can analyze the errors that have occurred during your flow runs, downloading the run details as a JSON file you can provide to the SAP Support for troubleshooting: Click <span class="SAP-icons-V5"></span> Download Run Details.
    -   \[Data Flow\] You can also perform a complete health analysis and generate detailed logs if you choose *Run* \> *Start Run with Checkup*. Send this health analysis log to your support team to get help in case of issues.
    -   \[Transformation Flow\]: You can run your transformation flow with Support Settings. For more information, see [Explore Transformation Flows](explore-transformation-flows-7588192.md).

5.  To view and modify a flow, click <span class="SAP-icons-V5"></span> Open in Data Builder.


