<!-- loio19cb5bdca7c5412da24bf0ac2badeef7 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Understanding Statuses and Substatuses

When you run an activity \(replicate a remote table, persist a view, etc..\), the progress of the task is monitored using statuses and substatuses. Statuses and substatuses are available in the relevant editors as well as in the *System Monitor*.

InSAP Datasphere , the activities can take a minimum of 3 main statuses:

-   *Running* or *Loading*: The task is currently running.
-   *Completed* or *Available*: The task has completed successfully.
-   *Failed* or *Error*: Something goes wrong during the task run and it could not be completed. Go to the details screen of your run and check the logs to identify to issue.

Depending on your activity, there might exist additional statuses. For more information, see [Replicating Data and Monitoring Remote Tables](replicating-data-and-monitoring-remote-tables-4dd95d7.md), [Persisting and Monitoring Views](persisting-and-monitoring-views-9af04c9.md), [Monitoring Flows](monitoring-flows-b661ea0.md), [Monitoring Remote Queries](monitoring-remote-queries-806d7f0.md) and [Monitoring Task Chains](monitoring-task-chains-4142201.md).

Statuses are sometimes combined with substatuses:


<table>
<tr>
<th valign="top">

Substatus

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*CANCELLED*

</td>
<td valign="top">

This task run was canceled, after it had started. In this case, the data was rolled back and restored to the state that existed before the task run was initially triggered.

</td>
</tr>
<tr>
<td valign="top">

*FAIL\_CONSENT\_EXPIRED*

</td>
<td valign="top">

The authorization that allows SAP to run task chains or schedule data integration tasks on your behalf has expired. Select the option provided to renew your consent \([Changing SAP Datasphere Settings](https://help.sap.com/viewer/ac696daa26f0413db39626bc2971e6c2/DEV_CURRENT/en-US/1084796d09464e78870f32cab8584dfc.html "To view and edit your user profile settings, click your user icon in the shell bar and select Settings. You can control various aspects of the user experience of SAP Datasphere and set data privacy and task scheduling consent options.") :arrow_upper_right:\).

</td>
</tr>
<tr>
<td valign="top">

*FAIL\_CONSENT\_INVALIDATED*

</td>
<td valign="top">

This task or task chain could not be executed, typically due to a change in the Identity Provider configuration of the tenant. In that case, no new task jobs or task chains can be run or scheduled in the name of the affected user. If the assigned user still exists in the new IdP, revoke the scheduling consent and then grant it again. If the assigned user no longer exists, assign a new task job or task chain owner and provide the required task scheduling consent. See the following SAP note [3089828](https://me.sap.com/notes/3089828) for more information.

</td>
</tr>
<tr>
<td valign="top">

*FAIL\_CONSENT\_NOT\_AVAILABLE*

</td>
<td valign="top">

You have not authorized SAP to run task chains or schedule data integration tasks on your behalf. Select the option provided to give your consent \([Changing SAP Datasphere Settings](https://help.sap.com/viewer/ac696daa26f0413db39626bc2971e6c2/DEV_CURRENT/en-US/1084796d09464e78870f32cab8584dfc.html "To view and edit your user profile settings, click your user icon in the shell bar and select Settings. You can control various aspects of the user experience of SAP Datasphere and set data privacy and task scheduling consent options.") :arrow_upper_right:\).

</td>
</tr>
<tr>
<td valign="top">

*FAIL\_NOT\_TRIGGERED* 

</td>
<td valign="top">

This task job could not be executed due to a system outage or some part of the database system not being available at the time of the planned execution. Wait for the next scheduled job execution time or reschedule the job.

</td>
</tr>
<tr>
<td valign="top">

*FAIL\_OWNER\_MISSING* 

</td>
<td valign="top">

This task job could not be executed because it does not have an assigned system user. Assign an owner user to the job.

</td>
</tr>
<tr>
<td valign="top">

*FORBIDDEN*

</td>
<td valign="top">

The assigned user does not have the privileges necessary to execute this task.

</td>
</tr>
<tr>
<td valign="top">

*LOCKED*

</td>
<td valign="top">

The same task was already running, so this task job cannot be run in parallel with an existing task’s execution.

</td>
</tr>
<tr>
<td valign="top">

*PARTIALLY\_COMPLETED \(PARTIALLY\_EXECUTED\)*

</td>
<td valign="top">

This task failed but, for some sub-objects, the execution ended successfully.

</td>
</tr>
<tr>
<td valign="top">

*SCHEDULE\_CANCELLED* 

</td>
<td valign="top">

This task job could not be executed due to an internal error. Contact SAP Support and provide them with the correlation id and timestamp from this task job’s log detail information.

</td>
</tr>
<tr>
<td valign="top">

*SET\_TO\_FAILED*

</td>
<td valign="top">

This task was running but the user set this task’s status to FAILED.

</td>
</tr>
<tr>
<td valign="top">

*STOPPED*

</td>
<td valign="top">

This task was stopped, but no rollback was performed.

</td>
</tr>
<tr>
<td valign="top">

*SUCCESS\_SKIPPED*

</td>
<td valign="top">

This task’s execution has not been triggered because a previous run of the same task is still in progress.

</td>
</tr>
<tr>
<td valign="top">

*TASK\_EXCEPTION* 

</td>
<td valign="top">

This task encountered an unspecified error during execution.

</td>
</tr>
<tr>
<td valign="top">

*TASK\_EXECUTOR\_ERROR* 

</td>
<td valign="top">

This task encountered an internal error, likely during preparation steps for execution, and the task could not be started.

</td>
</tr>
<tr>
<td valign="top">

*UNAUTHORIZED*

</td>
<td valign="top">

The user could not be authenticated, has been locked, or deleted.

</td>
</tr>
</table>

You can also monitor the statuses and substatuses in the <span class="FPA-icons"></span> \(*System Monitor*\). For more information, see [Monitoring SAP Datasphere](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/28910cded17a42a0bf16225309cb8bf6.html "Administrators have access to various monitoring logs and views, and can create database analysis users, if necessary, to help troubleshoot issues.") :arrow_upper_right:

