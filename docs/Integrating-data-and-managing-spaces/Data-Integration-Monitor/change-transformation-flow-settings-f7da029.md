<!-- loiof7da0290f5084e3db17c65b3d7c3140a -->

# Change Transformation Flow Settings

Change the run mode and transport runtime settings for a transformation flow.



## Optimize for Performance or Memory Consumption

You can change the run mode for a transformation flow.

1.  In the *Data Integration Monitor*, open your transformation flow. On the *Settings* tab, you can change the run mode for a transformation flow and choose between performance and memory consumption:
    -   *Performance-Optimized \(Recommended\)*: This is the recommended mode to run the transformation flow. SQL queries are processed directly in-memory. No intermediate result is stored on the disk to ensure a quicker data access and data consumption. However, this mode consumes memory resources and if your data model is very complex, it can result in an out of memory and the task failed.
    -   *Memory-Optimized*: The mode uses an enhancement of the SAP HANA Execution Engine, which stores intermediate results of SQL statements on the disk. Memory consumption of SQL statements is then lower because intermediate results are not stored in-memory but are saved on the disk. It results in slower runtime, though. For example, you can use it when you get an out of memory error while running the task, as alternative to manual partitioning. 

        > ### Note:  
        > You must ensure that you have sufficient disk space available. If not, it can result with an error of type "Disk Full". You can monitor your disk space using the SAP HANA Cockpit. For more information, see [Disk Usage: Monitor Disk Volume](https://help.sap.com/docs/SAP_HANA_COCKPIT/afa922439b204e9caf22c78b6b69e4f2/5c947a6a2f0f4c3b95a9628d4441bd18.html).





## Include Runtime Settings in Transport Packages

Transport runtime settings for a transformation flow.

In the *Data Integration Monitor*, open your transformation flow. On the *Settings* tab, you can define the transport runtime settings for a transformation flow that you want to include in a transport:

-   *Include Batches* for SAP HANA transformation flows.
-   *Include Run Mode* for SAP HANA transformation flows.
-   *Include Spark Application Configuration* for Apache Spark transformation flows.

The selected items are added to the flow definition when you export the flow using the *Transport* app. Transporting runtime settings ensures consistent runtime behavior across environments without manual reconfiguration after transport.

