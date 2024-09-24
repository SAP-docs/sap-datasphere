<!-- loio4cbf7c7fc64645bfa364332827557267 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Managing and Monitoring Data Integration

From <span class="FPA-icons-V3"></span> \(*Data Integration Monitor*\), you can run and monitor data replication for remote tables, monitor flows and task chain, monitor your local tables, your persisted views, and track the queries sent to your remote connected source systems for your space.

> ### Note:  
> For optimal performance, it is recommended that you consider staggering the scheduled run time of tasks such as data flows and task chains that may contain these tasks. There is a limit on how many tasks can be started at the same time. If you come close to this limit, scheduled task runs may be delayed and, if you go beyond the limit, some scheduled task runs might even be skipped.

The *Data Integration Monitor* is composed of several monitors that help you track how data is managed within your space:

-   *Remote Tables*: Copy data for remote tables that have been deployed in your space and monitor the replication of the data. Copy or schedule copying the full set of data from the source, or set up replication of data changes in real-time via change data capturing \(CDC\). For more information, see [Replicating Data and Monitoring Remote Tables](replicating-data-and-monitoring-remote-tables-4dd95d7.md).

    > ### Note:  
    > Remote tables from a source that is configured as data access *Remote Only* are not displayed in this monitor. For more information, see [Managing and Monitoring Data Integration](managing-and-monitoring-data-integration-4cbf7c7.md) 

-   *Local Tables*: Monitor all local tables which have been created in a space and display their metrics. From the detail screen, you can also delete table records on-demand, using filter conditions or using a schedule.
-   *Views*: Add, monitor and schedule persisted views. Turn your views into persisted views to improve performance while accessing your data. For more information, see [Persisting and Monitoring Views](persisting-and-monitoring-views-9af04c9.md).
-   *Flows*: View and monitor the execution details of the executed data flows, replication flows or transformation flows. For more information, see [Monitoring Flows](monitoring-flows-b661ea0.md).
-   *Remote Queries*:
    -   *Remote Queries*: Check and analyze how the communication is running between the federation layer of SAP HANA Cloud and the connected remote source systems. For more information, see [Monitoring Remote Queries](monitoring-remote-queries-806d7f0.md).
    -   *Remote Table Statistics*: Create statistics for your remote tables to improve federated query execution. For more information, see [Creating Statistics for Your Remote Tables](creating-statistics-for-your-remote-tables-e4120bb.md).

-   *Task Chains*: Monitor the status and progress of running and past task chains. For more information, see [Monitoring Task Chains](monitoring-task-chains-4142201.md).

Depending on your role and the tasks you need to perform in the *Data Integration Monitor*, you may need specific privileges. See [Privileges and Permissions](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/d7350c6823a14733a7a5727bad8371aa.html "A privilege represents a task or an area in SAP Datasphere and can be assigned to a specific role. The actions that can be performed in the area are determined by the permissions assigned to a privilege.") :arrow_upper_right:.

Here are some examples of privileges and permissions you need to perform some tasks:

-   To create or update connections, you need the *Data Warehouse Remote Connection* privilege.
-   To perform one-time actions in one of the monitors, such as replicating full set of data, redeploying persisted views, loading new snapshot, or removing persisted data, you need the privilege *Data Warehouse Data Integration* *Update*.
-   To schedule tasks in one of the monitors and perform task execution and log retrieval in general, you need the privilege *Data Warehouse Data Integration* *Execute*.
-   To add a new view in the *Views* monitor, or to set up or change partitioned data loading in the *Remote Tables* monitor, you need the privilege *Data Warehouse Data Builder* *Read*.

