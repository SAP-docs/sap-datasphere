<!-- loiod39b8652994846f9ab80b32fc5b4d671 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Monitoring SAP Datasphere

Users with an administrator role have access to various apps to monitor and manage the health of their SAP Datasphere tenant.

This topic contains the following sections:

-   [System and Tasks](monitoring-sap-datasphere-d39b865.md#loiod39b8652994846f9ab80b32fc5b4d671__system_monitor)
-   [Audit Logs](monitoring-sap-datasphere-d39b865.md#loiod39b8652994846f9ab80b32fc5b4d671__audit_logs)
-   [Activities](monitoring-sap-datasphere-d39b865.md#loiod39b8652994846f9ab80b32fc5b4d671__activities)
-   [Database Analysis Users](monitoring-sap-datasphere-d39b865.md#loiod39b8652994846f9ab80b32fc5b4d671__db_analysis_users)



<a name="loiod39b8652994846f9ab80b32fc5b4d671__system_monitor"/>

## System and Tasks

Click :desktop_computer: *Monitoring* in the side navigation to open the monitoring menu. You can access different monitoring apps:

-   <span class="SAP-icons-V5"></span> *System and Spaces*  

    Monitor system performance and issues related to storage, tasks, out-of-memory, and other issues across all spaces. Monitor the storage consumption for file spaces \(of storage type SAP HANA Data Lake Files\) and their usage of the Apache Spark application for task runs. See [Monitoring System and Spaces](monitoring-system-and-spaces-bce718d.md).

-   <span class="SAP-icons-V5"></span> *Capacities Monitoring*  

    Monitor monthly and daily capacity unit consumption, allowing users to track usage relative to their subscription and download detailed hourly data. See [Monitoring Capacity Unit Consumption](monitoring-capacity-unit-consumption-ba3d05b.md).

-   <span class="SAP-icons-V5"></span> *Task Logs*  

    Monitor the execution history of task runs. See [Reviewing Task Logs](reviewing-task-logs-399e52f.md).

-   <span class="SAP-icons-V5"></span> *Expensive Statement Logs*  

    Monitor SQL statements exceeding configured thresholds. See [Reviewing Expensive Statement Logs](reviewing-expensive-statement-logs-4f18e74.md).

-   <span class="FPA-icons-V3"></span> *Elastic Compute Nodes*  

    Monitor elastic compute nodes key performance figures. See [Monitoring Elastic Compute Nodes](monitoring-elastic-compute-nodes-1d5f583.md).

-   :fast_forward: *Data Integration*  

    Monitor, schedule, and run data replication and persistence tasks for remote tables and views, track queries sent to remote source systems, perform local table administration tasks like data deletion or house keeping, and manage other tasks through flows and task chains. Users need a space administrator or integrator role to access this app. See [Managing and Monitoring Data Integration](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/4cbf7c7fc64645bfa364332827557267.html "Users with a space administrator or integrator role can use the  Data Integration app to schedule, run, and monitor data replication and persistence tasks for remote tables and views, track queries sent to remote source systems, and manage other tasks through flows and task chains.") :arrow_upper_right:.


> ### Note:  
> For optimal performance, it is recommended that you consider staggering the scheduled run time of tasks such as data flows or task chains that may contain these tasks. Make sure to distribute your work such as scheduling and running tasks. There isn't a specific numerical limit on how many tasks can be scheduled. There could be a resource distribution issue caused by too many tasks running at once. Check your *Monitoring* app to look at your workload distribution. For more information see, [Monitoring SAP Datasphere](monitoring-sap-datasphere-d39b865.md) or [Persisted Views and Memory Consumption](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/e3d04951a4a344c28b25b2b1b13bf3d8.html "You want to persist a complex view and consider how it affects the memory consumption.") :arrow_upper_right:.



<a name="loiod39b8652994846f9ab80b32fc5b4d671__audit_logs"/>

## Audit Logs

Get an overview of audit logs created in spaces and manage the deletion of these logs to prevent them growing too large.

For more information, see [Monitor Database Operations with Audit Logs](monitor-database-operations-with-audit-logs-110404a.md).



<a name="loiod39b8652994846f9ab80b32fc5b4d671__activities"/>

## Activities

Keep track of changes to modeling objects \(and system objects\) via the *Activities* screen.

For more information, see [Monitor Object Changes with Activities](monitor-object-changes-with-activities-08e607c.md).



<a name="loiod39b8652994846f9ab80b32fc5b4d671__db_analysis_users"/>

## Database Analysis Users

Create database analysis users, which have read-only access to all space schemas, to monitor, analyze, trace, or debug your SAP Datasphere database in *Database Explorer* and *SAP HANA Cockpit*.

For more information, see [Create a Database Analysis User to Debug Database Issues](create-a-database-analysis-user-to-debug-database-issues-c28145b.md).

