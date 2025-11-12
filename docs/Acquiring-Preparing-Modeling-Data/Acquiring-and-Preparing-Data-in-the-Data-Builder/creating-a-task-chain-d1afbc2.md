<!-- loiod1afbc2b9ee84d44a00b0b777ac243e1 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Creating a Task Chain

Group multiple tasks into a task chain and run them manually once, or periodically, through a schedule.



<a name="loiod1afbc2b9ee84d44a00b0b777ac243e1__prereq_ccw_sdc_gtb"/>

## Prerequisites

To create task chains, you must have a scoped role that grants you access to a space with the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Data Warehouse Data Builder* \(`CRUD----`\) - To create, edit and delete task chains.
-   *Space Files* \(`CRUD----`\) - To create, read, update, and delete objects in your spaces.

To run and share task chains and configure email notifications, you must, in addition, have the following privileges:

-   *Data Warehouse Data Integration* \(`-RU-----`\) - To manually run task chains.
-   *Data Warehouse Data Integration* \(`-R--E---`\) - To schedule task chains.
-   *Data Warehouse Data Builder* \(`------S-`\) - To share task chains to other spaces.
-   *User* \(`R-------`\) - To display and add notification recipients from a list of current tenant members, when setting up email notifications.

The *DW Modeler* and *DW Space Administrator* role templates together, for example, grant these privileges. For more information, see [Privileges and Permissions](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/d7350c6823a14733a7a5727bad8371aa.html "A privilege represents a task or an area in SAP Datasphere and can be assigned to a specific role. The actions that can be performed in the area are determined by the permissions assigned to a privilege.") :arrow_upper_right: and [Standard Roles Delivered with SAP Datasphere](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/a50a51d80d5746c9b805a2aacbb7e4ee.html "SAP Datasphere is delivered with several standard roles. A standard role includes a predefined set of privileges and permissions.") :arrow_upper_right:. 

The following prerequisites also apply:

-   For SAP HANA Open SQL schema procedures to be available for users to include in a task chain, the schema’s owner must grant EXECUTE privileges to the space user for objects in the Open SQL schema. See [Allow the Space to Access the Open SQL Schema](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/7eaa370fe4624dea9f182ee9c9ab645f.html "To grant the space write privileges in the Open SQL schema and the ability to write data to target tables in the schema, use the GRANT_PRIVILEGE_TO_SPACE stored procedure. Once this is done, data flows running in the space can select tables in the Open SQL schema as targets and write data to them, and task chains can run procedures in the schema.") :arrow_upper_right:.
-   Objects must have been already deployed, so that they can be added to the task chain. Task chains must also be deployed to allow selection of tenant users or specify email addresses for notification of task chain completion.

-   Persisting of views may include one parameter that uses the default value defined with the view. Views must not have data access controls assigned to them.

-   If a data flow that has input parameters is included in a task chain, task chain runs will use default parameter values defined for the data flow.
-   A replication flow can be included in a task chain if all objects in the flow have load type *Initial Only*.




## Context

You can create task chains that include SAP Datasphere repository objects, that is, Remote Tables and Views, Local Tables, Intelligent Lookups, Data Flows, Replication Flows \(load type *Initial Only*\), and Transformation Flows. You can also include non-repository objects such as SAP HANA Open SQL schema procedures and SAP BW Bridge process chains. In addition, you can nest other existing, locally-created or shared task chains in other task chains, as well as share task chains you've created to other spaces.

In addition to the objects available from the Repository or Others tabs, you can also add two other additional objects to task chains that are only available from the task chain toolbar. The *API Task* object lets you configure and run API asks to access external systems. The *Notification Task* object lets you configure email notification for individual task chain tasks.

