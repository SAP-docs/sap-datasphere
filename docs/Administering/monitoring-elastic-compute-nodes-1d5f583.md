<!-- loio1d5f583f3b8d4abdae872a363ca3a94e -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Monitoring Elastic Compute Nodes

Monitor elastic compute node performance by reviewing key metrics including configuration, run details, CPU/memory usage, uptime, top statements, and errors to investigate issues and optimize resource allocation.



## Prerequisites

To monitor elastic compute nodes, you must have a global role that grants you the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *System Information* \(`-RU-----`\) - To access *Elastic Compute Nodes* in the *Monitoring* app.

The *DW Administrator* role template, for example, grants these privileges. For more information, see [Privileges and Permissions](Managing-Users-and-Roles/privileges-and-permissions-d7350c6.md) and [Standard Application RolesStandard Roles Delivered with SAP Datasphere](Managing-Users-and-Roles/standard-application-rolesstandard-roles-delivered-with-sap-datasphere-a50a51d.md). 



## Reviewing Elastic Compute Nodes

After creating an elastic compute node \(see [Create an Elastic Compute Node](Creating-and-Configuring-Your-Tenant/create-an-elastic-compute-node-99ad61e.md)\), monitor its key figures.

1.  In the side navigation area, click :desktop_computer: *Monitoring* \> <span class="FPA-icons-V3"></span> *Elastic Compute Nodes* .
2.  Select the node you want to monitor from the drop down list. If a single elastic compute node exists, its information is automatically displayed. If several nodes exist, you must select one to see its information.

3.  Review elastic compute node key figures or identify issues with the following cards:


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

    -   Status, such as *Ready* or *Running* \(see [Run an Elastic Compute Node](Creating-and-Configuring-Your-Tenant/run-an-elastic-compute-node-34b3585.md)\).

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
    
    Average amount of memory consumed \(in GB\) during the latest or previous run of the elastic compute node. The trend icon \(up or down arrow\) shows if the percentage is higher or lower than the previous run.

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

    To see detailed information about the statements, click *View Logs*, which takes you to the *Expensive Statement Logs* app \(see [Reviewing Expensive Statement Logs](reviewing-expensive-statement-logs-4f18e74.md)\).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Out-of-Memory Errors*
    
    </td>
    <td valign="top">
    
    Number of out-of-memory errors that have occurred in tasks and statements related to the elastic compute node during the last run.

    To see detailed information about the errors, click *View Logs*, which takes you to the *Expensive Statement Logs* app \(see [Reviewing Expensive Statement Logs](reviewing-expensive-statement-logs-4f18e74.md)\).
    
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
    
4.  To investigate further, you can:

    -   View statement details by clicking *View Logs* on a card to go to the *Expensive Statement Logs* monitor app, then click the links in the *Statement Details* column. \(see [Reviewing Expensive Statement Logs](reviewing-expensive-statement-logs-4f18e74.md)\).
    -   View details on a run by clicking *View Logs* on a card to go to the *Task Logs* monitor app, then click the link in the *Activity* column to open the run in the *Data Integration Monitor* \(see [Managing and Monitoring Data Integration](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/4cbf7c7fc64645bfa364332827557267.html "Users with a space administrator or integrator role can use the  Data Integration app to schedule, run, and monitor data replication and persistence tasks for remote tables and views, track queries sent to remote source systems, and manage other tasks through flows and task chains.") :arrow_upper_right:\).
    -   Navigate to the elastic compute node in the *Space Management* app by clicking *Manage Elastic Compute Node* \(see [Create an Elastic Compute Node](Creating-and-Configuring-Your-Tenant/create-an-elastic-compute-node-99ad61e.md) and [Run an Elastic Compute Node](Creating-and-Configuring-Your-Tenant/run-an-elastic-compute-node-34b3585.md)\).

    -   Analyze the performance of the SAP HANA database by clicking *Database Overview \(SAP HANA Cockpit\)* to open the Database Overview page in the SAP HANA Cockpit \(see [The Database Overview Page](https://help.sap.com/docs/hana-cloud/sap-hana-cloud-database-administration-with-sap-hana-cockpit/database-overview-page) in the *SAP HANA Cloud Database Administration with SAP HANA Cockpit*\).



