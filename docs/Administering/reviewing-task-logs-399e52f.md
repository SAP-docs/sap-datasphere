<!-- loio399e52f2b3824026a2c427a346fa792d -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Reviewing Task Logs

Monitor task execution history including start time, duration, resource usage, status, and object details to identify performance issues, resource bottlenecks, troubleshoot failures, and cancel long-running tasks.



## Prerequisites

To monitor task logs, you must have a global role that grants you the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *System Information* \(`-RU-----`\) - To access *Task Logs* in the *Monitoring* app.

The *DW Administrator* role template, for example, grants these privileges. For more information, see [Privileges and Permissions](Managing-Users-and-Roles/privileges-and-permissions-d7350c6.md) and [Standard Application RolesStandard Roles Delivered with SAP Datasphere](Managing-Users-and-Roles/standard-application-rolesstandard-roles-delivered-with-sap-datasphere-a50a51d.md). 



## Reviewing Task Logs

From the side navigation menu, click :desktop_computer: *Monitoring* *\>* <span class="SAP-icons-V5"></span> *Task Logs* . The *Task Logs* app opens.

The app lists the logs of task runs. The table contains the following columns:


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

*Start Date and Time*

</td>
<td valign="top">

Date and hour the task has started to run.

</td>
</tr>
<tr>
<td valign="top">

*Duration*

</td>
<td valign="top">

How long the task has run \(formatted as hh:mm:ss\).

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

Action that was performed on the object. For example: persist, replicate, run. You can click on the activity name, which takes you to the *Data Integration Monitor*.

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

*Space Storage Type*

</td>
<td valign="top">

Either SAP HANA Database \(Disk and In-Memory\) or SAP HANA Data Lake Files.

</td>
</tr>
<tr>
<td valign="top">

*Apache Spark Application*

</td>
<td valign="top">

Name of the application.

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

*SAP HANA Peak Memory \(MB\)*

</td>
<td valign="top">

Maximum amount of memory \(in MiB\) the task has used during the runtime in SAP HANA.

> ### Note:  
> You can see this information:
> 
> -   The option *Enable Expensive Statement Tracing* is enabled by default. It traces task exceeding the thresholds specified in <span class="FPA-icons-V3"></span> \(Configuration\) → *Monitoring*.
> 
> -   If the task is run for these objects \(and activities\): views \(persist, remove\_persisted\_data\), remote tables \(replicate, enable\_realtime\), data flows \(run\) and intelligent lookup \(run, delete\_data\).
> 
> 
> Otherwise, no number is displayed.



</td>
</tr>
<tr>
<td valign="top">

*SAP HANA CPU Time \(ms\)*

</td>
<td valign="top">

Maximum amount of CPU time \(in ms\) the task has used in SAP HANA.

> ### Note:  
> You can see this information:
> 
> -   If the option *Enable Expensive Statement Tracing* is enabled and if the task exceeds the thresholds specified in <span class="FPA-icons-V3"></span> \(Configuration\) → *Monitoring*. See [Configure Monitoring](configure-monitoring-9cd0691.md).
> 
> -   If the task is run for these objects \(and activities\): views \(persist, remove\_persisted\_data\), remote tables \(replicate, enable\_realtime\), data flows \(run\) and intelligent lookup \(run, delete\_data\).
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
> You can see this information only if the task is run for these objects \(and activities\): views \(persist\), remote tables \(replicate, enable\_realtime\), data flows \(run\) and intelligent lookup \(run, delete\_data\). Otherwise, no number is displayed.



</td>
</tr>
<tr>
<td valign="top">

*SAP HANA Used Memory \(MB\)*

</td>
<td valign="top">

Amount of memory \(in MiB\) that is used by the target table in SAP HANA after the task has finished running.

</td>
</tr>
<tr>
<td valign="top">

*SAP HANA Used Disk \(MB\)* 

</td>
<td valign="top">

Amount of disk space \(in MiB\) that is used by the target table in SAP HANA after the task has finished running.

</td>
</tr>
<tr>
<td valign="top">

*Apache Spark Peak Memory \(MB\)*

