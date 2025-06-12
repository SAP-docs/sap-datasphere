<!-- loio28910cded17a42a0bf16225309cb8bf6 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Monitoring SAP Datasphere

Users with an administrator role have access to various monitoring logs and views and can, if necessary, create database analysis users to help troubleshoot issues.

This topic contains the following sections:

-   [Monitor Disk and Memory Assignment](monitoring-sap-datasphere-28910cd.md#loio28910cded17a42a0bf16225309cb8bf6__section_irf_214_1cc)
-   [Monitor Tasks](monitoring-sap-datasphere-28910cd.md#loio28910cded17a42a0bf16225309cb8bf6__section_qyl_sc4_ccc)
-   [Monitor Statements](monitoring-sap-datasphere-28910cd.md#loio28910cded17a42a0bf16225309cb8bf6__section_t2q_sc4_ccc)
-   [Monitor Access Control Issues](monitoring-sap-datasphere-28910cd.md#loio28910cded17a42a0bf16225309cb8bf6__section_tt5_sc4_ccc)
-   [Monitor Elastic Compute Nodes](monitoring-sap-datasphere-28910cd.md#loio28910cded17a42a0bf16225309cb8bf6__section_yvw_k24_ccc)
-   [Task Logs Tab](monitoring-sap-datasphere-28910cd.md#loio28910cded17a42a0bf16225309cb8bf6__section_task_tab)
-   [Statement Logs Tab](monitoring-sap-datasphere-28910cd.md#loio28910cded17a42a0bf16225309cb8bf6__section_statement_tab)
-   [Show/Hide, Filter, Sort and Reorder Task and Statement Columns](monitoring-sap-datasphere-28910cd.md#loio28910cded17a42a0bf16225309cb8bf6__section_a4f_vzb_xtb)
-   [Monitor Capacity Units](monitoring-sap-datasphere-28910cd.md#loio28910cded17a42a0bf16225309cb8bf6__section_i3j_y34_g2c)

Click <span class="FPA-icons-V3"></span> \(*System Monitor*\) to access the main monitoring tool. The *System Monitor* allows to monitor the performance of your system and identify storage, task, out-of-memory, and other issues across all spaces.

For example, you can see all the errors \(such as failed tasks and out-of-memory errors\) that occurred yesterday or the top five statements with the highest peak memory consumption.

> ### Note:  
> For optimal performance, it is recommended that you consider staggering the scheduled run time of tasks such as data flows or task chains that may contain these tasks. Make sure to distribute your work such as scheduling and running tasks. There isn't a specific numerical limit on how many tasks can be scheduled. There could be a resource distribution issue caused by too many tasks running at once. Check your system monitor to look at your workload distribution. For more information see, [Monitoring SAP Datasphere](monitoring-sap-datasphere-28910cd.md) or [Persisted Views and Memory Consumption](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/e3d04951a4a344c28b25b2b1b13bf3d8.html "You want to persist a complex view and consider how it affects the memory consumption.") :arrow_upper_right:.

> ### Note:  
> SAP Datasphere is integrated into SAP Cloud ALM for health monitoring, which enables you to check the health of one or more SAP Datasphere tenants from the *Health Monitoring* app in SAP Cloud ALM. See [Health Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/health-monitoring) in the *SAP Cloud ALM - Application Help*.



<a name="loio28910cded17a42a0bf16225309cb8bf6__section_irf_214_1cc"/>

## Monitor Disk and Memory Assignment

1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(*System Monitor*\).

    You can monitor available disk and memory storage on your tenant with the following cards:


    <table>
    <tr>
    <th valign="top">

    Card
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Disk Storage Used*
    
    </td>
    <td valign="top">
    
    Shows the total amount of disk storage used in all spaces, broken down between:

    -   *Data in Spaces*: All data that is stored in spaces.

    -   *Audit Log Data*: Data related to audit logs \(see [Audit Logging](https://help.sap.com/viewer/0c3780ad05fd417fa27b98418535debd/cloud/en-US/c78a7c2a3cec4b0897db294d74e00d9b.html "Audit logs are records of read or change actions performed in the database. They allow you to see who performed which action at which point in time.") :arrow_upper_right:\).

        > ### Note:  
        > Audit logs can grow quickly and consume a great deal of disk storage \(see [Delete Audit Logs](delete-audit-logs-589fa42.md)\).

    -   *Other Data*: Includes data stored in database user group schemas \(see [Creating a Database User Group](../Creating-a-Database-User-Group/creating-a-database-user-group-1097a47.md)\) and SAP HANA data \(such as statistics schemas\).

    -   *Administrative Data*: Data used to administer the tenant and all spaces \(such as space quota, space version\). Includes all information stored in the central schemas \(DWC\_GLOBAL, DWC\_GLOBAL\_LOG, DWC\_TENANT\_OWNER\).



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Disk Used by Spaces for Storage*
    
    </td>
    <td valign="top">
    
    Shows the total amount of disk storage out of the total amount of disk storage. You can see a breakdown of this amount in the card *Disk Storage Used*.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Memory Used by Spaces for Storage*
    
    </td>
    <td valign="top">
    
    Shows the total amount of memory storage out of the total amount of memory storage.
    
    </td>
    </tr>
    </table>
    
2.  To investigate issues in particular spaces:
    1.  In the side navigation area, click ![](../images/Space_Management_a868247.png) \(*Space Management*\).
    2.  Display the list of spaces in the table layout and order by column. For example, you can display at the top of the table the spaces that use the highest amount of storage by choosing the descending order for the column *Used Storage*.
    3.  Open a space and click *Monitor* in the space details page to see the storage amount assigned to and used by the space \(see [Monitor Your Space Storage Consumption](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/94fe6c13f6a340288cd50ee355566591.html "See the storage amount assigned to and used by your space.") :arrow_upper_right:\).




<a name="loio28910cded17a42a0bf16225309cb8bf6__section_qyl_sc4_ccc"/>

## Monitor Tasks

For example, you can find out if tasks have to be scheduled at another time so that high-memory consuming tasks do not run at the same time. If single tasks consume too much memory, some additional views may need to be persisted or the view partitioning may need to be used to lower the memory consumption.

To investigate issues:

1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(*System Monitor*\).

    You can identify issues with tasks with the following cards:


    <table>
    <tr>
    <th valign="top">

    Card
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Failed Tasks*
    
    </td>
    <td valign="top">
    
    Two cards provide information:

    -   Shows the number of tasks that have failed in the last 24 hours with a trend icon \(up or down arrow\) indicating if there are more or less failed tasks than the day before.
    -   Shows the number of failed tasks by day for the last 7 days.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Top 5 Tasks by Run Duration*
    
    </td>
    <td valign="top">
    
    Two cards provide information:

    -   Shows the 5 tasks whose run duration time was the longest in the last 24 hours.
    -   Shows the 5 tasks whose run duration time was the longest in the last 48 hours.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Top 5 Tasks by Processing Memory Consumption*
    
    </td>
    <td valign="top">
    
    Two cards provide information:

    -   Shows the 5 tasks whose processing memory consumption was the highest in the last 24 hours.
    -   Shows the 5 tasks whose processing memory consumption was the highest in the last 48 hours.


    
    </td>
    </tr>
    </table>
    
2.  Click *View Logs* in a card to go to the *Task Logs* tab, which displays information filtered on the card criteria. For more information on the *Task Logs* tab, see [Task Logs Tab](monitoring-sap-datasphere-28910cd.md#loio28910cded17a42a0bf16225309cb8bf6__section_task_tab).
3.  Click the links in the following columns:
    -   *Activity* column - For the spaces you have access to \(via scoped roles\), a link opens the run in the *Data Integration Monitor* \(see [Managing and Monitoring Data Integration](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/4cbf7c7fc64645bfa364332827557267.html "Users with a space administrator or integrator role can use the Data Integration Monitor app to schedule, run, and monitor data replication and persistence tasks for remote tables and views, track queries sent to remote source systems, and manage other tasks through flows and task chains.") :arrow_upper_right:\).

    -   *Object Name* column - For the spaces you have access to \(via scoped roles\), a link opens the editor of the object.





<a name="loio28910cded17a42a0bf16225309cb8bf6__section_t2q_sc4_ccc"/>

## Monitor Statements

> ### Note:  
> Expensive statement tracing is enabled by default. If disabled, statement information and errors are not traced and you cannot see them in the *System Monitor*. For more information on enabling and configuring expensive statement tracing, see [Configure Monitoring](configure-monitoring-9cd0691.md).

1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(*System Monitor*\).

    You can monitor statements with the following cards:


    <table>
    <tr>
    <th valign="top">

    Card
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Top 5 Statements by Processing Memory Consumption*
    
    </td>
    <td valign="top">
    
    Two cards provide information:

    -   Shows the 5 statements whose processing memory consumption was the highest in the last 24 hours.
    -   Shows the 5 statements whose processing memory consumption was the highest in the last 48 hours.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Out-of-Memory Errors*
    
    </td>
    <td valign="top">
    
    Two cards provide information:

    -   Shows the number of out-of-memory errors that have occurred in tasks and statements in the last 24 hours.
    -   Shows the number of out-of-memory errors that have occurred in tasks and statements, by day for the last 7 days.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Top 5 MDS Requests by Processing Memory Consumption*
    
    </td>
    <td valign="top">
    
    Shows the 5 SAP HANA multi-dimensional services \(MDS\) requests \(used for example in SAP Analytics Cloud consumption\), whose processing memory consumption is the highest.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Out-of-Memory Errors \(MDS Requests\)*
    
    </td>
    <td valign="top">
    
    Shows the out-of-memory errors that are related to SAP HANA multi-dimensional services \(MDS\) requests, which is used for example for SAP Analytics Cloud consumption.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Top 5 Out-of-Memory Errors \(Workload Class\) by Space*
    
    </td>
    <td valign="top">
    
    Shows the schemas in which out-of-memory errors have occurred in the last 7 days because the statement limits have been exceeded.

    To set the statement limits for spaces, see [Set Priorities and Statement Limits for Spaces](../Creating-Spaces-and-Allocating-Storage/set-priorities-and-statement-limits-for-spaces-d66ac1e.md).
    
    </td>
    </tr>
    </table>
    
2.  Click *View Logs* in a card to go to the *Statement Logs*, which displays information filtered on the card criteria. For more information on the *Statements* tab, see [Statement Logs Tab](monitoring-sap-datasphere-28910cd.md#loio28910cded17a42a0bf16225309cb8bf6__section_statement_tab).
3.  Click the links in the *Statement Details* column.



<a name="loio28910cded17a42a0bf16225309cb8bf6__section_tt5_sc4_ccc"/>

## Monitor Access Control Issues

1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(*System Monitor*\).

    You can monitor statements that are rejected or queued with the following cards.


    <table>
    <tr>
    <th valign="top">

    Card
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Top 5 Admission Control Rejection Events by Space*
    
    </td>
    <td valign="top">
    
    Shows the 5 spaces with the highest number of rejected statements in the last 7 days.

    > ### Note:  
    > A space that has been deleted is prefixed with an asterisk character.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Admission Control Rejection Events*
    
    </td>
    <td valign="top">
    
    Two cards provide information:

    -   Shows the number of statements that have been rejected in the last 24 hours because they’ve exceeded the threshold percentage of CPU usage. A trend icon \(up or down arrow\) indicates if there are more or less rejected statements than the day before.
    -   Shows the number of statements that have been rejected in the last 7 days because they’ve exceeded the threshold percentage of CPU usage.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Top 5 Admission Control Queuing Events by Space*
    
    </td>
    <td valign="top">
    
    Shows the 5 spaces with the highest number of queued statements in the last 7 days.

    > ### Note:  
    > A space that has been deleted is prefixed with an asterisk character.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Admission Control Queuing Events*
    
    </td>
    <td valign="top">
    
    Two cards provide information:

    -   Shows the number of statements that have been queued in the last 24 hours because they’ve exceeded the threshold percentage of CPU usage. A trend icon \(up or down arrow\) indicates if there are more or less queued statements than the day before.
    -   Shows the number of statements that have been queued in the last 7 days because they’ve exceeded the threshold percentage of CPU usage.


    
    </td>
    </tr>
    </table>
    
2.  To investigate further, click *Open SAP HANA Cockpit* in a card.

    If you've created a database analysis user, you're connected to the SAP HANA Cockpit without entering your credentials \(see [Create a Database Analysis User to Debug Database Issues](create-a-database-analysis-user-to-debug-database-issues-c28145b.md).


For more information about admission control thresholds, see [Set Priorities and Statement Limits for Spaces](../Creating-Spaces-and-Allocating-Storage/set-priorities-and-statement-limits-for-spaces-d66ac1e.md).



<a name="loio28910cded17a42a0bf16225309cb8bf6__section_yvw_k24_ccc"/>

## Monitor Elastic Compute Nodes

Once you’ve created an elastic compute node in the *Space Management* app \(see [Create an Elastic Compute Node](../Creating-and-Configuring-Your-Tenant/create-an-elastic-compute-node-99ad61e.md)\), you can monitor its key figures, such as the start and end time of the last run or the amount of memory used for data replication.

1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(*System Monitor*\), then click the *Elastic Compute Nodes* tab.

2.  From the dropdown list, select the elastic compute node that you want to monitor.

    > ### Note:  
    > If one elastic compute node exists, related monitoring information is automatically displayed in the tab. If several elastic compute nodes exist, you must select a node from the dropdown list to display monitoring information in the tab.

    You can view elastic compute node key figures or identify issues with the following cards:


    <table>
    <tr>
    <th valign="top">

    Card
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Configuration*
    
    </td>
    <td valign="top">
    
    Shows the following information about the current elastic compute node:

    -   Technical name.

    -   Status, such as *Ready* or *Running* \(see [Run an Elastic Compute Node](../Creating-and-Configuring-Your-Tenant/run-an-elastic-compute-node-34b3585.md)\).

    -   The performance class and the resources allocated to the node: number of compute blocks, memory, disk storage and number of vCPUs.



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Run Details* 
    
    </td>
    <td valign="top">
    
    Shows the following information about the latest or the previous run of the current elastic compute node:

    -   The date and time at which the elastic compute node has started and stopped.

    -   The total run duration \(uptime\) from the starting to the stopping phase.

    -   The number of block-hours is the numbers of hours that have been consumed by the run. The number of block-hours is the result of the run duration in numbers of hours multiplied by the number of compute blocks. If a node that includes 4 compute blocks runs for 5 hours, 20 block-hours have been consumed. In such a case, the uptime equals the block-hours. If a node that includes 8 compute blocks runs for 5 hours, 40 block-hours have been consumed.



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Monthly Uptime*
    
    </td>
    <td valign="top">
    
    Shows the following information about the elastic compute node runs for the current month or the last month:

    -   The total duration \(uptime\) of all runs in the current or last month.

    -   The total number of block-hours consumed by all the runs in the current or last month.



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Average CPU*
    
    </td>
    <td valign="top">
    
    Shows the average percentage of the number of vCPUs consumed, during the latest or previous run of the elastic compute node.

    The trend icon \(up or down arrow\) indicates if the percentage is higher or lower than the previous run.

    To see the real-time average CPU utilization in percentage for the elastic compute note, click *Performance Monitor*, which opens the Performance Monitor page in the SAP HANA Cockpit \(see [The Perfomance Monitor](https://help.sap.com/docs/hana-cloud/sap-hana-cloud-database-administration-with-sap-hana-cockpit/performance-monitor) in the *SAP HANA Cloud Database Administration with SAP HANA Cockpit*\).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Average Memory*
    
    </td>
    <td valign="top">
    
    Shows the average amount of memory consumed \(in GiB\), during the latest or previous run of the elastic compute node.

    The trend icon \(up or down arrow\) indicates if the percentage is higher or lower than the previous run.

    To see the real-time average memory utilization in GB for the elastic compute note, click *Performance Monitor*, which opens the Performance Monitor page in the SAP HANA Cockpit \(see [The Perfomance Monitor](https://help.sap.com/docs/hana-cloud/sap-hana-cloud-database-administration-with-sap-hana-cockpit/performance-monitor) in the *SAP HANA Cloud Database Administration with SAP HANA Cockpit*\).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Total Uptime*
    
    </td>
    <td valign="top">
    
    Shows the total duration in hours of all runs of the elastic compute node.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Top 5 Statements by Processing Memory Consumption*
    
    </td>
    <td valign="top">
    
    Shows the 5 statements whose memory consumption was the highest during the last run of the elastic compute node.

    To see detailed information about the statements, you can click *View Logs*, which takes you to the *Statement Logs* tab. See [Monitoring SAP Datasphere](monitoring-sap-datasphere-28910cd.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Out-of-Memory Errors*
    
    </td>
    <td valign="top">
    
    Shows the number of out-of-memory errors that have occurred in tasks and statements related to the elastic compute node, during the last run.

    To see detailed information about the errors, you can click *View Logs*, which takes you to the *Statement Logs* tab. See [Monitoring SAP Datasphere](monitoring-sap-datasphere-28910cd.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Memory Distribution*
    
    </td>
    <td valign="top">
    
    Shows the amount of memory allocated to the elastic compute node, if in a running state, broken down between:

    -   *Unused Memory* - Shows the amount of memory available for the elastic compute node.

    -   *Memory Used for Data Replication* - Shows the amount of memory used to store replicated data for the elastic compute node.

    -   *Memory Used for Processing* - Shows the amount of memory used by the processes that are currently running for the elastic compute node. For example: consumption of the queries running on the elastic compute node.


    > ### Note:  
    > If the elastic compute node is not in a running state, no data is displayed.


    
    </td>
    </tr>
    </table>
    
3.  To investigate further, you can do the following:

    -   To view statement details, click *View Logs* in a card to go to the *Statement Logs* tab, which displays information filtered on the card criteria. Then, click the links in the *Statement Details* column. For more information on the *Statement Logs* tab, see [Statement Logs Tab](monitoring-sap-datasphere-28910cd.md#loio28910cded17a42a0bf16225309cb8bf6__section_statement_tab).
    -   To view details on a run, click *View Logs* in a card to go to the *Task Logs* tab, which displays information filtered on the card criteria. In the *Activity* column, click the link to open the run in the *Data Integration Monitor* \(see [Managing and Monitoring Data Integration](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/4cbf7c7fc64645bfa364332827557267.html "Users with a space administrator or integrator role can use the Data Integration Monitor app to schedule, run, and monitor data replication and persistence tasks for remote tables and views, track queries sent to remote source systems, and manage other tasks through flows and task chains.") :arrow_upper_right:\).
    -   To navigate to the elastic compute node in the *Space Management* app, click *Manage Elastic Compute Node* \(see [Create an Elastic Compute Node](../Creating-and-Configuring-Your-Tenant/create-an-elastic-compute-node-99ad61e.md) and [Run an Elastic Compute Node](../Creating-and-Configuring-Your-Tenant/run-an-elastic-compute-node-34b3585.md)\).

    -   To analyze the performance of the SAP HANA database, click *Database Overview \(SAP HANA Cockpit\)*, which opens the Database Overview page in the SAP HANA Cockpit \(see [The Database Overview Page](https://help.sap.com/docs/hana-cloud/sap-hana-cloud-database-administration-with-sap-hana-cockpit/database-overview-page) in the *SAP HANA Cloud Database Administration with SAP HANA Cockpit*\).





<a name="loio28910cded17a42a0bf16225309cb8bf6__section_i3j_y34_g2c"/>

## Monitor Capacity Units

As a tenant administrator, you can view the consumption of capacity units for various features over time. This tool is useful for optimizing resource allocation and ensuring efficient subscription management.

From the side navigation menu, click <span class="FPA-icons-V3"></span> \(*System Monitor*\)** \> *Capacities*.

Your dailly consumption for the current month is shown. You track usage relitive to your subscription. You can also download detailed hourly data. See [Monitor Capacities](monitor-capacities-ba3d05b.md).



<a name="loio28910cded17a42a0bf16225309cb8bf6__section_task_tab"/>

## Task Logs Tab

In *Task Logs*, the table shows the following information:


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

*Start Time*

</td>
<td valign="top">

Shows at what time \(date and hour\) the task has started to run.

</td>
</tr>
<tr>
<td valign="top">

*Duration \(sec\)*

</td>
<td valign="top">

Shows how many seconds the task has run.

</td>
</tr>
<tr>
<td valign="top">

*Object Type*

</td>
<td valign="top">

Shows the type of object that was run in the task. For example: view, remote table, data flow.

</td>
</tr>
<tr>
<td valign="top">

*Activity*

</td>
<td valign="top">

Shows the action that was performed on the object. For example: persist, replicate, execute. You can click on the activity name, which takes you to the *Data Integration Monitor*.

</td>
</tr>
<tr>
<td valign="top">

*Space Name*

</td>
<td valign="top">

Shows the name of the space in which the task is run.

</td>
</tr>
<tr>
<td valign="top">

*Object Name*

</td>
<td valign="top">

Shows the name of the object. You can click on the object name, which opens the object in the *Data Builder*.

</td>
</tr>
<tr>
<td valign="top">

*SAP HANA Peak Memory*

</td>
<td valign="top">

Shows the maximum amount of memory \(in MiB\) the task has used during the runtime in SAP HANA.

> ### Note:  
> You can see this information:
> 
> -   The option *Enable Expensive Statement Tracing* is enabled by default. It traces task exceeding the thresholds specified in <span class="FPA-icons-V3"></span> \(Configuration\) → *Monitoring*.
> 
> -   And if the task is run for these objects \(and activities\): views \(persist, remove\_persisted\_data\), remote tables \(replicate, enable\_realtime\), data flows \(execute\) and intelligent lookup \(execute, delete\_data\).
> 
> 
> Otherwise, no number is displayed.



</td>
</tr>
<tr>
<td valign="top">

*SAP HANA CPU Time*

</td>
<td valign="top">

Shows the maximum amount of CPU time \(in ms\) the task has used in SAP HANA.

> ### Note:  
> You can see this information:
> 
> -   If the option *Enable Expensive Statement Tracing* is enabled and if the task exceeds the thresholds specified in <span class="FPA-icons-V3"></span> \(Configuration\) → *Monitoring*. See [Configure Monitoring](configure-monitoring-9cd0691.md).
> 
> -   And if the task is run for these objects \(and activities\): views \(persist, remove\_persisted\_data\), remote tables \(replicate, enable\_realtime\), data flows \(execute\) and intelligent lookup \(execute, delete\_data\).
> 
> 
> Otherwise, no number is displayed.

> ### Note:  
> The CPU time indicates how much time is used for all threads. It means that if the CPU time is significantly higher than the duration of the statement, then many threads are used. If many threads are used for a long time, no other tasks should be scheduled at that point in time, or resource bottlenecks may occur and tasks may even be canceled.



</td>
</tr>
<tr>
<td valign="top">

*Records*

</td>
<td valign="top">

Shows the number of records of the target table after the task has finished running.

> ### Note:  
> You can see this information only if the task is run for these objects \(and activities\): views \(persist\), remote tables \(replicate, enable\_realtime\), data flows \(execute\) and intelligent lookup \(execute, delete\_data\). Otherwise, no number is displayed.



</td>
</tr>
<tr>
<td valign="top">

*SAP HANA Used Memory*

</td>
<td valign="top">

Shows the amount of memory \(in MiB\) that is used by the target table in SAP HANA after the task has finished running.

</td>
</tr>
<tr>
<td valign="top">

*SAP HANA Used Disk*

</td>
<td valign="top">

Shows the amount of disk space \(in MiB\) that is used by the target table in SAP HANA after the task has finished running.

</td>
</tr>
<tr>
<td valign="top">

*Status*

</td>
<td valign="top">

Shows the status of the task: completed, failed, running.

</td>
</tr>
<tr>
<td valign="top">

*Substatus*

</td>
<td valign="top">

For tasks with the status “failed”, shows the substatus and a message describing the cause of failure. For more information about failed task substatuses, see [Understanding Statuses and Substatuses](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/19cb5bdca7c5412da24bf0ac2badeef7.html "When you run an activity (replicate a remote table, persist a view, etc..), the progress of the task is monitored using statuses and substatuses. Statuses and substatuses are available in the relevant editors as well as in the System Monitor.") :arrow_upper_right:.

</td>
</tr>
<tr>
<td valign="top">

*User*

</td>
<td valign="top">

Shows the user who has run the task.

</td>
</tr>
<tr>
<td valign="top">

*Target Table*

</td>
<td valign="top">

Shows the SAP HANA database technical name of the target table.

</td>
</tr>
<tr>
<td valign="top">

*Statements*

</td>
<td valign="top">

Shows a link you can click to view all the statements of the task in the *Statements* tab, if the information is available.

> ### Note:  
> -   You can see this information if the option *Enable Expensive Statement Tracing* is enabled in <span class="FPA-icons-V3"></span> \(Configuration\) → *Monitoring*. See [Configure Monitoring](configure-monitoring-9cd0691.md).
> 
> -   However, as statements are traced for a limited period, you may not be able to see the statements used in the task.



</td>
</tr>
<tr>
<td valign="top">

*Out-of-Memory*

</td>
<td valign="top">

Shows if the task has an out-of-memory error \("Yes" is then displayed\) or not \("No" is then displayed\).

</td>
</tr>
<tr>
<td valign="top">

*Task Log ID*

</td>
<td valign="top">

Shows the identifier of the run task.

</td>
</tr>
<tr>
<td valign="top">

*Start Date*

</td>
<td valign="top">

Shows at which date the task has started to run.

</td>
</tr>
</table>

You can cancel a task run by selecting one single task and clicking *Cancel Task*. You can cancel a task run on the following objects:

-   Transformation flow
-   Remote table view
-   Data flow
-   Task chain

Cancelling a task run may be required when it takes too long or if the run impacts negatively other runs by taking too many resources away. Canceling a task via the *System Monitor* is the most reliable option. Its access isn't restricted when resource consumption is too high \(as in the *Data Integration Monitor*\), and it is the fastest way to cancel a task \(compared to the *Database Explorer*\). The data is rolled back and restored to the state that existed before the task run was initially triggered.

> ### Note:  
> -   Data on tasks are kept for the time specified in <span class="FPA-icons-V3"></span> \(Configuration\) → *Tasks*.
> -   You may not be able to cancel a task via the *Data Integration Monitor* or the *Database Explorer* when resource consumption is too high. You will always be able to cancel a task via the *System Monitor*.



<a name="loio28910cded17a42a0bf16225309cb8bf6__section_statement_tab"/>

## Statement Logs Tab

In *Statement Logs*, the table shows the following information, depending on what you've specified in <span class="FPA-icons-V3"></span> \(Configuration\) → *Monitoring*:

-   The option *Enable Expensive Statement Tracing* is enabled by default, you can see all the database statements that exceed the specified thresholds.

-   If the option *Enable Expensive Statement Tracing* is disabled, then the *Statements* tab is disabled.


See [Configure Monitoring](configure-monitoring-9cd0691.md).


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

*Start Time*

</td>
<td valign="top">

Shows at what time \(date and hour\) the statement has started to run.

</td>
</tr>
<tr>
<td valign="top">

*Duration \(ms\)*

</td>
<td valign="top">

Shows how many milliseconds the statement has run.

</td>
</tr>
<tr>
<td valign="top">

*Object Type*

</td>
<td valign="top">

-   Shows the type of object that was run in the statement \(for example: view, remote table, data flow\).

-   Or shows the area where the statement was run:

    -   MDS - this is an SAP HANA multi-dimensional services \(MDS\) statement, which is caused for example by stories when SAP Analytics Cloud queries SAP Datasphere.

    -   Data Flow - the statement was run by a data flow.

    -   Analysis - the statement was run by a database analysis user.

    -   Space SQL - the statement was run by a database user of a space.

    -   Business Layer Modeling - the statement was run in the *Business Builder*.

    -   Data Layer Modeling - the statement was run in the data preview of the view editor in the *Data Builder*.

    -   DWC Space Management - the statement was run in the *Space Management*, for example, when deploying an object.

    -   DB Usergroup - the statement was run by a user of a database user group.

    -   DWC Administration - the statement was run for an administration task such as writing a task framework status.

    -   System - any other SAP HANA system statement.





</td>
</tr>
<tr>
<td valign="top">

*Activity*

</td>
<td valign="top">

Shows the action that was performed. For example: update, compile, select.

</td>
</tr>
<tr>
<td valign="top">

*Object Name*

</td>
<td valign="top">

If the statement is related to a task, it shows the name of the object for which the statement was run.

</td>
</tr>
<tr>
<td valign="top">

*Schema Name* 

</td>
<td valign="top">

Shows the name of the schema in which the statement is run.

</td>
</tr>
<tr>
<td valign="top">

*SAP HANA Peak Memory*

</td>
<td valign="top">

Shows the maximum amount of memory \(in MiB\) the statement has used during the runtime in SAP HANA.

> ### Note:  
> You can see the information if the option *Enable Expensive Statement Tracing* is enabled and if the statement exceeds the thresholds specified in <span class="FPA-icons-V3"></span> \(Configuration\) → *Monitoring*. See [Configure Monitoring](configure-monitoring-9cd0691.md).
> 
> Otherwise, no number is displayed.



</td>
</tr>
<tr>
<td valign="top">

*SAP HANA CPU Time*

</td>
<td valign="top">

Shows the amount of CPU time \(in ms\) the statement has used in SAP HANA.

> ### Note:  
> You can see the information if the option *Enable Expensive Statement Tracing* is enabled and if the statement exceeds the thresholds specified in <span class="FPA-icons-V3"></span> \(Configuration\) → *Monitoring*. See [Configure Monitoring](configure-monitoring-9cd0691.md).
> 
> Otherwise, no number is displayed.

> ### Note:  
> The CPU time indicates how much time is used for all threads. It means that if the CPU time is significantly higher than the duration of the statement, then many threads are used. If many threads are used for a long time, no other tasks should be scheduled at that point in time, or resource bottlenecks may occur and tasks may even be canceled.



</td>
</tr>
<tr>
<td valign="top">

*Statement Details*

</td>
<td valign="top">

Shows the *More* link that you can click to view the complete SQL statement.

> ### Note:  
> For MDS queries - If you’ve enabled the tracing of MDS information \(see [Configure Monitoring](configure-monitoring-9cd0691.md)\), the payload of the MDS query that is run by SAP Analytics Cloud is displayed. If identified in the payload, the following information is also displayed: story ID, story name and data sources. You can copy or download the displayed information.



</td>
</tr>
<tr>
<td valign="top">

*Parameters*

</td>
<td valign="top">

Shows the values of the parameters of the statement that are indicated by the character "?" in the popup that opens when clicking *More* in the *Statement Details* column.

</td>
</tr>
<tr>
<td valign="top">

*Out-of-memory*

</td>
<td valign="top">

Shows if the statement has an out-of-memory error. If there is one, a timestamp is displayed. If there is none, *NULL* is then displayed.

</td>
</tr>
<tr>
<td valign="top">

*Task Log ID*

</td>
<td valign="top">

If the statement is related to a task, it shows the identifier of the task within a link, which takes you to the *Tasks* tab filtered on this task.

</td>
</tr>
<tr>
<td valign="top">

*Elastic Compute Node*

</td>
<td valign="top">

If the statement exceeds the thresholds specified in the option *Enable Expensive Statement Tracing* in <span class="FPA-icons-V3"></span> \(Configuration\) → *Monitoring* \(see [Configure Monitoring](configure-monitoring-9cd0691.md)\):

-   Shows the name of the elastic compute node if the statement is run on an elastic compute node.

-   Shows a hyphen \(-\) if the statement is run on the main instance.




</td>
</tr>
<tr>
<td valign="top">

*Error Code*

</td>
<td valign="top">

If the statement has failed, it shows the numeric code of the SQL error. See [SQL Error Codes](https://help.sap.com/docs/SAP_HANA_PLATFORM/4fe29514fd584807ac9f2a04f6754767/20a78d3275191014b41bae7c4a46d835.html) in the *SAP HANA SQL Reference Guide for SAP HANA Platform*.

</td>
</tr>
<tr>
<td valign="top">

*Error Message*

</td>
<td valign="top">

If the statement has failed, it shows a description of the SQL error.

</td>
</tr>
<tr>
<td valign="top">

*Workload Class*

</td>
<td valign="top">

If the statement has an out-of-memory error, it shows the name of the workload class whose limit has been exceeded.

</td>
</tr>
<tr>
<td valign="top">

*Statement ID*

</td>
<td valign="top">

Shows the identifier of the statement.

</td>
</tr>
<tr>
<td valign="top">

*Connection ID*

</td>
<td valign="top">

Shows the ID used to connect to the database.

</td>
</tr>
<tr>
<td valign="top">

*Start Date*

</td>
<td valign="top">

Shows at which date the statement has started to run.

</td>
</tr>
</table>

> ### Note:  
> Data on statements are kept for a time that depends on the thresholds specified in <span class="FPA-icons-V3"></span> \(Configuration\) → *Monitoring* \(see [Configure Monitoring](configure-monitoring-9cd0691.md)\). As a certain number of statements are kept \(30.000 by default\), if very low thresholds are set, the time period may be very low \(for example, only a few hours\). To keep the statements for a longer time, the thresholds should be set accordingly.



<a name="loio28910cded17a42a0bf16225309cb8bf6__section_a4f_vzb_xtb"/>

## Show/Hide, Filter, Sort and Reorder Task and Statement Columns

You can control the tables in *Task Logs* and *Statement Logs* in the following ways:

-   Reorder the columns by drag and drop.
-   Sort on a column by clicking the column header and then clicking <span class="SAP-icons-V5"></span> \(Sort Ascending\) or <span class="SAP-icons-V5"></span> \(Sort Descending\).
-   Filter on a column by using the quick filtering or the advanced filtering options.

    -   **Quick Filters** 


        <table>
        <tr>
        <th valign="top">

        Filter
        
        </th>
        <th valign="top">

        Description
        
        </th>
        </tr>
        <tr>
        <td valign="top">
        
        *Date and Time Range*
        
        </td>
        <td valign="top">
        
        Enter one date and time range or click <span class="SAP-icons-V5"></span> to see the available options:

        -   Single Dates - *Today*, *Yesterday*
        -   Date Ranges - *From/To*, *From/To \(Date and Time\)*, *From*, *To*, *From \(Date and Time\)*,*To \(Date and Time\)*, *Last X Minutes/Hours/Days/Weeks* 
        -   Custom Options - *Last 1 Hour*, *Last 6 Hours*, *Last 24 Hours*


        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *Spaces*
        
        </td>
        <td valign="top">
        
        Select or enter the name of at least one space. All spaces of the tenant are available, even the ones you are not added to.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *Statuses*
        
        </td>
        <td valign="top">
        
        Select or enter at least one status: *Completed*, *Failed*, or *Running*.
        
        </td>
        </tr>
        </table>
        
        > ### Example:  
        > You are looking for all failed and running records that happened last week in the space *ACME\_TF*. Define the time range by clicking <span class="SAP-icons-V5"></span> to display the list of available options and selecting *From/To* in *Date and Time Range* and selecting the dates relevant to you in the calendar. Then, select the space *ACME\_TF* in the *Space* filter drop down list. Finally, select *Failed* and *Running* in the *Statuses* drop down list. The log list automatically updates after each filter definition.

        > ### Note:  
        > -   Defined quick filters are shown in the *Define Filter* dialog. If you add an advanced filter in the *Define Filter* dialog, the quick filters fields will be cleared. The filters are not deleted.
        > -   Filters defined in the *Define Filter* dialog are not shown in the quick filters fields.

    -   **Advanced Filters** 
        1.  Click a column header, then click <span class="FPA-icons-V3"></span> \(Filter\). The *Define Filter* dialog opens and advanced filtering options are available.
        2.  Chose the appropriate section for your filter. If your filter is meant to include data in the table \(you could say "I want my Data Preview to show"\), add your filter in the *Include* section. If your filter is meant to exclude data from the table \(you could say "I want my Data Preview to hide"\), add your filter in the *Exclude* section. When in the appropriate section, click <span class="FPA-icons-V3"></span> \(Add Filter\) to add a filter.
        3.  Select a column to filter on, a filtering option, and a value. You can add several filters. Click *OK* to apply the filter\(s\). The currently applied filters are displayed above the table.

            > ### Example:  
            > To only see the tasks that have failed on remote tables, in the *Include* area, select the column *Object Type*, then the filtering value *contains* and enter "REMOTE". Then, add a filter, select the column *Status*, then the filtering value *contains* and enter "FAILED". Once applied, the filter is displayed above the table.

        4.  Click *Clear Filter* in the filter strip or <span class="FPA-icons-V3"></span> \(Remove Filter\) in the *Define Filter* dialog to remove the filter.


    > ### Note:  
    > -   The filtering options available depend on the data type of the column you filter on.
    > -   Filters applied to text columns are case-sensitive.
    > -   You can enter filter or sort values in multiple columns.
    > -   To increase performance, only the first 1,000 rows are displayed. Use filters to find the data you are looking for. Filters are applied to all rows, but only the first filtered 1,000 rows are displayed.

    > ### Note:  
    > If you filter on one of the following columns and you enter a number, use the “.” \(period\) character as the decimal separator, regardless of the decimal separator used in the number formatting that you’ve chosen in the general user settings \(*Settings* \> *Language & Region*\): *SAP HANA Peak Memory*, *SAP HANA CPU Time*, *SAP HANA Used Memory* and *SAP HANA Used Disk*.

-   Show or hide columns by clicking :gear: to open the *Columns Settings* dialog, selecting columns as appropriate. To return to the default preview columns, click *Reset*.
-   Refresh the table at any time by clicking *Refresh*.

