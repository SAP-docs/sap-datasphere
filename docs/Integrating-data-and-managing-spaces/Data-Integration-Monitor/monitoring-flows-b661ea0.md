<!-- loiob661ea0766a24c7d839df950330a89fd -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Monitoring Flows

In the Flow Monitor, you can find all the deployed flows per space.



<a name="loiob661ea0766a24c7d839df950330a89fd__prereq_sj1_njx_cpb"/>

## Prerequisites

-   To use the Flow Monitor, you need the `DW Integrator` role along with the `DW Viewer` or the `DW Modeler` role.

-   To run the flows, you need the `DWC_DATAINTEGRATION` privilege and the **Update** permission. For more information, see [Managing Roles and Privileges](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/3740dacbc2794f33bb5d8d42216cc3bc.html "Assigning roles to your users maintains access rights and secures your information in SAP Datasphere.") :arrow_upper_right:.

-   To schedule the flows, you need the `DWC_DATAINTEGRATION` privilege and the **Execute** permission. For more information, see [Managing Roles and Privileges](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/3740dacbc2794f33bb5d8d42216cc3bc.html "Assigning roles to your users maintains access rights and secures your information in SAP Datasphere.") :arrow_upper_right:.




<a name="loiob661ea0766a24c7d839df950330a89fd__context_ev4_2dg_k4b"/>

## Context

In the Flow Monitor, you can find all the deployed flows \(data flows and replication flows\) per space. Here, you can run the deployed flows, and you can view and monitor the execution details of the flows.

> ### Note:  
> For optimal performance, it is recommended that you consider staggering the scheduled run time of tasks such as data flows and task chains that may contain these tasks. There is a limit on how many tasks can be started at the same time. If you come close to this limit, scheduled task runs may be delayed and, if you go beyond the limit, some scheduled task runs might even be skipped.

For more information and points to consider when using replication flows, see also [SAP Note 3297105](https://launchpad.support.sap.com/#/notes/SAP Note 3297105).



<a name="loiob661ea0766a24c7d839df950330a89fd__steps_nfv_52s_knb"/>

## Procedure

1.  In the SAP Datasphere, navigate to *Data Integration Monitor* \> *Flow Monitor*.

    You can find all the deployed flows per space. You can run the deployed flows under *Run*, and you can view and monitor the execution details of the flows. You can also create, edit or delete a schedule for a data flow under *Schedule*. For more information, see [Schedule a Data Integration Task](schedule-a-data-integration-task-7c11059.md).

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
    
    *Name*


    
    </td>
    <td valign="top">
    
    Name of the flow


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Last Run Status*


    
    </td>
    <td valign="top">
    
    Indicates the status of the last run of the flow. For more information on specifics for replication flow runs, see [Statuses for Replication Flow Runs](statuses-for-replication-flow-runs-e8b2ff9.md).

    > ### Note:  
    > If the status of a flow is empty, it means that the data flow has not run yet.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Frequency*


    
    </td>
    <td valign="top">
    
    Indicates if a schedule is defined for a data flow:

    -   *Scheduled*: A schedule task is defined for this data flow. If you click on *Scheduled*, you get detailed information on the schedule. You can update the schedule options at any time from *Schedule* \> *Edit Schedule*, or delete the schedule from *Schedule* \> *Delete Schedule*


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Duration*


    
    </td>
    <td valign="top">
    
    Provides information on the total execution time of the last run.

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
    
    If a schedule is set for a data flow, you can see here by when the next run is scheduled.


    
    </td>
    </tr>
    </table>
    
    > ### Note:  
    > Parallel execution is not supported: You can't run two identical flows at the same time. You need to wait until the first run is completed before you can launch another one. Otherwise your second run gets the status *Failed*.

2.  To see the run details of a flow, click <span class="SAP-icons"></span> \(Details\) for the relevant flow.

    The run details page opens. It shows the runs of the flow in the left panel and their corresponding messages in the right panel. Here, you can use the *Stop Run* button to stop a run that is currently running. This button is available until the run ends.

3.  Select a flow run in the left panel to view its details. The run details contain messages for all runs and metrics for the current run.

    -   Messages:

        For failed runs, click *View Details* besides the error message to see more information about the error.

    -   Metrics:

        For successful runs, the metrics provide the record count for source and target tables used in the flow.

        > ### Note:  
        > -   It takes a while to load the metrics once the flow run is completed.
        > -   If the flow run has been optimized for better performance, no record count information is shown.
        > -   For historical runs of a flow, metrics can’t be retrieved.


4.  You can analyze errors that have occurred during your data flow runs with the *Checkup* function that creates a detailed log. Diagnostic information can also be downloaded for a flow: Click <span class="SAP-icons"></span> Download Run Details and save the JSON file to provide it to the SAP Support for troubleshooting.

5.  To view and modify a flow, click <span class="SAP-icons"></span> Open in Editor.


