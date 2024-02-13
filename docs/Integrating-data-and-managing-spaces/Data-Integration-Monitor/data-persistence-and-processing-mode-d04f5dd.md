<!-- loiod04f5dd6bbda44448407d54d2a7979be -->

# Data Persistence and Processing Mode

From the *Views* Details screen, you can change the settings to persist your data to ensure that you choose the best processing mode depending on your business case.

When persisting a view, an SQL procedure is called in SAP HANA. In case of high data volume to persist, processing the SQL procedure can impact the memory consumption and the system resources. In the details screen of the view under *Settings*, you can optimize the run and processing mode depending on your needs.



<a name="loiod04f5dd6bbda44448407d54d2a7979be__section_aft_2hw_tzb"/>

## Run Mode

You can change the run mode of your data persistence and choose between performance and memory consumption:

-   *Performance-Optimized \(Recommended\)*: This is the recommended mode to run the task. SQL queries are processed directly in-memory. No intermediate result is stored on the disk to ensure a quicker data access and data consumption. However, this mode consumes memory resources and if your data model is very complex, it can result in an out of memory and the task failed.
-   *Memory-Optimized*: The mode uses an enhancement of the SAP HANA Execution Engine, which stores intermediate results of SQL statements on the disk. Memory consumption of SQL statements is then lower because intermediate results are not stored in-memory but are saved on the disk. It results in slower runtime, though. For example, you can use it when you get an out of memory error while running the task, as alternative to manual partitioning. 

    > ### Note:  
    > You must ensure that you have sufficient disk space available. If not, it can result with an error of type "Disk Full". You can monitor your disk space using the SAP HANA Cockpit. For more information, see [Disk Usage: Monitor Disk Volume](https://help.sap.com/docs/SAP_HANA_COCKPIT/afa922439b204e9caf22c78b6b69e4f2/5c947a6a2f0f4c3b95a9628d4441bd18.html?locale=en-US&version=2.16.0.0) 




<a name="loiod04f5dd6bbda44448407d54d2a7979be__section_j35_dhw_tzb"/>

## Processing Mode

While persisting a view, an SQL procedure is called in SAP HANA. The SQL procedure can be executed synchronously or asynchronously. You can change the settings to optimize the processing mode while persistîng a view following your needs:

-   Default \(asynchronous, may change in future\)

    By default, while persisting a view, the process is run using the asynchronous mode. Keeping the default mode ensures that you always stick to the recommended SAP default execution, even if the default mode is changed by SAP.

-   Synchronous

    The service will immediately recognize once the SQL procedure is completed. Therefore, the synchronous execution is recommended in case the process to persist view is running only for a very short time.

-   Asynchronous

    Due to the complexity of the view or a high data volume to be persisted, the execution of the SQL procedure can take a lot of time. Thus, in case of an issue during the process, for example a service is temporary not available, the task to persist the view is aborded and failed. Switching to the asynchronous mode will allow the SQL procedure to continue to run, even if the service is not available. SAP recommends to use the asynchronous mode to persist views with a normal or longer runtime: The execution is done with an asynchronous process in the database, which is independent from other services, and thus avoid the abortion of the process in case these services are not available. This more resilient way of execution leads to a very small performance degradation. Note that the maximum execution time in the asynchronous mode is 12 hours. If the process to persist the view exceeds 12 hours, then it is aborted. The steps "Persist intermediate views" and "Handling of remote tables" described on the page *Persisted Views and Memory Consumption* may also help to reduce the execution time of the process to persist a view. See [Persisted Views and Memory Consumption](persisted-views-and-memory-consumption-e3d0495.md).


