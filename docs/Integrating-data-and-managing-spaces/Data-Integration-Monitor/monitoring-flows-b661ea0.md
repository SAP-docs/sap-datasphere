<!-- loiob661ea0766a24c7d839df950330a89fd -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Monitoring Flows

In the *Flows* monitor, you can find all the deployed flows per space.



<a name="loiob661ea0766a24c7d839df950330a89fd__prereq_sj1_njx_cpb"/>

## Prerequisites

-   To use the *Flows* monitor, you need the `DW Integrator` role along with the `DW Viewer` or the `DW Modeler` role.

-   To run the flows, you need the `DWC_DATAINTEGRATION` privilege and the **Update** permission. For more information, see [Managing Roles and Privileges](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/3740dacbc2794f33bb5d8d42216cc3bc.html "Assigning roles to your users maintains access rights and secures your information in SAP Datasphere.") :arrow_upper_right:.

-   To schedule the flows, you need the `DWC_DATAINTEGRATION` privilege and the **Execute** permission. For more information, see [Managing Roles and Privileges](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/3740dacbc2794f33bb5d8d42216cc3bc.html "Assigning roles to your users maintains access rights and secures your information in SAP Datasphere.") :arrow_upper_right:.




<a name="loiob661ea0766a24c7d839df950330a89fd__context_ev4_2dg_k4b"/>

## Context

In the *Flows* monitor, you can find all the deployed flows \(data flows, replication flows and transformation flows\) per space. Here, you can run the deployed flows, and you can view and monitor the execution details of the flows.

> ### Note:  
> For optimal performance, it is recommended that you consider staggering the scheduled run time of tasks such as data flows and task chains that may contain these tasks. There is a limit on how many tasks can be started at the same time. If you come close to this limit, scheduled task runs may be delayed and, if you go beyond the limit, some scheduled task runs might even be skipped.

For more information and points to consider when using replication flows, see also SAP Note [3297105](https://me.sap.com/notes/3297105).



<a name="loiob661ea0766a24c7d839df950330a89fd__steps_nfv_52s_knb"/>

## Procedure

1.  In the SAP Datasphere, navigate to *Data Integration Monitor* \> *Flows*.

    You can find all the deployed flows per space. You can run the deployed flows under *Run*, and you can view and monitor the execution details of the flows. You can also create, edit, delete, pause or resume a schedule for a data flow, or assign a schedule to your name under *Schedule*. Whenever it's applicable, you can select several data flows to group the scheduling actions. For more information, see [Schedule a Data Integration Task](schedule-a-data-integration-task-7c11059.md).

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

    -   *Running*: the flow is currently running.
    -   *Completed*: the flow is completed successfully.
    -   *Failed*: Something goes wrong during the flow run and it could not be completed. Go to the details screen of your flow and check the logs to identify to issue.

    All these statuses can be combined with a sub-status. For more information on sub-statuses, see [Understanding Statuses and Substatuses](understanding-statuses-and-substatuses-19cb5bd.md).

    > ### Note:  
    > If the status of a flow is empty, it means that the flow has not run yet.

    For more information on specifics for replication flow runs, see [Working With Existing Replication Flow Runs](working-with-existing-replication-flow-runs-da62e1e.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Type*
    
    </td>
    <td valign="top">
    
    Indicates the type of flow: data flow, transformation flow or replications flow.
    
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
    > The initialization time for executing a flow takes an average of 20 seconds even with smaller data loads, causing longer runtime for the flow.


    
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
    > Parallel execution is not supported: You can't run two identical flows at the same time. You need to wait until the first run is completed before you can launch another one. Otherwise your second run gets the status *Failed*.

2.  To see the run details of a flow, click <span class="SAP-icons"></span> \(Details\) for the relevant flow.

    The run details page opens. It shows the runs of the flow in the left panel and their corresponding messages in the right panel. Here, you can use the *Stop Run* \(for *Replication Flow*\), *Cancel Run* \(for *Transformation Flow*\) or *Set to failed* \(for *Data Flow\)* buttons to stop a run that is currently running. The buttons are available until the run ends.

3.  Select a flow run in the left panel to view its details. The run details contain messages for all runs and metrics for the current run.

    -   Messages:

        For failed runs, click *View Details* besides the error message to see more information about the error.

    -   Metrics:

        For successful runs, the metrics provide the record count for source and target tables used in the flow.

        > ### Note:  
        > -   It takes a while to load the metrics once the flow run is completed.
        > -   If the flow run has been optimized for better performance, no record count information is shown.
        > -   For historical runs of a flow, metrics can’t be retrieved.


4.  You can analyze errors that have occurred during your data flow runs downloading the run details as a JSON file you can provide to the SAP Support for troubleshooting: Click <span class="SAP-icons"></span> Download Run Details

5.  You can also perform a complete health analysis and generate detailed logs if you choose *Run* \> *Start Run with Checkup*

6.  To view and modify a flow, click <span class="SAP-icons"></span> Open in Data Builder.


