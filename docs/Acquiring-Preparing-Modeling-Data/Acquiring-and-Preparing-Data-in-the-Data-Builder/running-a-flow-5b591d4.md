<!-- loio5b591d4998fa4a148750016a29ada91e -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Running a Flow

Once your flow is configured and deployed, you can run it.

To run a flow, you have 3 main options depending on your flow type:

-   Click *Run* to start a regular run.
-   Click *Schedule* to run your data flow or your transformation flow at later time, or on regular basis \(this is not available for *Replication Flow*\).
-   Add the flow into a task chain. For more information, see [Creating a Task Chain](creating-a-task-chain-d1afbc2.md).

> ### Caution:  
> A data flow uses a technical user during run. So, if a source view or an underlying view of the source view uses the SESSION\_CONTEXT function, incorrect data is read from the view during the execution of the data flow. This results in incorrect data or no data in the output.



<a name="loio5b591d4998fa4a148750016a29ada91e__section_kxy_dq3_pzb"/>

## Run a Regular Flow

Once you have completed the flow configuration and saved it, you can run it. Click <span class="FPA-icons-V3"></span> \(Run\) to start the process to acquire and transform data as per your defined settings. Once completed, the *Run Status* section in the property panel is updated. You can navigate to the *Flows* monitor to get more detail on the run. See [Monitoring Flows](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/b661ea0766a24c7d839df950330a89fd.html "In the Flows monitor, you can find all the deployed flows per space.") :arrow_upper_right:.

> ### Note:  
> Regarding data flows:
> 
> -   If your data flow contains input parameters, a dialog box appears prompting the user to enter a value for each input parameter. You can either keep the default value or override it \(see [Create an Input Parameter in a Data Flow](create-an-input-parameter-in-a-data-flow-a6fb3e7.md)\).
> 
> -   The initialization time for running a data flow takes an average of 20 seconds even with smaller data loads causing longer runtime for the data flow.
> -   Metrics are displayed only for source and target tables and can be used for further analysis. They are available in the *Flows* monitor.
> -   If a source view or an underlying view of the source view has data access controls applied to it, then no data is read from the view during the execution of the data flow. This results in incorrect data or no data in the output.
> 
>     For more information, see [Securing Data with Data Access Controls](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/a032e51c730147c7a1fcac125b4cfe14.html "Users with a space administrator role can create data access controls to allow modelers to apply row-level security to Data Builder and Business Builder objects. Once a data access control is applied to an object, any user viewing its data either directly or via an object using it as a source, will see only those records they are authorized to view, based on the specified criteria.") :arrow_upper_right:.

> ### Note:  
> Regarding transformation flows:
> 
> -   In the *Data Integration Monitor*, you can:
> 
>     -   Cancel a running transformation flow. For more information, see [Cancel a Transformation Flow Run](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/ab885f05210f4a52aebe8306c8cad083.html "You want to cancel a transformation flow that is running.") :arrow_upper_right:
>     -   Simulate a run that doesn't save changes in the target table by clicking *Simulate Run*. Simulating allows you to test a transformation flow and see if you get the desired outcome. Based on the result, you can decide to deploy the flow, resolve errors, or to optimize the flow to improve performances. For more information, see [Explore Transformation Flows](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/7588192bf4cd4e3db43704239ba4d366.html "Use Run with Settings to explore graphical or SQL views and the entities they consume in a transformation flow.") :arrow_upper_right:
>     -   Download a PLV file of a visual map of the operators and their relationships and hierarchies by clicking *Generate a SQL Analyzer Plan File*. The plan file contains detailed information about your data model that you can download for further analysis. Analyzing this file allows you to resolve errors and enhance the transformation flow performances. For more information, see [Explore Transformation Flows](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/7588192bf4cd4e3db43704239ba4d366.html "Use Run with Settings to explore graphical or SQL views and the entities they consume in a transformation flow.") :arrow_upper_right:
> 
> -   If a source view or an underlying view of the source view has data access controls applied to it, then the transformation flow aborts with an error.
> 
>     For more information, see [Securing Data with Data Access Controls](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/a032e51c730147c7a1fcac125b4cfe14.html "Users with a space administrator role can create data access controls to allow modelers to apply row-level security to Data Builder and Business Builder objects. Once a data access control is applied to an object, any user viewing its data either directly or via an object using it as a source, will see only those records they are authorized to view, based on the specified criteria.") :arrow_upper_right:.
> 
> -   The runtime is different if you are running a transformation flow in an SAP HANA space or a transformation flow in a file space. Indeed with file spaces, space administrators enable the object store to enhance space capabilities to support business scenarios with storage of large amounts of data at lower cost.



<a name="loio5b591d4998fa4a148750016a29ada91e__section_bqf_5q3_pzb"/>

## Create a Schedule to Run Your Flow

You can also create a schedule to run your data flow or your transformation flow on regular basis. Click <span class="FPA-icons-V3"></span> \(Schedule\) and define your schedule. For more information, see [Scheduling Data Integration Tasks](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/7fa07621d9c0452a978cb2cc8e4cd2b1.html "Schedule data integration tasks to run periodically at a specified date or time.") :arrow_upper_right:.

> ### Note:  
> For optimal performance, it is recommended that you consider staggering the scheduled run time of tasks such as data flows or task chains that may contain these tasks. Make sure to distribute your work such as scheduling and running tasks. There isn't a specific numerical limit on how many tasks can be scheduled. There could be a resource distribution issue caused by too many tasks running at once. Check your system monitor to look at your workload distribution. For more information see, [Monitoring SAP Datasphere](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/28910cded17a42a0bf16225309cb8bf6.html "Users with an administrator role have access to various monitoring logs and views and can, if necessary, create database analysis users to help troubleshoot issues.") :arrow_upper_right: or [Persisted Views and Memory Consumption](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/e3d04951a4a344c28b25b2b1b13bf3d8.html "You want to persist a complex view and consider how it affects the memory consumption.") :arrow_upper_right:.

> ### Note:  
> In very rare situations, an error may occur the first time that a scheduled data flow is run in a space. In this case, you should run the data flow manually once. Subsequent scheduled runs will not require further intervention.



<a name="loio5b591d4998fa4a148750016a29ada91e__section_hh4_pr3_pzb"/>

## Run Your Data Flow Using a Task Chain

You can run a flow using a task chain. For more information, see [Creating a Task Chain](creating-a-task-chain-d1afbc2.md).

Alternatively, you can also run your flows from the <span class="FPA-icons-V3"></span> \( Data Integration Monitor\).

From the *Flows* monitor, you can check details of your runs, and perform other actions on your flows. For more information, see [Monitoring Flows](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/b661ea0766a24c7d839df950330a89fd.html "In the Flows monitor, you can find all the deployed flows per space.") :arrow_upper_right:.

