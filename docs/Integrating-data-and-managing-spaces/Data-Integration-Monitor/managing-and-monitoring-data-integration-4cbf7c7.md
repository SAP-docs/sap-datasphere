<!-- loio4cbf7c7fc64645bfa364332827557267 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Managing and Monitoring Data Integration

Users with a space administrator or integrator role can use the *Data Integration Monitor* app to schedule, run, and monitor data replication and persistence tasks for remote tables and views, track queries sent to remote source systems, and manage other tasks through flows and task chains.

> ### Note:  
> For optimal performance, it is recommended that you consider staggering the scheduled run time of tasks such as data flows or task chains that may contain these tasks. Make sure to distribute your work such as scheduling and running tasks. There isn't a specific numerical limit on how many tasks can be scheduled.. There could be a resource distribution issue caused by too many tasks running at once. Check your system monitor to look at your workload distribution. For more information see, [Monitoring SAP Datasphere](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/28910cded17a42a0bf16225309cb8bf6.html "Users with an administrator role have access to various monitoring logs and views and can, if necessary, create database analysis users to help troubleshoot issues.") :arrow_upper_right: or [Persisted Views and Memory Consumption](persisted-views-and-memory-consumption-e3d0495.md).

The *Data Integration Monitor* is composed of several monitors that help you track how data is managed within your space. Note that the available monitors depend on space capabilities. 

-   *Remote Tables* \(Not available if you are in space of type SAP HANA Cloud, data lake files\): Copy data for remote tables that have been deployed in your space and monitor the replication of the data. Copy or schedule copying the full set of data from the source, or set up replication of data changes in real-time via change data capturing \(CDC\). For more information, see [Replicating Data and Monitoring Remote Tables](replicating-data-and-monitoring-remote-tables-4dd95d7.md).

    > ### Note:  
    > Remote tables from a source that is configured as data access *Remote Only* are not displayed in this monitor. For more information, see [Managing and Monitoring Data Integration](managing-and-monitoring-data-integration-4cbf7c7.md) 

-   *Local Tables* \(Not available if you are in space of type SAP HANA Cloud, data lake files\): Monitor all local tables which have been created in a space and display their metrics. From the detail screen, you can also delete table records on-demand, using filter conditions or using a schedule.
-   *Local Tables \(Files\)* \(Not available if you are in space of type SAP HANA Cloud, SAP HANA database\): Check how and when your local tables \(files\) were last updated and if new data has still to be merged. For more information, see [Monitoring Local Tables \(File\)](monitoring-local-tables-file-6b2d007.md)
-   *Views* \(Not available if you are in space of type SAP HANA Cloud data lake files\): Add, monitor and schedule persisted views. Turn your views into persisted views to improve performance while accessing your data. For more information, see [Persisting and Monitoring Views](persisting-and-monitoring-views-9af04c9.md).
-   *Flows*: View and monitor the execution details of the executed data flows, replication flows or transformation flows. For more information, see [Monitoring Flows](monitoring-flows-b661ea0.md).

    > ### Note:  
    > Data flows are not available for spaces of type SAP HANA Cloud data lake files

-   *Remote Queries*:
    -   *Remote Queries*: Check and analyze how the communication is running between the federation layer of SAP HANA Cloud and the connected remote source systems. For more information, see [Monitoring Remote Queries](monitoring-remote-queries-806d7f0.md).
    -   *Remote Table Statistics* \(Not available if you are in space of type SAP HANA Cloud, data lake files\): Create statistics for your remote tables to improve federated query execution. For more information, see [Creating Statistics for Your Remote Tables](creating-statistics-for-your-remote-tables-e4120bb.md).

-   *Task Chains*: Monitor the status and progress of running and past task chains. For more information, see [Monitoring Task Chains](monitoring-task-chains-4142201.md).

Depending on your role and the tasks you need to perform in the *Data Integration Monitor*, you may need specific privileges. See [Privileges and Permissions](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/d7350c6823a14733a7a5727bad8371aa.html "A privilege represents a task or an area in SAP Datasphere and can be assigned to a specific role. The actions that can be performed in the area are determined by the permissions assigned to a privilege.") :arrow_upper_right:.