</td>
<td valign="top">

Maximum amount of memory used across all executors and the driver during an Apache Spark job's lifetime. It reflects the highest demand for memory resources at any point during the execution. If the memory usage exceeds the maximum memory specified in the Apache Spark application configuration, it is recommended to consider a higher configuration or increase the size of the executors using a custom configuration.

</td>
</tr>
<tr>
<td valign="top">

*Apache Spark Peak Memory \(%\)*

</td>
<td valign="top">

Percentage overview of the peak memory consumption relative to the size of the Spark application configuration. It helps you understand how efficiently the application is using its allocated memory and whether adjustments are needed to optimize performance.

</td>
</tr>
<tr>
<td valign="top">

*Apache Spark Spill to Disk \(MB\)*

</td>
<td valign="top">

Amount of data that has been spilled to disk \(in MiB\). It ensures that applications do not exceed their memory limits, causing data to be temporarily stored on disk. High spill rates can lead to performance bottlenecks, so monitoring this metric is crucial for identifying memory-related issues.

</td>
</tr>
<tr>
<td valign="top">

*Apache Spark Number of Cores*

</td>
<td valign="top">

Number of CPU cores utilized by the Spark application. It helps you assess whether the application is efficiently using available compute resources and if there is a need to adjust the number or cores allocated to improve performance.

</td>
</tr>
<tr>
<td valign="top">

*Apache Spark Used Compute Time \(ms\)*

</td>
<td valign="top">

Total compute time used by the Spark application \(in ms\). It gives you insight into the duration of the application's run, which is useful for performance analysis and resource planning.

</td>
</tr>
<tr>
<td valign="top">

*Apache Spark Used Compute \(%\)*

</td>
<td valign="top">

Percentage of compute resources used by the Spark application relative to its configuration. It helps you evaluate the efficiency of resource utilization and identify potential areas for optimization.

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

For tasks with the status “failed”, shows the substatus and a message describing the cause of failure \(see [Understanding Statuses and Substatuses](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/19cb5bdca7c5412da24bf0ac2badeef7.html "When you run an activity (replicate a remote table, persist a view, etc..), the progress of the task is monitored using statuses and substatuses. Statuses and substatuses are available in the relevant editors as well as in the  Monitoring apps.") :arrow_upper_right:\).

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

Shows if the task has an out-of-memory error \(a timestamp is then displayed\) or not \(nothing is displayed\). It is either empty \(instead of No\) and if out of memory occurs then we dispaly the timestamp of the event.

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
<tr>
<td valign="top">

*Apache Spark Resource ID*

</td>
<td valign="top">

Unique identifier for the reosources used by the Spark application. It can be helpful for debugging purposes, allowing you to trace specific resource allocations and usage patterns when troubleshooting issues.

</td>
</tr>
</table>



## Canceling a Task

Cancel a task run by selecting one single run and clicking *Cancel Task*. You can cancel a task run on the following objects:

-   Transformation flow
-   Remote table
-   Data flow
-   Task chain

Canceling a task run may be required when it takes too long or if the run impacts negatively other runs by taking too many resources away. Canceling a task via the *Task Logs* monitor app is the most reliable option. Its access isn't restricted when resource consumption is too high \(as in the *Data Integration* monitor app\), and it is the fastest way to cancel a task \(compared to the *Database Explorer*\). The data is rolled back and restored to the state that existed before the task run was initially triggered.

> ### Note:  
> -   Data on tasks are kept for the time specified in <span class="FPA-icons-V3"></span> \(Configuration\) → *Tasks*.
> -   You may not be able to cancel a task via the *Data Integration Monitor* or the *Database Explorer* when resource consumption is too high. You will always be able to cancel a task via the *System Monitor*.



## Show/Hide, Filter, Sort and Reorder Columns

You can control the display of entries as follows:

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
        <tr>
        <td valign="top">
        
        *Space Storage Type*
        
        </td>
        <td valign="top">
        
        Select one type of space storage: *SAP HANA Database* or *SAP HANA Data Lake Files*.
        
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

