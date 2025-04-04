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


The *DW Integrator* role template, for example, grants these privileges. For more information, see [Privileges and Permissions](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/d7350c6823a14733a7a5727bad8371aa.html "A privilege represents a task or an area in SAP Datasphere and can be assigned to a specific role. The actions that can be performed in the area are determined by the permissions assigned to a privilege.") :arrow_upper_right: and [Standard Roles Delivered with SAP Datasphere](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/a50a51d80d5746c9b805a2aacbb7e4ee.html "SAP Datasphere is delivered with several standard roles. A standard role includes a predefined set of privileges and permissions.") :arrow_upper_right:. 



<a name="loio7fa07621d9c0452a978cb2cc8e4cd2b1__section_h4g_n51_t2c"/>

## Introduction to Scheduling Data Integration Tasks

You can schedule or unschedule data integration tasks such as remote table replication, persisting views, and data flow, replication flow, or task chain execution. You may also pause and then later resume execution of scheduled tasks.

> ### Note:  
> For optimal performance, it is recommended that you consider staggering the scheduled run time of tasks such as data flows and task chains that may contain these tasks. There is a limit on how many tasks can be started at the same time. If you come close to this limit, scheduled task runs may be delayed and, if you go beyond the limit, some scheduled task runs might even be skipped.

Using a dedicated dialog box, you can specify the frequency and time range of the schedule by using a simple form or by directly entering a cron expression.

> ### Note:  
> When you click *Create*, the definition of the schedule that is created and saved is the one that is currently displayed \(either in the *Simple Schedule* area or the *Cron Expression* area\).

> ### Note:  
> If you create a schedule for a remote table whose data access is *Replicated \(Real-time\)*, the replication type will change from real-time replication to batch replication at the next run of the schedule. The data will no longer be updated in real-time.

