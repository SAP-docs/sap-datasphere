<!-- loiod04f5dd6bbda44448407d54d2a7979be -->

# Data Persistence and Run Mode

From the *Views* Details screen, you can change the settings to persist your data to ensure that you choose the best run mode according to your business case.

When persisting a view, an SQL procedure is called in SAP HANA. In case of high data volume to persist, processing the SQL procedure can impact the memory consumption and the system resources. In the details screen of the view under *Settings*, you can optimize the run mode depending on your needs.



<a name="loiod04f5dd6bbda44448407d54d2a7979be__section_aft_2hw_tzb"/>

## Run Mode

You can change the run mode of your data persistence and choose between performance and memory consumption:

-   *Performance-Optimized \(Recommended\)*: This is the recommended mode to run the task. SQL queries are processed directly in-memory. No intermediate result is stored on the disk to ensure a quicker data access and data consumption. However, this mode consumes memory resources and if your data model is very complex, it can result in an out of memory and the task failed.
-   *Memory-Optimized*: The mode uses an enhancement of the SAP HANA Execution Engine, which stores intermediate results of SQL statements on the disk. Memory consumption of SQL statements is then lower because intermediate results are not stored in-memory but are saved on the disk. It results in slower runtime, though. For example, you can use it when you get an out of memory error while running the task, as alternative to manual partitioning. 

    > ### Note:  
    > You must ensure that you have sufficient disk space available. If not, it can result with an error of type "Disk Full". You can monitor your disk space using the SAP HANA Cockpit. For more information, see [Disk Usage: Monitor Disk Volume](https://help.sap.com/docs/SAP_HANA_COCKPIT/afa922439b204e9caf22c78b6b69e4f2/5c947a6a2f0f4c3b95a9628d4441bd18.html?locale=en-US&version=2.16.0.0) 


