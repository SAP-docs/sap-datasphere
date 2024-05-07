<!-- loio28910cded17a42a0bf16225309cb8bf6 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Monitoring SAP Datasphere

Administrators have access to various monitoring logs and views, and can create database analysis users, if necessary, to help troubleshoot issues.

This topic contains the following sections:

-   [Monitoring Out-of-Memory Errors and Other Statement-Related Information](monitoring-sap-datasphere-28910cd.md#loio28910cded17a42a0bf16225309cb8bf6__section_zn2_nyr_c5b)
-   [Dashboard](monitoring-sap-datasphere-28910cd.md#loio28910cded17a42a0bf16225309cb8bf6__section_k1v_2jx_b5b)
-   [Tasks](monitoring-sap-datasphere-28910cd.md#loio28910cded17a42a0bf16225309cb8bf6__section_ocq_twn_wtb)
-   [Statements](monitoring-sap-datasphere-28910cd.md#loio28910cded17a42a0bf16225309cb8bf6__section_fyv_twn_wtb)
-   [Show/Hide, Filter, Sort and Reorder Task and Statement Columns](monitoring-sap-datasphere-28910cd.md#loio28910cded17a42a0bf16225309cb8bf6__section_a4f_vzb_xtb)

Click <span class="FPA-icons-V3"></span> \(*System Monitor*\) to access the main monitoring tool. The *System Monitor* allows to monitor the performance of your system and identify storage, task, out-of-memory, and other issues across all spaces.

For example, you can see all the errors \(such as failed tasks and out-of-memory errors\) that occurred yesterday or the top five statements with the highest peak memory consumption.

> ### Note:  
> For optimal performance, it is recommended that you consider staggering the scheduled run time of tasks such as data flows and task chains that may contain these tasks. There is a limit on how many tasks can be started at the same time. If you come close to this limit, scheduled task runs may be delayed and, if you go beyond the limit, some scheduled task runs might even be skipped.



<a name="loio28910cded17a42a0bf16225309cb8bf6__section_zn2_nyr_c5b"/>

## Monitoring Out-of-Memory Errors and Other Statement-Related Information

You can monitor out-of-memory errors and other information that are related to SAP HANA database SQL statements, depending on what you've specified in <span class="FPA-icons-V3"></span> \(Configuration\) → *Monitoring*:

-   If *Enable Expensive Statement Tracing* is not selected, then in *System Monitor* \> *Dashboard*, you cannot see the widgets about out-of-memory errors and about other information related to statements. For example, you cannot see the widgets: *Out-of-Memory Errors*, *Top 5 Statements by Processing Memory Consumption*.

-   If *Enable Expensive Statement Tracing* is not selected and none of the threshold options is selected, then in the tables of *System Monitor* \> *Logs*, you cannot see any information about out-of-memory errors and about other information related to statements. For example, no information is displayed in the columns *Peak Memory \(MiB\)* and *Peak CPU \(ms\)*.


A maximum of 30.000 records by default \(a number that you can change\) are stored for expensive statements. It means that the thresholds also determine how long you are able to see the statements. If the thresholds are very low, many statements are traced in a short timeframe.

For this reason, we recommend the following:

-   *Threshold Duration* - Specify 5 seconds.

-   *Threshold Memory* - Specify 1.000 MB.

-   *Threshold CPU Time* - Do not select this option.


You can change the maximum number of records to trace more data in the *System Monitor*. For example, if about 5 days are traced in the expensive statement tables and you don’t want to change the thresholds, you can double the number of records in *In-Memory Tracing Records* so that about 10 days are traced.

For more information on enabling and configuring expensive statement tracing, see [Analyze Monitoring Data in a Space](analyze-monitoring-data-in-a-space-9cd0691.md).



<a name="loio28910cded17a42a0bf16225309cb8bf6__section_k1v_2jx_b5b"/>

## Dashboard

The out-of-memory widgets and top-memory consumption widgets help you to identify issues. You can see detailed information about the issues by clicking *View Logs*, which takes you to the *Logs* tab. For example, you can find out if tasks have to be scheduled at another time so that high-memory consuming tasks do not run at the same time. If single tasks consume too much memory, some additional views may need to be persisted or the view partitioning may need to be used to lower the memory consumption.

The following information is available in the *Dashboard* tab:

-   *Disk Used by Spaces for Storage* - Shows the total amount of disk storage used in all spaces, out of the total amount of disk storage assigned to all spaces.

    In *Disk Storage Used*, you can see a breakdown between:

    -   *Data in Spaces*: All data that is stored in spaces.

    -   *Audit Log Data*: Data related to audit logs \(see [Audit Logging](https://help.sap.com/viewer/0c3780ad05fd417fa27b98418535debd/cloud/en-US/c78a7c2a3cec4b0897db294d74e00d9b.html "Audit logs are records of read or change actions performed in the database. They allow you to see who did what and when.") :arrow_upper_right:\).

        > ### Note:  
        > Audit logs can grow quickly and consume a great deal of disk storage \(see [Delete Audit Logs](delete-audit-logs-589fa42.md)\).

    -   *Other Data*: Includes data stored in database user group schemas \(see [Creating a Database User Group](../Creating-a-Database-User-Group/creating-a-database-user-group-1097a47.md)\) and SAP HANA data \(such as statistics schemas\).

    -   *Administrative Data*: Data used to administer the tenant and all spaces \(such as space quota, space version\). Includes all information stored in the central schemas \(DWC\_GLOBAL, DWC\_GLOBAL\_LOG, DWC\_TENANT\_OWNER\).


-   *Memory Used by Spaces for Storage* - Shows the total amount of memory storage used in all spaces, out of the total amount of memory storage assigned to all spaces.
-   *Disk Assigned to Spaces for Storage* - Shows the total amount of disk storage assigned to all spaces.
-   *Memory Assigned to Spaces for Storage* - Shows the total amount of memory storage assigned to all spaces.

For each of the key indicator widgets listed below, you can see detailed information by clicking the link *View Logs*, which takes you to the *Logs* tab.


<table>
<tr>
<th valign="top">

Widget

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Failed Tasks*

*Last 24 Hours*

</td>
<td valign="top">

Shows the number of tasks that have failed in the last 24 hours with a trend icon \(up or down arrow\) indicating if there are more or less failed tasks than the day before.

</td>
</tr>
<tr>
<td valign="top">

*Out-of-Memory Errors* 

*Last 24 Hours*

</td>
<td valign="top">

Shows the number of out-of-memory errors that have occurred in tasks and statements in the last 24 hours.

</td>
</tr>
<tr>
<td valign="top">

*Top 5 Out-of-Memory Errors \(Workload Class\) by Space*

*Last 7 Days*

</td>
<td valign="top">

Shows the schemas in which out-of-memory errors have occurred in the last 7 days because the statement limits have been exceeded.

You can set the statement limits for a space in the *Workload Management* area of a space.

</td>
</tr>
<tr>
<td valign="top">

*Out-of-Memory Errors \(MDS Requests\)*

*Last 7 Days*

</td>
<td valign="top">

Shows the out-of-memory errors that are related to SAP HANA multi-dimensional services \(MDS\) requests, which is used for example for SAP Analytics Cloud consumption.

</td>
</tr>
<tr>
<td valign="top">

*Failed Tasks* 

*Last 7 Days*

</td>
<td valign="top">

Shows the number of failed tasks by day for the last 7 days.

</td>
</tr>
<tr>
<td valign="top">

*Out-of-Memory Errors*

*Last 7 Days*

</td>
<td valign="top">

Shows the number of out-of-memory errors that have occurred in tasks and statements, by day for the last 7 days.

</td>
</tr>
<tr>
<td valign="top">

*Top 5 Tasks by Run Duration*

*Last 24 Hours*

</td>
<td valign="top">

Shows the 5 tasks whose run duration time was the longest in the last 24 hours.

</td>
</tr>
<tr>
<td valign="top">

*Top 5 Tasks by Run Duration*

*Last 48 Hours*

</td>
<td valign="top">

Shows the 5 tasks whose run duration time was the longest in the last 48 hours.

</td>
</tr>
<tr>
<td valign="top">

*Top 5 Tasks by Processing Memory Consumption*

*Last 24 Hours*

</td>
<td valign="top">

Shows the 5 tasks whose processing memory consumption was the highest in the last 24 hours.

</td>
</tr>
<tr>
<td valign="top">

*Top 5 Tasks by Processing Memory Consumption*

*Last 48 Hours*

</td>
<td valign="top">

Shows the 5 tasks whose processing memory consumption was the highest in the last 48 hours.

</td>
</tr>
<tr>
<td valign="top">

*Top 5 Statements by Processing Memory Consumption*

*Last 24 Hours*

</td>
<td valign="top">

Shows the 5 statements whose processing memory consumption was the highest in the last 24 hours.

</td>
</tr>
<tr>
<td valign="top">

*Top 5 Statements by Processing Memory Consumption*

*Last 48 Hours*

</td>
<td valign="top">

Shows the 5 statements whose processing memory consumption was the highest in the last 48 hours.

</td>
</tr>
<tr>
<td valign="top">

*Top 5 MDS Requests by Processing Memory Consumption*

*Last 24 Hours*

</td>
<td valign="top">

Shows the 5 SAP HANA multi-dimensional services \(MDS\) requests \(used for example in SAP Analytics Cloud consumption\), whose processing memory consumption is the highest.

</td>
</tr>
<tr>
<td valign="top">

*Admission Control Rejection Events*

*Last 24 Hours*

</td>
<td valign="top">

Shows the number of statements that have been rejected in the last 24 hours because they’ve exceeded the threshold percentage of CPU usage. A trend icon \(up or down arrow\) indicates if there are more or less rejected statements than the day before.

</td>
</tr>
<tr>
<td valign="top">

*Admission Control Queuing Events*

*Last 24 Hours*

</td>
<td valign="top">

Shows the number of statements that have been queued in the last 24 hours because they’ve exceeded the threshold percentage of CPU usage. A trend icon \(up or down arrow\) indicates if there are more or less queued statements than the day before.

</td>
</tr>
<tr>
<td valign="top">

*Admission Control Rejection Events*

*Last 7 Days*

</td>
<td valign="top">

Shows the number of statements that have been rejected in the last 7 days because they’ve exceeded the threshold percentage of CPU usage.

</td>
</tr>
<tr>
<td valign="top">

*Admission Control Queuing Events*

*Last 7 Days*

</td>
<td valign="top">

Shows the number of statements that have been queued in the last 7 days because they’ve exceeded the threshold percentage of CPU usage.

</td>
</tr>
<tr>
<td valign="top">

*Top 5 Admission Control Rejection Events by Space*

*Last 7 Days*

</td>
<td valign="top">

Shows the 5 spaces with the highest number of rejected statements in the last 24 hours.

> ### Note:  
> A space that has been deleted is prefixed with an asterisk character.



</td>
</tr>
<tr>
<td valign="top">

*Top 5 Admission Control Queuing Events by Space*

*Last 7 Days*

</td>
<td valign="top">

Shows the 5 spaces with the highest number of queued statements in the last 24 hours.

> ### Note:  
> A space that has been deleted is prefixed with an asterisk character.



</td>
</tr>
</table>

> ### Note:  
> -   To investigate why statements are being queued or rejected, you can click *Open SAP HANA Cockpit* in the widgets dedicated to admission contol. If you've created a database analysis user, you're connected to the SAP HANA Cockpit without entering your credentials \(see [Create a Database Analysis User to Debug Database Issues](create-a-database-analysis-user-to-debug-database-issues-c28145b.md).
> 
> -   For more information about admission control thresholds, see [Set a Priority and Statement Limits for a Space](../Creating-Spaces-and-Allocating-Storage/set-a-priority-and-statement-limits-for-a-space-d66ac1e.md).



<a name="loio28910cded17a42a0bf16225309cb8bf6__section_ocq_twn_wtb"/>

## Tasks

In *Logs* \> *Tasks*, the table shows the following information:


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
> -   If the option *Enable Expensive Statement Tracing* is enabled and if the task exceeds the thresholds specified in <span class="FPA-icons-V3"></span> \(Configuration\) → *Monitoring*.
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

Shows the amount of CPU time \(in ms\) the task has used in SAP HANA.

> ### Note:  
> You can see this information:
> 
> -   If the option *Enable Expensive Statement Tracing* is enabled and if the task exceeds the thresholds specified in <span class="FPA-icons-V3"></span> \(Configuration\) → *Monitoring*.
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

Shows a link you can click to view all the statements of the task in the *Statements* table.

> ### Note:  
> -   You can see this information if the option *Enable Expensive Statement Tracing* is enabled in <span class="FPA-icons-V3"></span> \(Configuration\) → *Monitoring*.
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
</table>

> ### Note:  
> Data on tasks are kept for the time specified in <span class="FPA-icons-V3"></span> \(Configuration\) → *Tasks*.



<a name="loio28910cded17a42a0bf16225309cb8bf6__section_fyv_twn_wtb"/>

## Statements

In *Logs* \> *Statements*, the table shows the following information, depending on what you've specified in <span class="FPA-icons-V3"></span> \(Configuration\) → *Monitoring*:

-   If the option *Enable Expensive Statement Tracing* is disabled, then the *Statements* tab is disabled.

-   If the option *Enable Expensive Statement Tracing* is enabled, you can see all the database statements that exceed the specified thresholds.



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
> You can see the information if the option *Enable Expensive Statement Tracing* is enabled and if the statement exceeds the thresholds specified in <span class="FPA-icons-V3"></span> \(Configuration\) → *Monitoring*.
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
> You can see the information if the option *Enable Expensive Statement Tracing* is enabled and if the statement exceeds the thresholds specified in <span class="FPA-icons-V3"></span> \(Configuration\) → *Monitoring*.
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
> For MDS queries - If you’ve enabled the tracing of MDS information \(see [Analyze Monitoring Data in a Space](analyze-monitoring-data-in-a-space-9cd0691.md)\), the payload of the MDS query that is run by SAP Analytics Cloud is displayed. If identified in the payload, the following information is also displayed: story ID, story name and data sources. You can copy or download the displayed information.



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

Shows if the statement has an out-of-memory error \("Yes" is then displayed\) or not \("No" is then displayed\).

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
</table>

> ### Note:  
> Data on statements are kept for a time that depends on the thresholds specified in <span class="FPA-icons-V3"></span> \(Configuration\) → *Monitoring*. As a certain number of statements are kept \(30.000 by default\), if very low thresholds are set, the time period may be very low \(for example, only a few hours\). To keep the statements for a longer time, the thresholds should be set accordingly.



<a name="loio28910cded17a42a0bf16225309cb8bf6__section_a4f_vzb_xtb"/>

## Show/Hide, Filter, Sort and Reorder Task and Statement Columns

You can control the tables in *Tasks* and *Statements* in the following ways:

-   Reorder the columns by drag and drop.
-   Sort on a column by clicking the column header and then clicking <span class="SAP-icons-V5"></span> \(Sort Ascending\) or <span class="SAP-icons-V5"></span> \(Sort Descending\).
-   Filter on a column by clicking the column header, then clicking <span class="FPA-icons-V3"></span> \(Filter\)

    The *Define Filter* dialog opens and advanced filtering options are available:

    1.  Chose the appropriate section for your filter. If your filter is meant to include data in the table \(you could say "I want my Data Preview to show"\), add your filter in the *Include* section. If your filter is meant to exclude data from the table \(you could say "I want my Data Preview to hide"\), add your filter in the *Exclude* section. When in the appropriate section, click <span class="FPA-icons-V3"></span> \(Add Filter\) to add a filter.
    2.  Select a column to filter on, a filtering option, and a value. You can add several filters. Click *OK* to apply the filter\(s\). The currently applied filters are displayed above the table.

        > ### Example:  
        > To only see the tasks that have failed on remote tables, in the *Include* area, select the column *Object Type*, then the filtering value *contains* and enter "REMOTE". Then, add a filter, select the column *Status*, then the filtering value *contains* and enter "FAILED". Once applied, the filter is displayed above the table.

        > ### Note:  
        > -   The filtering options available depend on the data type of the column you filter on.
        > -   Filters applied to text columns are case-sensitive.
        > -   You can enter filter or sort values in multiple columns.
        > -   Previewing a SQL view isn't possible if one of the view's objects is shared from another space and has an input parameter.
        > 
        > -   To increase performance, only the first 1,000 rows are displayed. Use filters to find the data you are looking for. Filters are applied to all rows, but only the first filtered 1,000 rows are displayed.

        > ### Note:  
        > If you filter on one of the following columns and you enter a number, use the “.” \(period\) character as the decimal separator, regardless of the decimal separator used in the number formatting that you’ve chosen in the general user settings \(*Settings* \> *Language & Region*\): *SAP HANA Peak Memory*, *SAP HANA CPU Time*, *SAP HANA Used Memory* and *SAP HANA Used Disk*.

    3.  Click *Clear Filter* in the filter strip or <span class="FPA-icons-V3"></span> \(Remove Filter\)in the *Define Filter* dialog to remove the filter.

-   Show or hide columns by clicking :gear: to open the *Columns Settings* dialog, selecting columns as appropriate. To return to the default preview columns, click *Reset*.
-   Refresh the table at any time by clicking *Refresh*.

