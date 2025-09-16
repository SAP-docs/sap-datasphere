<!-- loio20e5be31cc9744f58f7205e01a94dfbc -->

# Run a Data Flow

Once your data flow is configured and deployed, you can run it.

To run your flow, you can:

-   Click *Run* to start an immediate run.
-   Click *Schedule* to run at a regular specified time.
-   Add it to a task chain. For more information, see [Creating a Task Chain](creating-a-task-chain-d1afbc2.md).

> ### Caution:  
> A data flow uses a technical user during run. So, if a source view or an underlying view of the source view uses the SESSION\_CONTEXT function, incorrect data is read from the view during the execution of the data flow. This results in incorrect data or no data in the output.

Once completed, the *Run Status* section in the property panel is updated. From the *Flows* monitor, you can check details of your runs, and perform other actions on your flows. For more information, see [Monitoring Flows](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/b661ea0766a24c7d839df950330a89fd.html "In the Flows monitor, you can find all the deployed flows per space.") :arrow_upper_right:. 

> ### Note:  
> -   If your data flow contains input parameters, a dialog box appears prompting the user to enter a value for each input parameter. You can either keep the default value or override it \(see [Create an Input Parameter in a Data Flow](create-an-input-parameter-in-a-data-flow-a6fb3e7.md)\).
> -   The Initialization time for running a data flow takes an average of 20 seconds, even with smaller data loads, causing longer runtime for the data flow.
> -   Metrics are displayed only for source and target tables and can be used for further analysis. They are available in the *Flows* monitor.
> -   If a source view or an underlying view of the source view has data access controls applied to it, then no data is read from the view during the execution of the data flow. This results in incorrect data or no data in the output.
> 
> For more information, see [Securing Data with Data Access Controls](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/a032e51c730147c7a1fcac125b4cfe14.html "Users with a space administrator role can create data access controls to allow modelers to apply row-level security to Data Builder and Business Builder objects. Once a data access control is applied to an object, any user viewing its data either directly or via an object using it as a source, will see only those records they are authorized to view, based on the specified criteria.") :arrow_upper_right:



<a name="loio20e5be31cc9744f58f7205e01a94dfbc__section_jst_4vs_dgc"/>

## Create a Schedule to Run Your data Flow

You can also create a schedule to run your flow on a regular basis. Click *Schedule* and define your schedule. For more information, see [Scheduling Data Integration Tasks](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/7fa07621d9c0452a978cb2cc8e4cd2b1.html "Schedule data integration tasks to run periodically at a specified date or time.") :arrow_upper_right:.

> ### Note:  
> -   For optimal performance, it is recommended that you consider staggering the scheduled run time of tasks such as data flows or task chains that may contain these tasks. Make sure to distribute your work, such as scheduling and running tasks. There isn't a specific numerical limit on how many tasks can be scheduled. There could be a resource distribution issue caused by too many tasks running at once. Check your system monitor to look at your workload distribution. For more information, see [Monitoring SAP Datasphere](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/28910cded17a42a0bf16225309cb8bf6.html "Users with an administrator role have access to various monitoring logs and views and can, if necessary, create database analysis users to help troubleshoot issues.") :arrow_upper_right: or [Persisted Views and Memory Consumption](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/e3d04951a4a344c28b25b2b1b13bf3d8.html "You want to persist a complex view and consider how it affects the memory consumption.") :arrow_upper_right:.
> -   In very rare situations, an error may occur the first time that a scheduled data flow is run in a space. In this case, you should run the data flow manually once. Subsequent scheduled runs will not require further intervention.



## Run Your Flow Using a Task Chain

You can run a flow using a task chain. For more information, see [Creating a Task Chain](creating-a-task-chain-d1afbc2.md).

Alternatively, you can also run your flows from the *Data Integration Monitor*.

From the *Flows* monitor, you can check details of your runs, and perform other actions on your flows. For more information, see [Monitoring Flows](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/b661ea0766a24c7d839df950330a89fd.html "In the Flows monitor, you can find all the deployed flows per space.") :arrow_upper_right:.

