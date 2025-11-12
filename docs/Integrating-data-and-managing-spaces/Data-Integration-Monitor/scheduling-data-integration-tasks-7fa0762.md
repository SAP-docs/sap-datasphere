<!-- loio7fa07621d9c0452a978cb2cc8e4cd2b1 -->

# Scheduling Data Integration Tasks

Schedule data integration tasks to run periodically at a specified date or time.



<a name="loio7fa07621d9c0452a978cb2cc8e4cd2b1__section_e5m_k51_t2c"/>

## Prerequisites

To schedule data integration tasks, you must have a scoped role that grants you access to the space with the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Data Warehouse Data Integration* \(`-R------`\) - To view data integration task logs in the *Data Integration Monitor* app.

-   *Data Warehouse Data Integration* \(`--U-----`\) - To manually run data integration tasks.

-   *Data Warehouse Data Integration* \(`----E---`\) - To schedule data integration tasks.


The *DW Integrator* role template, for example, grants these privileges. For more information, see [Privileges and Permissions](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/d7350c6823a14733a7a5727bad8371aa.html "A privilege represents a task or an area in SAP Datasphere and can be assigned to a specific role. The actions that can be performed in the area are determined by the permissions assigned to a privilege.") :arrow_upper_right: and [Standard Roles Delivered with SAP Datasphere](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/a50a51d80d5746c9b805a2aacbb7e4ee.html "SAP Datasphere is delivered with several standard roles. A standard role includes a predefined set of privileges and permissions.") :arrow_upper_right:. 



<a name="loio7fa07621d9c0452a978cb2cc8e4cd2b1__section_h4g_n51_t2c"/>

## Introduction to Scheduling Data Integration Tasks

You can schedule or unschedule data integration tasks such as remote table replication, persisting views, and data flow, replication flow, or task chain execution. You may also pause and then later resume execution of scheduled tasks.

> ### Note:  
> For optimal performance, it is recommended that you consider staggering the scheduled run time of tasks such as data flows or task chains that may contain these tasks. Make sure to distribute your work such as scheduling and running tasks. There isn't a specific numerical limit on how many tasks can be scheduled. There could be a resource distribution issue caused by too many tasks running at once. Check your system monitor to look at your workload distribution. For more information see, [Monitoring SAP Datasphere](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/28910cded17a42a0bf16225309cb8bf6.html "Users with an administrator role have access to various monitoring logs and views and can, if necessary, create database analysis users to help troubleshoot issues.") :arrow_upper_right: or [Persisted Views and Memory Consumption](persisted-views-and-memory-consumption-e3d0495.md).

Using a dedicated dialog box, you can specify the frequency and time range of the schedule by using a simple form or by directly entering a cron expression.

> ### Note:  
> When you click *Create*, the definition of the schedule that is created and saved is the one that is currently displayed \(either in the *Simple Schedule* area or the *Cron Expression* area\).

> ### Note:  
> If you create a schedule for a remote table whose data access is *Replicated \(Real-time\)*, the replication type will change from real-time replication to batch replication at the next run of the schedule. The data will no longer be updated in real-time.

