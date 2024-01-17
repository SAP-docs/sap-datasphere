<!-- loio5b591d4998fa4a148750016a29ada91e -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Running a Flow

Once your flow is configured and deployed, you can run it.

To run a flow, you have 3 main options depending on your flow type:

-   Click *Run* to start a direct run.
-   Click *Schedule* to run your data flow or your transformation flow at later time, or on regular basis \(this is not available for *Replication Flow*\).
-   Add the flow into a task chain. This is only valid for a data flow. For more information, see [Creating a Task Chain](creating-a-task-chain-d1afbc2.md).



<a name="loio5b591d4998fa4a148750016a29ada91e__section_kxy_dq3_pzb"/>

## Run a Direct Flow

Once you have completed the flow configuration and saved it, you can run it. Click <span class="FPA-icons"></span> \(Run\) to start the process to acquire and transform data as per your defined settings. Once completed, the *Run Status* section in the property panel is updated. You can navigate to the *Flows* monitor to get more detail on the run. See [Monitoring Flows](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/b661ea0766a24c7d839df950330a89fd.html "In the Flows monitor, you can find all the deployed flows per space.") :arrow_upper_right:.

> ### Note:  
> Regarding data flows:
> 
> -   If your data flow contains input parameters, a dialog box appears prompting the user to enter a value for each input parameter. You can either keep the default value or override it \(see [Create an Input Parameter](create-an-input-parameter-a6fb3e7.md)\).
> 
> -   The initialization time for running a data flow takes an average of 20 seconds even with smaller data loads causing longer runtime for the data flow.
> -   Metrics are displayed only for source and target tables and can be used for further analysis. They are available in the *Flows* monitor.
> -   If a source view or an underlying view of the source view has data access controls applied to it, then no data is read from the view during the execution of the data flow. This results in incorrect data or no data in the output.
> 
>     For more information, see [Securing Data with Data Access Controls](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/a032e51c730147c7a1fcac125b4cfe14.html "Data access controls allow you to apply row-level security to your objects. When a data access control is applied to a data layer view or a business layer object, any user viewing its data will see only the rows for which they are authorized, based on the specified criteria.") :arrow_upper_right:.

> ### Note:  
> Regarding transformation flows:
> 
> You can cancel a running transformation flow in the *Data Integration Monitor*. For more information, see [Cancel a Transformation Flow Run](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/ab885f05210f4a52aebe8306c8cad083.html "You want to cancel a transformation flow that is running.") :arrow_upper_right:.



<a name="loio5b591d4998fa4a148750016a29ada91e__section_bqf_5q3_pzb"/>

## Create a Schedule to Run Your Flow

You can also create a schedule to run your data flow or your transformation flow on regular basis. Click <span class="FPA-icons"></span> \(Schedule\) and define your schedule. For more information, see [Scheduling Data Integration Tasks](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/7fa07621d9c0452a978cb2cc8e4cd2b1.html "Schedule data integration tasks to run periodically at a specified date or time.") :arrow_upper_right:.

> ### Note:  
> For optimal performance, it is recommended that you consider staggering the scheduled run time of tasks such as data flows and task chains that may contain these tasks. There is a limit on how many tasks can be started at the same time. If you come close to this limit, scheduled task runs may be delayed and, if you go beyond the limit, some scheduled task runs might even be skipped.

> ### Note:  
> In very rare situations, an error may occur the first time that a scheduled data flow is run in a space. In this case, you should run the data flow manually once. Subsequent scheduled runs will not require further intervention.



<a name="loio5b591d4998fa4a148750016a29ada91e__section_hh4_pr3_pzb"/>

## Run Your Data Flow Using a Task Chain

You can run a data flow using a task chain. For more information, see [Creating a Task Chain](creating-a-task-chain-d1afbc2.md).

Alternatively, you can also run your flows from the <span class="FPA-icons"></span> \( Data Integration Monitor\).

From the *Flows* monitor, you can check details of your runs, and perform other actions on your flows. For more information, see [Monitoring Flows](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/b661ea0766a24c7d839df950330a89fd.html "In the Flows monitor, you can find all the deployed flows per space.") :arrow_upper_right:.