> ### Note:  
> For remote table and view objects included in a task chain, you have the option, by default, to replicate or persist the data associated with the corresponding remote tables or views. Or, you can choose to remove the replicated or persisted data by selecting that option in the *Activities* section of an object’s *Properties* detail display.
> 
> -   For remote tables, if you choose the *Remove Replicated Data* option and the remote table object already has data replicated using Snapshot Replication, the replicated data will be removed and the data will be read directly from the remote source and no longer from the repository. For more information, see [Monitoring Remote Tables](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/4dd95d7bff1f48b399c8b55dbdd34b9e.html "In the Remote Tables monitor, you can find a remote table monitor per space. Here, you can copy data from remote tables that have been deployed in your space into SAP Datasphere, and you can monitor the replication of the data. You can copy or schedule copying the full set of data from the source, or you can set up replication of data changes in real-time via change data capturing (CDC).") :arrow_upper_right:. If the data is being replicated via Real Time Replication, the data will also be removed and the object’s data access method will be changed to Remote access. \(A log message will be displayed in the remote table's log to indicate that the data access type has been changed when the remote table object is run.\)
> 
> -   For views, if you choose the *Remove Persisted Data* option, data persistence will be removed and the view data will be read from the remote source and no longer from the repository. For more information, see [Persisting and Monitoring Views](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/9af04c990f294fd28c00f46763dd8b0d.html "From Data Integration Monitor > > Views , you can monitor views that have been created in the Data Builder. You can persist these views (direct run or via a schedule) to make them available locally to improve the performance when accessing your data. You can monitor the existing persisted views to keep control of your data sizing and free up memory space.") :arrow_upper_right:.
> 
> If replication and data removal tasks are both attempted to run at the same time, the tasks are given priority based on a first-come, first served basis.

When creating a task chain, you can create linear task chains in which one task is run after another. A succeeding task is only run once the previous task in the series has finished successfully with a *completed* status. The running of tasks in the series will not resume if the previous task has a *failed* status. You can also create task chains in which individual tasks are run in parallel and successful continuation of the entire task chain run depends on whether ANY or ALL parallel tasks are completed successfully.

> ### Note:  
> For optimal performance, it is recommended that you consider staggering the scheduled run time of tasks such as data flows or task chains that may contain these tasks. Make sure to distribute your work such as scheduling and running tasks. There isn't a specific numerical limit on how many tasks can be scheduled. There could be a resource distribution issue caused by too many tasks running at once. Check your system monitor to look at your workload distribution. For more information see, [Monitoring SAP Datasphere](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/28910cded17a42a0bf16225309cb8bf6.html "Users with an administrator role have access to various monitoring logs and views and can, if necessary, create database analysis users to help troubleshoot issues.") :arrow_upper_right: or [Persisted Views and Memory Consumption](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/e3d04951a4a344c28b25b2b1b13bf3d8.html "You want to persist a complex view and consider how it affects the memory consumption.") :arrow_upper_right:.

When creating or editing a task chain, you can also set up email notification for deployed task chains to notify selected users of task chain completion. After deploying a task chain, you can add tenant users or email addresses to notify individuals when task chain runs are completed.

You can monitor the status of task chain runs from the Data Integration Monitor. For more information, see [Monitoring Task Chains](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/4142201ec1aa49faad89a688a2f1852c.html "Monitor the status and progress of running and previously run task chains.") :arrow_upper_right:.

In addition to working with task chains in the editor, you can also:

-   List, create, read, update, and delete them using the `datasphere` command line interface \(see [Manage Modeling Objects and Tasks via the Command Line](https://help.sap.com/viewer/d0ecd6f297ac40249072a44df0549c1a/cloud/en-US/6f5c65f209004751aa48f9682ee2ec45.html "Users with a modeler role can use the datasphere command line interface to list, create, update, and delete modeling objects.") :arrow_upper_right:\).
-   Export and import them via the secure *Transport* app \(see [Transporting Content Between Tenants](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/df12666cf98e41248ef2251c564b0166.html "Users with an administrator or space administrator role can use the Transport app to transfer content between tenants via a private cloud storage area.") :arrow_upper_right:\).
-   Export and import them via CSN files \(see [Importing and Exporting Objects in CSN/JSON Files](../Creating-Finding-Sharing-Objects/importing-and-exporting-objects-in-csn-json-files-f8ff062.md)\).



## Procedure

1.  From the *Data Builder*, click *New Task Chain*.

2.  From the left-side panel, drag and drop a first object on to the task chain canvas from those available in the repository \(from the *Repository* tab\), or non-repository objects \(selected from the *Others* tab\).

    > ### Note:  
    > From the *Repository* tab, you can see the remote tables, views, intelligent lookups, data flow, replication flow, transformation flow objects and task chains that meet prerequisites and are available to be added to the task chain. Task chains you've shared or have been shared with you from another space are denoted by the <span class="FPA-icons-V3"></span> \(Share\) icon following the task chain's business name. For more information on sharing and running shared task chains, see [Nest and Share Task Chains](nest-and-share-task-chains-8067b77.md).
    > 
    > From the *Others* tab, you can see the non-repository Open SQL schema procedures and BW Bridge process chains you can add to a task chain. For more information on adding Open SQL schema procedures from the Others tab, see [Run Open SQL Procedures in a Task Chain](run-open-sql-procedures-in-a-task-chain-59b9c77.md). For more information on adding BW Bridge process chains to a task chain, see [Run BW Bridge Process Chains in a Task Chain](run-bw-bridge-process-chains-in-a-task-chain-7d7d02a.md).
    > 
    > In addition to the objects available from the Repository or Others tabs, you can also add two other additional objects to task chains that are only available from the task chain toolbar. The *API Task* object lets you configure API Tasks to access external systems. \(For more information, see [Run API Tasks in a Task Chain](run-api-tasks-in-a-task-chain-9a8489e.md).\) The *Notification Task* object lets you configure email notification for individual task chain tasks. \(For more information, see [Configure Email Notification](configure-email-notification-7ff6a4e.md).\)

3.  Drag a second object on to the first object in the task chain. As you drag the object over the top of the first object, a context menu displays options *Add as New Task* \(the default\), *Replace Existing*, or *Add as Parallel* to place the new object in the linear arrangement of tasks in the task chain, or as a task in parallel with a selected task.

    Choosing the *Add as New Task* option automatically connects the new object task to the previous object task. The properties panel for the task chain is also updated with the added objects.

    > ### Note:  
    > Options on the task chain toolbar in the *Plus Sign* \(*\+*\) menu also let you add new task objects to the task chain. The *Add Placeholder after Selected Task* option places a new task object placeholder in the existing linear arrangement of tasks in the task chain. The *Add Parallel Branch after Selected Task* option places a new task object placeholder in parallel with the currently selected task. For more information on creating task chains with parallel task branches, see [Run Parallel Tasks in a Task Chain](run-parallel-tasks-in-a-task-chain-363ffe9.md).

4.  Continue adding remaining object tasks you want to include in the task chain.

    In addition to adding or replacing object tasks in a task chain, you can drag objects already on the task chain canvas to change the order in which tasks are run. By default, tasks in a task chain are displayed in a vertical direction, from top to bottom. On the left side of the task chain toolbar, the *Layout* menu provides options to let you change the orientation of tasks from Top to Bottom \(*Top-Bottom*\) to Left to Right \(*Left-Right*\).

5.  In the properties panel, specify a name for the task chain.

    ![](images/Task_chain_repository_listing_and_properties_55f7187.png)

    Task chain properties:


    <table>
    <tr>
    <th valign="top">

    Properties
    
    </th>
    <th valign="top">

    Comments
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Business Name
    
    </td>
    <td valign="top">
    
    Enter a descriptive name to help users identify the object. This name can be changed at any time. 
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Technical Name
    
    </td>
    <td valign="top">
    
    Displays the name used in scripts and code, synchronized by default with the *Business Name*. 
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Package
    
    </td>
    <td valign="top">
    
    Select the package to which the object belongs. 

    Packages are used to group related objects in order to facilitate their transport between tenants.

    > ### Note:  
    > Once a package is selected, it cannot be changed here. Only a user with the DW Space Administrator role \(or equivalent privileges\) can modify a package assignment in the *Packages* editor.

    For more information, see [Creating Packages to Export](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/24aba84ceeb3416881736f70f02e3a0a.html "Users with the DW Space Administrator role can create packages to model groups of related objects for transport between tenants. Modelers can add objects to packages via the Package field, which appears in editors when a package is created in their space. Once a package is complete and validated, the space administrator can export it to the Content Network. The structure of your package is preserved and, as the objects it contains evolve, you can easily export updated versions of it.") :arrow_upper_right:.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Status
    
    </td>
    <td valign="top">
    
    Displays the deployment status of the task chain: it can be deployed, not deployed, or changes to deploy.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Objects in Task Chain
    
    </td>
    <td valign="top">
    
    Displays all objects that have been added to the task chain.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Run Status
    
    </td>
    <td valign="top">
    
    Displays the current run status of the task chain: Not run yet, running, failed, or completed.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Email Notifications
    
    </td>
    <td valign="top">
    
    Set up email notification for task chain run completion.
    
    </td>
    </tr>
    </table>
    
    When you click on one of the task chain objects, the properties for this selected task object is displayed in the properties panel:

    ![](images/Select_Open_Object_08d0613.png)

    Note that you can also access the details of each task chain object in the task chain properties panel. Select the relevant object in the object list and click <span class="SAP-icons-V5"></span>:

    ![](images/View_Detail_Object_fc2af80.png)

    Task chain object properties:


    <table>
    <tr>
    <th valign="top">

    Properties
    
    </th>
    <th valign="top">

    Comments
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Business Name
    
    </td>
    <td valign="top">
    
    Name of the object
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Technical Name
    
    </td>
    <td valign="top">
    
    Technical name of the object
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Object Type
    
    </td>
    <td valign="top">
    
    A remote table, view, intelligent lookup, data flow, local table, replication flow \(load type *Initial Only*\), or transformation flow.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Activity
    
    </td>
    <td valign="top">
    
    Activity that will be triggered by the task chain.

    *Repository Objects:*

    -   Remote table - Replicate

    -   View - Persist
    -   Intelligent lookup - Run
    -   Data flow - Run
    -   Replication Flow - Run
    -   Transformation flow - Run
    -   Local table - Delete Records with Change Type "Deleted"
    -   Local Table \(File\) - Merge, Optimize or Delete Records.

        > ### Note:  
        > -   Merge: Add, update or delete data into the existing local table \(file\). Data updates are pushed by a replication flow or SAP BW to the inbound buffer \(specific folder in file storage\) of a target local table \(file\). To process data updates from this inbound buffer to the local table \(file\), and therefore make data visible, a merge task has to run..
        > -   Optimize: Improve data access performance by optimizing the layout of data in file storage \(for example by grouping small files into larger files\)..
        > -   Delete Records: Delete records from your local table \(file\). Under Settings, define what type of deletion you want:
        >     -   *Delete All Records \(Mark as Deleted\)*: Records will not be physically deleted but marked as deleted and filtered out when accessing the active records of the local table. They will still consume storage, and they can still be processed by other apps that consume them.
        >     -   *Delete Previous Versions \(Vacuum\), which are older than the specified number of days*: You delete previous versions, which are older than the number of days you have specified. Records that meet your defined criteria will be permanently deleted. Default value is 90 days. Minimum authorized value is 7 so that records from the last 7 days cannot be deleted. In addition, only records that have been fully processed can be deleted. 
        > 
        > 
        > For more information on local tables \(file\), see [Creating a Local Table \(File\)](creating-a-local-table-file-d21881b.md) and [Deleting Local Table \(File\) Records](deleting-local-table-file-records-6ec9b8a.md).

        \[Optional\]. When you select one of these options, you can override the default *Apache Spark Application Settings* that were defined at space creation by your administrator.

    -   Task Chain - Run

    For remote table and view objects included in a task chain, the default option lets you replicate or persist the data associated with the remote table or view respectively. Or, you can choose to remove the replicated or persisted data.

    -   For remote tables, if you choose the *Remove Replicated Data* option and the remote table object already has data replicated using Snapshot Replication, that table's data will be removed. If the data is being replicated via Real Time Replication, the table's data will also be removed and the object’s data access method will be changed to Remote access. \(A log message will be displayed in the remote table log to indicate that the data access type has been changed when the remote table object is run.\)

    -   For views, if you choose the *Remove Persisted Data* option, that view's data will be removed.

    *Other \(Non-Repository\) Objects:*

    -   BW Process Chains - Run \(For more information, see [Run BW Bridge Process Chains in a Task Chain](run-bw-bridge-process-chains-in-a-task-chain-7d7d02a.md)\)
    -   SQL Script Procedures - Run \(For more information, see [Run Open SQL Procedures in a Task Chain](run-open-sql-procedures-in-a-task-chain-59b9c77.md)\)

    *Task Chain Toolbar Objects:*

    -   API Tasks - Run \(For more information, see [Run API Tasks in a Task Chain](run-api-tasks-in-a-task-chain-9a8489e.md).\)
    -   Notification Tasks - Run \(For more information, see [Configure Email Notification](configure-email-notification-7ff6a4e.md).\)


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Apache Spark Settings
    
    </td>
    <td valign="top">
    
    \[File Space Only\] When creating a file space, administrators have defined default *Apache Spark Applications* to run tasks \(in Workload Management\). You can update these settings following your needs by object types:

    -   *Use Default*: The default application is the application selected in the table settings. If no default application is defined there, the application selected by an administrator during the file space creation is used. However, if the settings have been changed on the object level, in the data integration monitor, this value has become the default value, erasing the value defined in *Workload Management*.
    -   *Define New Setting for This Task*: Select another *Apache Spark Application* that fits your needs.

    For more information, see [Merge or Optimize Your Local Tables (File)](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/e533b154ed3e49ce9a03e4421a5296e7.html "Local Tables (File) can store large quantities of data in the object store. You can manage this file storage with merge or optimize tasks, and allocate the required amount of compute resources that the file space can consume when processing these tasks.") :arrow_upper_right: and [Override the Default Settings to Run Your Transformation Flow (in a File Space)](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/e5c4ac8ab3bf4573b86cd4f4f3118c16.html "Update the maximum amount of compute resources that the file space can consume to run a transformation flow.") :arrow_upper_right:.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Status
    
    </td>
    <td valign="top">
    
    Deployment status of the task chain: it can be deployed, not deployed, or changes to deploy
    
    </td>
    </tr>
    </table>
    
    When you add a shared task chain to the current task chain, the Properties display also lists the space from which the task chain was shared, when that object is selected.

    > ### Note:  
    > When you select an object, you can also delete it from the task chain or navigate to the corresponding editor for that object.

6.  When you’ve finished adding objects to the task chain, save and deploy your new task chain.

    The properties of your task chain are updated.

    ![](images/Properties_Update_with_Deploy_3674719.png)

    > ### Note:  
    > SAP Datasphere allows you to save task chains that may have unconnected task objects on the canvas. However, you will not be able to deploy and run them until all task objects are connected to define their order of execution when the task chain is run.

    After creating and deploying a task chain, you can optionally set up email notification for completion of task chain runs. For more information, see [Configure Email Notification](configure-email-notification-7ff6a4e.md).

    After you've finished making changes and optionally setting up email notification for the task chain, you can then run the task chain or create a schedule to run your task chain periodically, and navigate to the *Task Chains* monitor to check your task chain runs. For more information, see [Run a Task Chain](run-a-task-chain-684bd8b.md), [Scheduling Data Integration Tasks](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/7fa07621d9c0452a978cb2cc8e4cd2b1.html "Schedule data integration tasks to run periodically at a specified date or time.") :arrow_upper_right:, and [Monitoring Task Chains](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/4142201ec1aa49faad89a688a2f1852c.html "Monitor the status and progress of running and previously run task chains.") :arrow_upper_right:.

    > ### Note:  
    > In addition to running a task chain, you can also share or export the task chain following deployment:
    > 
    > -   To share a task chain to another space, click the editor toolbar <span class="FPA-icons-V3"></span> \(Share\) icon. You are then prompted to specify one or more spaces you want to share the task chain to. For more information, see [Sharing Entities and Task Chains to Other Spaces](../Creating-Finding-Sharing-Objects/sharing-entities-and-task-chains-to-other-spaces-64b318f.md).
    > -   To export the definition of a task chain to a CSN/JSON file, which may later be imported again in the same space or other spaces, click the <span class="FPA-icons-V3"></span> \(Export\) icon. Note that the exported file does not create the objects defined in the task chain or include the recipients of email notification for the exported task chain. For more information on exporting objects, see [Exporting Objects to a CSN/JSON File](../Creating-Finding-Sharing-Objects/exporting-objects-to-a-csn-json-file-3916101.md).

7.  The tools in the editor toolbar help you work with your object throughout its lifecycle:


    <table>
    <tr>
    <th valign="top">

    Tool
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    <span class="FPA-icons-V3"></span> \(Save\)
    
    </td>
    <td valign="top">
    
    Save your changes to the design-time repository. You can use *Save As* to create a copy of the object. 

    See [Saving and Deploying Objects](../saving-and-deploying-objects-7c0b560.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    <span class="SAP-icons-V5"></span> \(Deploy\)
    
    </td>
    <td valign="top">
    
    Deploy your changes to make them available in the run-time environment.

    See [Saving and Deploying Objects](../saving-and-deploying-objects-7c0b560.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    <span class="FPA-icons-V3"></span> \(Run\)
    
    </td>
    <td valign="top">
    
    Run the object to obtain or update its output results.

    You must deploy the object before you can run it.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    <span class="FPA-icons-V3"></span> \(Share\)
    
    </td>
    <td valign="top">
    
    Share the object to other spaces.

    See [Sharing Entities and Task Chains to Other Spaces](../Creating-Finding-Sharing-Objects/sharing-entities-and-task-chains-to-other-spaces-64b318f.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    <span class="FPA-icons-V3"></span> \(Source Browser\)
    
    </td>
    <td valign="top">
    
    Show the *Source Browser* panel to drag objects into the task chain. 

    See [Using the Source Browser](../using-the-source-browser-7d2b21d.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    <span class="FPA-icons-V3"></span> \(Undo\) / <span class="FPA-icons-V3"></span> \(Redo\)
    
    </td>
    <td valign="top">
    
    Revert the last change to the object or redo a change you have previously undone.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    <span class="FPA-icons-V3"></span> \(Export\)
    
    </td>
    <td valign="top">
    
    Export the object to a CSN/JSON file.

    See [Exporting Objects to a CSN/JSON File](../Creating-Finding-Sharing-Objects/exporting-objects-to-a-csn-json-file-3916101.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    <span class="FPA-icons-V3"></span> \(Impact and Lineage Analysis\)
    
    </td>
    <td valign="top">
    
    Open the *Impact and Lineage Analysis* graph for the object. 

    See [Impact and Lineage Analysis](../impact-and-lineage-analysis-9da4892.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Versions
    
    </td>
    <td valign="top">
    
    Open the *Version History* dialog for the object. 

    See [Reviewing and Restoring Object Versions](../reviewing-and-restoring-object-versions-4f717cc.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Details
    
    </td>
    <td valign="top">
    
    Toggles the display of the *Properties* panel.
    
    </td>
    </tr>
    </table>
    

