<!-- loiod04f5dd6bbda44448407d54d2a7979be -->

# Data Persistence and Processing Mode

From the *Views* Details screen, you can change the settings of the processing mode.

While persisting a view, an SQL procedure is called in SAP HANA. The SQL procedure can be executed synchronously or asynchronously. In the settings tab of the *Views* - Details screen, you can change the settings to optimize the processing mode while persistîng a view following your needs:

-   Default \(asynchronous, may change in future\)

    By default, while persisting a view, the process is run using the asynchronous mode. Keeping the default mode ensures that you always stick to the recommended SAP default execution, even if the default mode is changed by SAP..

-   Synchronous

    The service will immediately recognize once the SQL procedure is completed. Therefore, the synchronous execution is recommended in case the process to persist view is running only for a very short time.

-   Asynchronous

    Due to the complexity of the view or a high data volume to be persisted, the execution of the SQL procedure can take a lot of time. Thus, in case of an issue during the process, for example a service is temporary not available, the task to persist the view is aborded and failed. Switching to the asynchronous mode will allow the SQL procedure to continue to run, even if the service is not available. SAP recommends to use the asynchronous mode to persist views with a normal or longer runtime: The execution is done with an asynchronous process in the database, which is independent from other services, and thus avoid the abortion of the process in case these services are not available. This more resilient way of execution leads to a very small performance degradation. Note that the maximum execution time in the asynchronous mode is 12 hours. If the process to persist the view exceeds 12 hours, then it is aborted. The steps "Persist intermediate views" and "Handling of remote tables" described on the page *Persisted Views and Memory Consumption* may also help to reduce the execution time of the process to persist a view. See [Persisted Views and Memory Consumption](persisted-views-and-memory-consumption-e3d0495.md).


