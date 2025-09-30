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
-   [Monitoring File Space Storage Consumption and Apache Spark Application Usage](monitoring-sap-datasphere-28910cd.md#loio28910cded17a42a0bf16225309cb8bf6__section_apachespark_tasks)
-   [Task Logs Tab](monitoring-sap-datasphere-28910cd.md#loio28910cded17a42a0bf16225309cb8bf6__section_task_tab)
-   [Statement Logs Tab](monitoring-sap-datasphere-28910cd.md#loio28910cded17a42a0bf16225309cb8bf6__section_statement_tab)
-   [Show/Hide, Filter, Sort and Reorder Task and Statement Columns](monitoring-sap-datasphere-28910cd.md#loio28910cded17a42a0bf16225309cb8bf6__section_a4f_vzb_xtb)
-   [Monitor Capacity Units](monitoring-sap-datasphere-28910cd.md#loio28910cded17a42a0bf16225309cb8bf6__section_i3j_y34_g2c)

Click <span class="FPA-icons-V3"></span> \(*System Monitor*\) in the side navigation to open the main monitoring tool. The *System Monitor* cards and tabs allow the monitoring of your system perfomance and issues related to storage, tasks, out-of-memory, and other issues across all spaces.

For example, you can see all the errors \(such as failed tasks and out-of-memory errors\) that occurred yesterday or the top five statements with the highest peak memory consumption.

> ### Note:  
> For optimal performance, it is recommended that you consider staggering the scheduled run time of tasks such as data flows or task chains that may contain these tasks. Make sure to distribute your work such as scheduling and running tasks. There isn't a specific numerical limit on how many tasks can be scheduled. There could be a resource distribution issue caused by too many tasks running at once. Check your system monitor to look at your workload distribution. For more information see, [Monitoring SAP Datasphere](monitoring-sap-datasphere-28910cd.md) or [Persisted Views and Memory Consumption](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/e3d04951a4a344c28b25b2b1b13bf3d8.html "You want to persist a complex view and consider how it affects the memory consumption.") :arrow_upper_right:.

> ### Note:  
> SAP Datasphere is integrated into SAP Cloud ALM for health monitoring, which enables you to check the health of one or more SAP Datasphere tenants from the *Health Monitoring* app in SAP Cloud ALM. See [Health Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/health-monitoring) in the *SAP Cloud ALM - Application Help*.



<a name="loio28910cded17a42a0bf16225309cb8bf6__section_irf_214_1cc"/>

## Monitor Disk and Memory Assignment

1.  Review these cards to identify storage issues:


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
    
    Total disk usage in all spaces, broken down by:

    -   *Data in Spaces*: All data that is stored in spaces.

    -   *Audit Log Data*: Data related to audit logs \(see [Audit Logging](https://help.sap.com/viewer/0c3780ad05fd417fa27b98418535debd/cloud/en-US/c78a7c2a3cec4b0897db294d74e00d9b.html "Audit logs are records of read or change actions performed in the database. They allow you to see who performed which action at which point in time.") :arrow_upper_right:\). Audit logs can quickly consume large amounts of storage \(see [Delete Audit Logs](delete-audit-logs-589fa42.md)\).

    -   *Other Data*: Includes data stored in database user group schemas \(see [Creating a Database User Group](../Creating-a-Database-User-Group/creating-a-database-user-group-1097a47.md)\) and SAP HANA data \(such as statistics schemas\).

    -   *Administrative Data*: Data used to administer the tenant and all spaces \(such as space quota, space version\) and central schemas information \(DWC\_GLOBAL, DWC\_GLOBAL\_LOG, DWC\_TENANT\_OWNER\).



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Disk Used by Spaces for Storage*
    
    </td>
    <td valign="top">
    
    Total amount of disk storage out of the total amount of disk storage. See a breakdown of this amount in the card *Disk Storage Used*.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Memory Used by Spaces for Storage*
    
    </td>
    <td valign="top">
    
    Total amount of memory storage out of the total amount of memory storage.
    
    </td>
    </tr>
    </table>
    
2.  To investigate issues in particular spaces:
    1.  In the side navigation area, click ![](../images/Space_Management_a868247.png) \(*Space Management*\).
    2.  Display the list of spaces in the table layout and order by column. For example, you can display at the top of the table the spaces that use the highest amount of storage by choosing the descending order for the column *Used Storage*.
    3.  Open a space and click *Monitor* in the space details page to see the storage amount assigned to and used by the space \(see [Monitor Your Space Storage Consumption](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/94fe6c13f6a340288cd50ee355566591.html "See the storage amount assigned to and used by your space.") :arrow_upper_right:\).




<a name="loio28910cded17a42a0bf16225309cb8bf6__section_qyl_sc4_ccc"/>

## Monitor Tasks

Monitoring tasks can help you understand errors better. For example, you can find out if tasks have to be scheduled at another time so that high-memory consuming tasks do not run at the same time. If single tasks consume too much memory, some additional views may need to be persisted or the view partitioning may need to be used to lower the memory consumption.

To investigate issues:

1.  Review these cards to identify issues with tasks:


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
    
    Two cards show the number of tasks that have failed in the last 24 hours and last 7 days with a trend icon \(up or down arrow\) indicating if there are more or less failed tasks than the day before for the 24 hours card.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Top 5 Tasks by Run Duration*
    
    </td>
    <td valign="top">
    
    Two cards show the 5 tasks whose run duration time was the longest in the last 24 hours and 48 hours.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Top 5 Tasks by Processing Memory Consumption*
    
    </td>
    <td valign="top">
    
    Two cards show the 5 tasks whose processing memory consumption was the highest in the last 24 hours and 48 hours.
    
    </td>
    </tr>
    </table>
    
2.  Click *View Logs* in a card to go to the *Task Logs* tab, which displays information filtered on the card criteria \(see [Task Logs Tab](monitoring-sap-datasphere-28910cd.md#loio28910cded17a42a0bf16225309cb8bf6__section_task_tab)\).
3.  For the spaces you have access to \(via scoped roles\), click the links in the following columns:
    -   *Activity* - opens the run in the *Data Integration Monitor* \(see [Managing and Monitoring Data Integration](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/4cbf7c7fc64645bfa364332827557267.html "Users with a space administrator or integrator role can use the Data Integration Monitor app to schedule, run, and monitor data replication and persistence tasks for remote tables and views, track queries sent to remote source systems, and manage other tasks through flows and task chains.") :arrow_upper_right:\).

    -   *Object Name* - opens the editor of the object.



> ### Note:  
> If your SAP Datasphere tenant is enabled for job & automation monitoring in SAP Cloud ALM, you can monitor the tasks run or scheduled in SAP Datasphere \(except for a task which is a child of another task\), from the *Job & Automation Monitoring* app in SAP Cloud ALM . See [Job & Automation Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/job-automation-monitoring) in the *SAP Cloud ALM - Application Help*.



<a name="loio28910cded17a42a0bf16225309cb8bf6__section_t2q_sc4_ccc"/>

## Monitor Statements

> ### Note:  
> Expensive statement tracing is enabled by default. If disabled, statement information and errors are not traced and you cannot see them in the *System Monitor*. For more information on enabling and configuring expensive statement tracing, see [Configure Monitoring](configure-monitoring-9cd0691.md).

1.  Monitor statements with the following cards:


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
    
    Two cards show the 5 statements whose processing memory consumption was the highest in the last 24 hours and 48 hours.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Out-of-Memory Errors*
    
    </td>
    <td valign="top">
    
    Two cards show the number of out-of-memory errors that have occurred in tasks and statements in the last 24 hours and 7 days.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Top 5 MDS Requests by Processing Memory Consumption*
    
    </td>
    <td valign="top">
    
    Top 5 SAP HANA multi-dimensional services \(MDS\) requests \(used for example in SAP Analytics Cloud consumption\), whose processing memory consumption is the highest.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Out-of-Memory Errors \(MDS Requests\)*
    
    </td>
    <td valign="top">
    
    Out-of-memory errors that are related to SAP HANA multi-dimensional services \(MDS\) requests, which is used for example for SAP Analytics Cloud consumption.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Top 5 Out-of-Memory Errors \(Workload Class\) by Space*
    
    </td>
    <td valign="top">
    
    Schemas in which out-of-memory errors have occurred in the last 7 days because the statement limits have been exceeded. Set the statement limits for spaces, see [Set Priorities and Statement Limits for Spaces or Groups](../Creating-Spaces-and-Allocating-Storage/set-priorities-and-statement-limits-for-spaces-or-groups-d66ac1e.md).
    
    </td>
    </tr>
    </table>
    
2.  Click *View Logs* in a card to go to the *Statement Logs* to see information filtered on the card criteria. See [Statement Logs Tab](monitoring-sap-datasphere-28910cd.md#loio28910cded17a42a0bf16225309cb8bf6__section_statement_tab).
3.  Click the links in the *Statement Details* column for further details.



<a name="loio28910cded17a42a0bf16225309cb8bf6__section_tt5_sc4_ccc"/>

## Monitor Access Control Issues

1.  Monitor rejected or queued statements with the following cards:


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
    
    Top 5 spaces with the highest number of rejected statements in the last 7 days. Deleted spaces are prefixed with an asterisk character.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Admission Control Rejection Events*
    
    </td>
    <td valign="top">
    
    Number of statements that have been rejected in the last 24 hours or 7 days because they’ve exceeded the threshold percentage of CPU usage. A trend icon \(up or down arrow\) indicates if there are more or less rejected statements than the day before for the 24 hours card.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Top 5 Admission Control Queuing Events by Space*
    
    </td>
    <td valign="top">
    
    Top 5 spaces with the highest number of queued statements in the last 7 days. Deleted spaces are prefixed with an asterisk character.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Admission Control Queuing Events*
    
    </td>
    <td valign="top">
    
    Number of statements that have been queued in the last 24 hours or 7 days because they’ve exceeded the threshold percentage of CPU usage. A trend icon \(up or down arrow\) indicates if there are more or less queued statements than the day before for the 24 hours card.
    
    </td>
    </tr>
    </table>
    
2.  To investigate further, click *Open SAP HANA Cockpit* in a card. If you've created a database analysis user, you're connected to the SAP HANA Cockpit without entering your credentials \(see [Create a Database Analysis User to Debug Database Issues](create-a-database-analysis-user-to-debug-database-issues-c28145b.md).

For more information about admission control thresholds, see [Set Priorities and Statement Limits for Spaces or Groups](../Creating-Spaces-and-Allocating-Storage/set-priorities-and-statement-limits-for-spaces-or-groups-d66ac1e.md).



<a name="loio28910cded17a42a0bf16225309cb8bf6__section_yvw_k24_ccc"/>

## Monitor Elastic Compute Nodes

After creating an elastic compute node \(see [Create an Elastic Compute Node](../Creating-and-Configuring-Your-Tenant/create-an-elastic-compute-node-99ad61e.md)\), monitor its key figures.

1.  Click the *Elastic Compute Nodes* tab and select the node you want to monitor from the drop down list. If a single elastic compute node exists, its information is automatically displayed in the tab. If several nodes exist, you must select one to see its information.

2.  Review elastic compute node key figures or identify issues with the following cards:


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
    
    Information about the selected elastic compute node:

    -   Technical name.

    -   Status, such as *Ready* or *Running* \(see [Run an Elastic Compute Node](../Creating-and-Configuring-Your-Tenant/run-an-elastic-compute-node-34b3585.md)\).

    -   Performance class and resources allocated to the node \(number of compute blocks, memory, disk storage and number of vCPUs\).



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Run Details* 
    
    </td>
    <td valign="top">
    
    Information about the latest or the previous run of the current elastic compute node:

    -   Date and time at which the node has started and stopped.

    -   Total run duration \(uptime\) from the starting to the stopping phase.

    -   Block-hours represent the total hours consumed by a run. You calculate block-hours by multiplying the run duration in hours by the number of compute blocks. For example, if a node with four compute blocks runs for five hours, it consumes 20 block-hours. In this scenario, the uptime equals the block-hours. Similarly, if a node with eight compute blocks runs for five hours, it consumes 40 block-hours.



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Monthly Uptime*
    
    </td>
    <td valign="top">
    
    Information about the node's runs for the current month or the last month:

    -   The total duration \(uptime\) of all runs in the current or last month.

    -   The total number of block-hours consumed by all the runs in the current or last month.



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Average CPU*
    
    </td>
    <td valign="top">
    
    Average percentage of the number of vCPUs consumed during the latest or previous run of the elastic compute node. The trend icon \(up or down arrow\) shows if the usage higher or lower than the previous run.

    For real-time average CPU utilization percentage, click *Performance Monitor* to open the Performance Monitor page in the SAP HANA Cockpit \(see [The Perfomance Monitor](https://help.sap.com/docs/hana-cloud/sap-hana-cloud-database-administration-with-sap-hana-cockpit/performance-monitor) in the *SAP HANA Cloud Database Administration with SAP HANA Cockpit*\).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Average Memory*
    
    </td>
    <td valign="top">
    
    Average amount of memory consumed \(in GiB\) during the latest or previous run of the elastic compute node. The trend icon \(up or down arrow\) shows if the percentage is higher or lower than the previous run.

    For real-time average memory utilization in GB, click *Performance Monitor* to open the Performance Monitor page in the SAP HANA Cockpit \(see [The Perfomance Monitor](https://help.sap.com/docs/hana-cloud/sap-hana-cloud-database-administration-with-sap-hana-cockpit/performance-monitor) in the *SAP HANA Cloud Database Administration with SAP HANA Cockpit*\).
    
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
    
    Top 5 statements whose memory consumption was the highest during the last run of the elastic compute node.

    See detailed information about the statements in the *View Logs*, then click the *Statement Logs* tab. See [Monitoring SAP Datasphere](monitoring-sap-datasphere-28910cd.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Out-of-Memory Errors*
    
    </td>
    <td valign="top">
    
    Number of out-of-memory errors that have occurred in tasks and statements related to the elastic compute node during the last run.

    See detailed information about the errors in the *View Logs*, then click the *Statement Logs* tab. See [Monitoring SAP Datasphere](monitoring-sap-datasphere-28910cd.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Memory Distribution*
    
    </td>
    <td valign="top">
    
    Amount of memory allocated to the elastic compute node, if in a running state, broken down between:

    -   *Unused Memory* - Shows the amount of memory available for the elastic compute node.

    -   *Memory Used for Data Replication* - Shows the amount of memory used to store replicated data for the elastic compute node.

    -   *Memory Used for Processing* - Shows the amount of memory used by the processes that are currently running for the elastic compute node. For example: consumption of the queries running on the elastic compute node.


    > ### Note:  
    > If the elastic compute node is not in a running state, no data is displayed.


    
    </td>
    </tr>
    </table>
    
3.  To investigate further, you can:

    -   View statement details by clicking *View Logs* on a card to go to the *Statement Logs* tab, then click the links in the *Statement Details* column. \(see [Statement Logs Tab](monitoring-sap-datasphere-28910cd.md#loio28910cded17a42a0bf16225309cb8bf6__section_statement_tab)\).
    -   View details on a run by clicking *View Logs* on a card to go to the *Task Logs* tab, then click the link in the *Activity* column to open the run in the *Data Integration Monitor* \(see [Managing and Monitoring Data Integration](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/4cbf7c7fc64645bfa364332827557267.html "Users with a space administrator or integrator role can use the Data Integration Monitor app to schedule, run, and monitor data replication and persistence tasks for remote tables and views, track queries sent to remote source systems, and manage other tasks through flows and task chains.") :arrow_upper_right:\).
    -   Navigate to the elastic compute node in the *Space Management* app by clicking *Manage Elastic Compute Node* \(see [Create an Elastic Compute Node](../Creating-and-Configuring-Your-Tenant/create-an-elastic-compute-node-99ad61e.md) and [Run an Elastic Compute Node](../Creating-and-Configuring-Your-Tenant/run-an-elastic-compute-node-34b3585.md)\).

    -   Analyze the performance of the SAP HANA database by clicking *Database Overview \(SAP HANA Cockpit\)* to open the Database Overview page in the SAP HANA Cockpit \(see [The Database Overview Page](https://help.sap.com/docs/hana-cloud/sap-hana-cloud-database-administration-with-sap-hana-cockpit/database-overview-page) in the *SAP HANA Cloud Database Administration with SAP HANA Cockpit*\).





<a name="loio28910cded17a42a0bf16225309cb8bf6__section_i3j_y34_g2c"/>

## Monitor Capacity Units

As a tenant administrator, you can view the consumption of capacity units for various features over time, helping for resource optimization and subscription management.

From the side navigation menu, click <span class="FPA-icons-V3"></span> \(*System Monitor*\)** \> *Capacities*.

View daily consumption for the current month and track usage relative to your subscription, and download detailed hourly data \(see [Monitor Capacities](monitor-capacities-ba3d05b.md)\).



<a name="loio28910cded17a42a0bf16225309cb8bf6__section_apachespark_tasks"/>

## Monitoring File Space Storage Consumption and Apache Spark Application Usage

Monitor the storage consumption for file spaces \(of storage type SAP HANA Data Lake Files\) and their usage of the Apache Spark application for task runs. This allows you to identify high consumption areas and to target specific tasks.

1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(*System Monitor*\), then click the *Object Store* tab.

2.  In the *Spaces* drop-down list of all file spaces, select the file space in the drop-down list that you want to monitor. You can monitor the storage utilization of your selected file space and of all file spaces with the two following cards:


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
    
    *SAP HANA Data Lake Files: Storage Utilization*
    
    </td>
    <td valign="top">
    
    Amount of storage used in terabyte \(TB\) for the selected space.

    > ### Note:  
    > As an administrator, you can see the storage of all spaces even if you aren't a member.

    You can see the space usage of tasks runs in the*Apache Spark: Tasks* table below.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *SAP HANA Data Lake Files: Storage Utilization of All Spaces*
    
    </td>
    <td valign="top">
    
    Amount of storage used in terabyte \(TB\) for all spaces.
    
    </td>
    </tr>
    </table>
    
3.  You can investigate the selected space's tasks further in the *Apache Spark: Tasks* table:
    1.  Select a time frame in the *Date and Time Range* options \(*Single Dates*, *Date Ranges*, *Weeks*, *Months*, or *Custom Options*\).
    2.  The table shows the following information:
        -   *Applications*: Name of the application.
        -   *Number of Tasks*: Total of tasks that ran in the application during the selected time range. Select the line or click <span class="SAP-icons-V5"></span> \(Details\) to show more information about the tasks, such as *Application Configuration* details \(*Executor CPU*, *Executor Memory*,*Driver CPU*, *Driver Memory*, *Maximum CPU*, and *Maximum Memory*\) and *Tasks details* \(*Object Type*, *Task Activity*, and *Number of Tasks*\). Sorting and filtering abilities are available.





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

Date and hour the task has started to run.

</td>
</tr>
<tr>
<td valign="top">

*Duration \(sec\)*

</td>
<td valign="top">

How many seconds the task has run.

</td>
</tr>
<tr>
<td valign="top">

*Object Type*

</td>
<td valign="top">

Type of object that was run in the task. For example: view, remote table, data flow.

</td>
</tr>
<tr>
<td valign="top">

*Activity*

</td>
<td valign="top">

Action that was performed on the object. For example: persist, replicate, execute. You can click on the activity name, which takes you to the *Data Integration Monitor*.

</td>
</tr>
<tr>
<td valign="top">

*Space Name*

</td>
<td valign="top">

Name of the space in which the task is run.

</td>
</tr>
<tr>
<td valign="top">

*Object Name*

</td>
<td valign="top">

Name of the object. Click on the object name to open the object in the *Data Builder*.

</td>
</tr>
<tr>
<td valign="top">

*SAP HANA Peak Memory*

</td>
<td valign="top">

Maximum amount of memory \(in MiB\) the task has used during the runtime in SAP HANA.

> ### Note:  
> You can see this information:
> 
> -   The option *Enable Expensive Statement Tracing* is enabled by default. It traces task exceeding the thresholds specified in <span class="FPA-icons-V3"></span> \(Configuration\) → *Monitoring*.
> 
> -   If the task is run for these objects \(and activities\): views \(persist, remove\_persisted\_data\), remote tables \(replicate, enable\_realtime\), data flows \(execute\) and intelligent lookup \(execute, delete\_data\).
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

Maximum amount of CPU time \(in ms\) the task has used in SAP HANA.

> ### Note:  
> You can see this information:
> 
> -   If the option *Enable Expensive Statement Tracing* is enabled and if the task exceeds the thresholds specified in <span class="FPA-icons-V3"></span> \(Configuration\) → *Monitoring*. See [Configure Monitoring](configure-monitoring-9cd0691.md).
> 
> -   If the task is run for these objects \(and activities\): views \(persist, remove\_persisted\_data\), remote tables \(replicate, enable\_realtime\), data flows \(execute\) and intelligent lookup \(execute, delete\_data\).
> 
> 
> Otherwise, no number is displayed.

> ### Note:  
> CPU time measures the time used by all threads. If it's much higher than the statement's duration, it indicates heavy thread usage. Prolonged high thread usage can lead to resource bottlenecks and task cancellations, so no other tasks should be scheduled then.



</td>
</tr>
<tr>
<td valign="top">

*Records*

</td>
<td valign="top">

Number of records of the target table after the task has finished running.

> ### Note:  
> You can see this information only if the task is run for these objects \(and activities\): views \(persist\), remote tables \(replicate, enable\_realtime\), data flows \(execute\) and intelligent lookup \(execute, delete\_data\). Otherwise, no number is displayed.



</td>
</tr>
<tr>
<td valign="top">

*SAP HANA Used Memory*

</td>
<td valign="top">

Amount of memory \(in MiB\) that is used by the target table in SAP HANA after the task has finished running.

</td>
</tr>
<tr>
<td valign="top">

*SAP HANA Used Disk*

</td>
<td valign="top">

Amount of disk space \(in MiB\) that is used by the target table in SAP HANA after the task has finished running.

</td>
</tr>
<tr>
<td valign="top">

*Status*

</td>
<td valign="top">

Status of the task: completed, failed, running.

</td>
</tr>
<tr>
<td valign="top">

*Substatus*

</td>
<td valign="top">

For tasks with the status “failed”, shows the substatus and a message describing the cause of failure \(see [Understanding Statuses and Substatuses](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/19cb5bdca7c5412da24bf0ac2badeef7.html "When you run an activity (replicate a remote table, persist a view, etc..), the progress of the task is monitored using statuses and substatuses. Statuses and substatuses are available in the relevant editors as well as in the System Monitor.") :arrow_upper_right:\).

</td>
</tr>
<tr>
<td valign="top">

*User*

</td>
<td valign="top">

Name of the user who has run the task.

</td>
</tr>
<tr>
<td valign="top">

*Target Table*

</td>
<td valign="top">

SAP HANA database technical name of the target table.

</td>
</tr>
<tr>
<td valign="top">

*Statements*

</td>
<td valign="top">

View all the statements of the task in the *Statements* tab, if the information is available.

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

Identifier of the run task.

</td>
</tr>
<tr>
<td valign="top">

*Start Date*

</td>
<td valign="top">

Date the task has started to run.

</td>
</tr>
</table>

Cancel a task run by selecting one single task and clicking *Cancel Task*. You can cancel a task run on the following objects:

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

Time \(date and hour\) the statement has started to run.

</td>
</tr>
<tr>
<td valign="top">

*Duration \(ms\)*

</td>
<td valign="top">

How long in milliseconds the statement has run.

</td>
</tr>
<tr>
<td valign="top">

*Object Type*

</td>
<td valign="top">

-   Type of object that was run in the statement \(for example: view, remote table, data flow\).

-   Or area where the statement was run:

    -   MDS - this is an SAP HANA multi-dimensional services \(MDS\) statement, which is caused for example by stories when SAP Analytics Cloud queries SAP Datasphere.

    -   Data Flow - run by a data flow.

    -   Analysis - run by a database analysis user.

    -   Space SQL - run by a database user of a space.

    -   Business Layer Modeling - run in the *Business Builder*.

    -   Data Layer Modeling - run in the data preview of the view editor in the *Data Builder*.

    -   DWC Space Management - run in the *Space Management*, for example, when deploying an object.

    -   DB Usergroup - run by a user of a database user group.

    -   DWC Administration - run for an administration task such as writing a task framework status.

    -   System - any other SAP HANA system statement.





</td>
</tr>
<tr>
<td valign="top">

*Activity*

</td>
<td valign="top">

Action that was performed. For example: update, compile, select.

</td>
</tr>
<tr>
<td valign="top">

*Object Name*

</td>
<td valign="top">

Name of the object for which the task-related statement was run.

</td>
</tr>
<tr>
<td valign="top">

*Schema Name* 

</td>
<td valign="top">

Name of the schema in which the statement is run.

</td>
</tr>
<tr>
<td valign="top">

*SAP HANA Peak Memory*

</td>
<td valign="top">

Maximum amount of memory \(in MiB\) the statement has used during the runtime in SAP HANA.

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

Amount of CPU time \(in ms\) the statement has used in SAP HANA.

> ### Note:  
> You can see the information if the option *Enable Expensive Statement Tracing* is enabled and if the statement exceeds the thresholds specified in <span class="FPA-icons-V3"></span> \(Configuration\) → *Monitoring*. See [Configure Monitoring](configure-monitoring-9cd0691.md).
> 
> Otherwise, no number is displayed.

> ### Note:  
> CPU time measures the time used by all threads. If it's much higher than the statement's duration, it indicates heavy thread usage. Prolonged high thread usage can lead to resource bottlenecks and task cancellations, so no other tasks should be scheduled then.



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

Values of the parameters of the statement that are indicated by the character "?" in the popup that opens when clicking *More* in the *Statement Details* column.

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

-   Name of the elastic compute node if the statement is run on an elastic compute node.

-   Shows a hyphen \(-\) if the statement is run on the main instance.




</td>
</tr>
<tr>
<td valign="top">

*Error Code*

</td>
<td valign="top">

Numeric code of the SQL error if the statement has failed. See [SQL Error Codes](https://help.sap.com/docs/SAP_HANA_PLATFORM/4fe29514fd584807ac9f2a04f6754767/20a78d3275191014b41bae7c4a46d835.html) in the *SAP HANA SQL Reference Guide for SAP HANA Platform*.

</td>
</tr>
<tr>
<td valign="top">

*Error Message*

</td>
<td valign="top">

Description of the SQL error if the statement has failed.

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

Identifier of the statement.

</td>
</tr>
<tr>
<td valign="top">

*Connection ID*

</td>
<td valign="top">

ID used to connect to the database.

</td>
</tr>
<tr>
<td valign="top">

*Start Date*

</td>
<td valign="top">

Date the statement has started to run.

</td>
</tr>
</table>

> ### Note:  
> Data on statements are kept for a time that depends on the thresholds specified in <span class="FPA-icons-V3"></span> \(Configuration\) → *Monitoring* \(see [Configure Monitoring](configure-monitoring-9cd0691.md)\). As a certain number of statements are kept \(30.000 by default\), if very low thresholds are set, the time period may be very low \(for example, only a few hours\). To keep the statements for a longer time, the thresholds should be set accordingly.



<a name="loio28910cded17a42a0bf16225309cb8bf6__section_a4f_vzb_xtb"/>

## Show/Hide, Filter, Sort and Reorder Task and Statement Columns

Control the tables in *Task Logs* and *Statement Logs*:

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

