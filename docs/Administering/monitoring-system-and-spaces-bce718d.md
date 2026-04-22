<!-- loiobce718d12a2540f081510fd097433620 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Monitoring System and Spaces

Monitor disk storage, memory, task, and statement metrics to track tenant resource usage, identify storage risks, investigate failed tasks and expensive operations, and resolve performance issues before outages occur.



## Prerequisites

To monitor the system performance and issues across all spaces, you must have a global role that grants you the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *System Information* \(`-RU-----`\) - To access *System and Spaces* in the *Monitoring* app.

The *DW Administrator* role template, for example, grants these privileges. For more information, see [Privileges and Permissions](Managing-Users-and-Roles/privileges-and-permissions-d7350c6.md) and [Standard Application RolesStandard Roles Delivered with SAP Datasphere](Managing-Users-and-Roles/standard-application-rolesstandard-roles-delivered-with-sap-datasphere-a50a51d.md). 



<a name="loiobce718d12a2540f081510fd097433620__section_monitor_disk_storage_usage"/>

## Monitor Disk Storage Usage

1.  Click :desktop_computer: *Monitoring* in the side navigation to open the monitoring menu, and click <span class="SAP-icons-V5"></span> *System and Spaces*  to access the *System and Spaces* monitoring *Dashboard*.
2.  Review your SAP Datasphere tenant disk storage capacity and its current utilization in the SAP HANA database and identify risks of storage-related outages in the *Disk Storage Usage* card.


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
    
    *Type*
    
    </td>
    <td valign="top">
    
    Shows the following usage types:

    -   DATA - Data stored in all SAP Datasphere spaces.
    -   TRACE and LOG - Trace and log data needed for SAP HANA internal processes.

    > ### Note:  
    > If the SAP HANA database is setup in single volume, the 3 types DATA, TRACE and LOG are stored on the same volume. If SAP HANA database is setup in multi-volume, the 2 types DATA and TRACE are stored on one volume and LOG is stored on another volume.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Usage*
    
    </td>
    <td valign="top">
    
    Shows in a bar chart the following amounts out of the tenant's total amount of disk storage:

    -   The amount of reserved data \(in grey\), which represents 15%.
    -   The amount of data used by all types of data \(DATA, TRACE, LOG\).


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Used*
    
    </td>
    <td valign="top">
    
    Shows the amount of disk storage already used.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Usable*
    
    </td>
    <td valign="top">
    
    Shows the amount of disk storage that can be used.

    > ### Note:  
    > To prevent your tenant from storage-related outages, we reserve 15% of the tenant's total amount of disk storage as a buffer. Therefore:
    > 
    > -   The amount in the *Usable* column represents 85% of the tenant's total amount of disk storage \(displayed in the *Total* column\).
    > -   SAP Datasphere locks all spaces if the entire amount in the *Usable* column is used \(see [Unlock a Locked Space](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/c05b6a6d06db427dbdd3041d61fd5840.html "When a space exceeds its assigned storage or when the audit logs enabled in the space consume too much disk storage, the space is automatically locked after 60 minutes if you do not free up space. Also, when the tenant disk usage has reached a critical threshold, all spaces are automatically locked to protect your tenant from storage-related outages.") :arrow_upper_right:\).


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Total*
    
    </td>
    <td valign="top">
    
    Shows the total amount of disk storage that you've chosen for your tenant \(see [Configure the Size of Your SAP Datasphere Tenant](Creating-and-Configuring-Your-Tenant/configure-the-size-of-your-sap-datasphere-tenant-33f8ef4.md)\).

    To protect your tenant from storage-related outages, we reserve 15% of the tenant's total amount of disk storage as a buffer.
    
    </td>
    </tr>
    </table>
    
    > ### Note:  
    > The card uses the SAP HANA system view M\_DISKS, which reflects the effective file system sizes \(see [M\_DISKS System View](https://help.sap.com/docs/hana-cloud-database/sap-hana-cloud-sap-hana-database-sql-reference-guide/m-disks-system-view)\).

3.  To manage your tenant and prevent it from storage-related outages, see [Manage Tenant Disk Storage](manage-tenant-disk-storage-27d4c68.md).



<a name="loiobce718d12a2540f081510fd097433620__section_irf_214_1cc"/>

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

    -   *Other Data*: Includes data stored in database user group schemas \(see [Creating a Database User Group](Creating-a-Database-User-Group/creating-a-database-user-group-1097a47.md)\) and SAP HANA data \(such as statistics schemas\).

    -   *Administrative Data*: Data used to administer the tenant and all spaces \(such as space quota, space version\) and central schemas information \(DWC\_GLOBAL, DWC\_GLOBAL\_LOG, DWC\_TENANT\_OWNER\).



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Disk Used by Spaces for Storage*
    
    </td>
    <td valign="top">
    
    Total amount of disk storage used out of the total amount of usable disk storage. You can see a breakdown of this amount in the card *Disk Storage Used*.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Memory Used by Spaces for Storage*
    
    </td>
    <td valign="top">
    
    Total amount of memory storage used out of the total amount of memory storage.

    > ### Note:  
    > If the storage is set to *In-Memory* for some tables, this value includes the quantity of memory required to fully load the local tables data in-memory even if, for reasons of memory optimization, SAP HANA has currently only partially loaded the data in-memory.


    
    </td>
    </tr>
    </table>
    
2.  To investigate issues in particular spaces:
    1.  In the side navigation area, click ![](images/Space_Management_a868247.png) \(*Space Management*\).
    2.  Display the list of spaces in the table layout and order by column. For example, you can display at the top of the table the spaces that use the highest amount of storage by choosing the descending order for the column *Used Storage*.
    3.  Open a space and click *Monitor* in the space details app to see the storage amount assigned to and used by the space \(see [Monitor Your Space Storage Consumption](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/94fe6c13f6a340288cd50ee355566591.html "See the storage amount assigned to and used by your space.") :arrow_upper_right:\).




<a name="loiobce718d12a2540f081510fd097433620__section_qyl_sc4_ccc"/>

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
    
2.  Click *View Logs* in a card to go to the *Task Logs* tab, which displays information filtered on the card criteria \(see [Reviewing Task Logs](reviewing-task-logs-399e52f.md)\).
3.  For the spaces you have access to \(via scoped roles\), click the links in the following columns:
    -   *Activity* - opens the run in the *Data Integration Monitor* \(see [Managing and Monitoring Data Integration](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/4cbf7c7fc64645bfa364332827557267.html "Users with a space administrator or integrator role can use the  Data Integration app to schedule, run, and monitor data replication and persistence tasks for remote tables and views, track queries sent to remote source systems, and manage other tasks through flows and task chains.") :arrow_upper_right:\).

    -   *Object Name* - opens the editor of the object.



> ### Note:  
> If your SAP Datasphere tenant is enabled for job & automation monitoring in SAP Cloud ALM, you can monitor the tasks run or scheduled in SAP Datasphere, from the *Job & Automation Monitoring* app in SAP Cloud ALM. See [Job & Automation Monitoring](https://help.sap.com/docs/cloud-alm/applicationhelp/job-automation-monitoring) in the *SAP Cloud ALM - Application Help*.



<a name="loiobce718d12a2540f081510fd097433620__section_t2q_sc4_ccc"/>

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
    
    Schemas in which out-of-memory errors have occurred in the last 7 days because the statement limits have been exceeded. Set the statement limits for spaces, see [Set Priorities and Statement Limits for Spaces or Groups](Creating-Spaces-and-Allocating-Storage/set-priorities-and-statement-limits-for-spaces-or-groups-d66ac1e.md).
    
    </td>
    </tr>
    </table>
    
2.  Click *View Logs* in a card to go to the *Statement Logs* to see information filtered on the card criteria. See [Reviewing Expensive Statement Logs](reviewing-expensive-statement-logs-4f18e74.md).
3.  Click the links in the *Statement Details* column for further details.



<a name="loiobce718d12a2540f081510fd097433620__section_tt5_sc4_ccc"/>

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

For more information about admission control thresholds, see [Set Priorities and Statement Limits for Spaces or Groups](Creating-Spaces-and-Allocating-Storage/set-priorities-and-statement-limits-for-spaces-or-groups-d66ac1e.md).



<a name="loiobce718d12a2540f081510fd097433620__monitoringobjectstore"/>

## Monitor Object Store Storage and Apache Spark Tasks

Monitor storage consumption for file spaces and Apache Spark application task runs to identify high consumption areas and target specific tasks for optimization.

1.  In the side navigation area, click :desktop_computer: *Monitoring* \> <span class="SAP-icons-V5"></span> *System and Spaces*  \> *Object Store* tab.

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
    
3.  You can investigate the selected file space's local table and transformation flow tasks further in the *Apache Spark: Tasks* table:
    1.  Select a time frame in the *Date and Time Range* options \(*Single Dates*, *Date Ranges*, *Weeks*, *Months*, or *Custom Options*\).
    2.  The table shows the application name, the total of tasks that ran in the application during the selected time range. Select the line or click <span class="SAP-icons-V5"></span> \(Details\) to show more information about the task.


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
        
        *Application Name*
        
        </td>
        <td valign="top">
        
        The name of the Apache Spark application is displayed in bold at the top of the details.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *Application Configuration*
        
        </td>
        <td valign="top">
        
        Displays various configuration parameters of the Apache Spark application:

        -   *Executor CPU*: The CPU resources allocated to the executors.
        -   *Executor Memory*: The memory allocated to the executors.
        -   *Driver CPU*: The CPU resources allocated to the driver.
        -   *Driver Memory*: The memory allocated to the driver.
        -   *Maximum CPU*: The maximum CPU resources that can be utilized.
        -   *Maximum Memory*: The maximum memory that can be utilized.


        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *Tasks*
        
        </td>
        <td valign="top">
        
        Provides information on task activities:

        -   *Object Type*: Type of object that was run in the task. For example: local table or transformation flow.
        -   *Task Activity*: Action that was performed on the object. For example: persist, replicate, run.
        -   *Number of Tasks*: The total number of tasks ran by the selected application during the defined time frame.

        Use filters to refine your task search:

        -   *Search* bar: Enter the name of an object type or a task activity.
        -   <span class="SAP-icons-V5"></span> \(Sort Table\): Define a sorting order by selecting a *Sort Order* \(*Ascending* or *Descending*\) and a *Sort By* category \(*Object Type*, *Task Activity*, *Number of Tasks*\).
        -   <span class="SAP-icons-V5"></span> \(Filter\): Filter on the task list by selecting an *Object Type* or *Task Activity*.


        
        </td>
        </tr>
        </table>
        


