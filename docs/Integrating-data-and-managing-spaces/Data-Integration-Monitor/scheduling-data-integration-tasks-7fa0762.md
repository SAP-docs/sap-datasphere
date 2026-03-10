<!-- loio7fa07621d9c0452a978cb2cc8e4cd2b1 -->

# Scheduling Data Integration Tasks

Schedule data integration tasks to run periodically at a specified date or time.



<a name="loio7fa07621d9c0452a978cb2cc8e4cd2b1__section_e5m_k51_t2c"/>

## Prerequisites

To schedule data integration tasks, you must have a scoped role that grants you access to a space with the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Data Warehouse Data Integration* \(`-R------`\) - To view data integration task logs in the *Data Integration Monitor* app.

-   *Data Warehouse Data Integration* \(`--U-----`\) - To manually run data integration tasks.

-   *Data Warehouse Data Integration* \(`----E---`\) - To schedule data integration tasks.


The *DW Integrator* role template, for example, grants these privileges. For more information, see [Privileges and Permissions](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/d7350c6823a14733a7a5727bad8371aa.html "A privilege represents a task or an area in SAP Datasphere and can be assigned to a specific role. The actions that can be performed in the area are determined by the permissions assigned to a privilege.") :arrow_upper_right: and [Standard Roles Delivered with SAP Datasphere](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/a50a51d80d5746c9b805a2aacbb7e4ee.html "SAP Datasphere is delivered with several standard roles. A standard role includes a predefined set of privileges and permissions.") :arrow_upper_right:. 

Technical users need to be added to the space by an administrator in order to add a technical user as an owner. For more information, see [Create an OAuth2.0 Client with a Technical User Purpose](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/88b13468fc3c4ebd972bcb8faa6cafbf.html "Users with an administrator role can create OAuth2.0 clients with a technical user purpose and provide the client parameters to users, giving them limited privileges and permissions when connecting clients, tools, or apps to SAP Datasphere.") :arrow_upper_right:.

To run recurring scheduled tasks on your behalf, you need to authorize the job scheduling component of SAP Datasphere. In your profile settings under *Authorized Consent Settings*, you can give and revoke your consent to SAP Datasphere to run your scheduled tasks in the future. Note that when you don't give your consent or revoke your consent, tasks that you own won't be executed but will fail.

> ### Note:  
> Your consent is valid for 365 days. If your consent will expire within the next four weeks, when you attempt to schedule new tasks, SAP Datasphere displays a message warning that your consent is approaching its expiration date. After the consent has expired, a log message informs you that the tasks for which you own the schedule won’t be executed anymore. Renew your consent to resume task execution according to the schedules. Additionally, in *Data Integration Monitor*, a warning message appears four weeks before the expiry of consent.

> ### Note:  
> Your consent is valid for 365 days. If your consent will expire within the next 30 days, you will automatically receive an email notification letting you know that your consent is approaching its expiration date. After the consent has expired, a log message informs you that future tasks you have scheduled will no longer run. Renew your consent to resume task runs according to their original schedules.



<a name="loio7fa07621d9c0452a978cb2cc8e4cd2b1__section_h4g_n51_t2c"/>

## Introduction to Scheduling Data Integration Tasks

You can schedule or unschedule data integration tasks such as remote table replication, persisting views, and data flow, replication flow, or task chain execution. You may also pause and then later resume execution of scheduled tasks. You can choose a business user or technical user to be the owner of a schedule. To change the owner of a schedule, see [Modify the Owner of a Schedule](modify-the-owner-of-a-schedule-4b660c0.md).

> ### Note:  
> For optimal performance, it is recommended that you consider staggering the scheduled run time of tasks such as data flows or task chains that may contain these tasks. Make sure to distribute your work such as scheduling and running tasks. There isn't a specific numerical limit on how many tasks can be scheduled. There could be a resource distribution issue caused by too many tasks running at once. Check your system monitor to look at your workload distribution. For more information see, [Monitoring SAP Datasphere in the System Monitor](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/28910cded17a42a0bf16225309cb8bf6.html "Monitor the overall health of your SAP Datasphere tenant in the System Monitor.") :arrow_upper_right: or [Persisted Views and Memory Consumption](persisted-views-and-memory-consumption-e3d0495.md).

Using a dedicated dialog box, you can specify the frequency and time range of the schedule by using a simple form or by directly entering a cron expression.

> ### Note:  
> When you click *Create*, the definition of the schedule that is created and saved is the one that is currently displayed \(either in the *Simple Schedule* area or the *Cron Expression* area\).

> ### Note:  
> If you create a schedule for a remote table whose data access is *Replicated \(Real-time\)*, the replication type will change from real-time replication to batch replication at the next run of the schedule. The data will no longer be updated in real-time.

