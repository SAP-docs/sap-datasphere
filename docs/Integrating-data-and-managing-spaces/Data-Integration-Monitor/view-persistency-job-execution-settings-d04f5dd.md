<!-- loiod04f5dd6bbda44448407d54d2a7979be -->

# View Persistency Job Execution Settings

From the *View Persistency Monitor*- Details screen, you can change the settings of the job execution.

While persisting a view, an SQL procedure is called in SAP HANA. The SQL procedure can be executed synchronously or asynchronously. In the settings tab of the *View Persistency Monitor* - Details screen, you can change the settings to optimize the job execution of a view persistency following your needs:

-   Default \(synchronous, may change in future\)

    By default, while persisting a view, the process is run using a synchronous mode. Keeping the default mode ensure that you always stick to the recommended SAP default execution, even if the default mode is changed by SAP.

-   Synchronous

    The service will immediately recognize once the SQL procedure is completed. Therefore, the synchronous execution is recommended in case a view persistency is running only for a short time.

-   Asynchronous

    Due to the complexity of the view or a high data volume to be persisted, the execution of the SQL procedure can take a lot of time. Thus, in case of an issue during the process, for example a service is temporary not available, the view persistency is aborded and failed. Switching to the asynchronous mode will allow the SQL procedure to continue to run, even if the service is not available. SAP recommends to use the asynchronous mode only in case the persistency of a view is aborted because the service is not available.


