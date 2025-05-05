<!-- loioe30fd1417e954577baae3246ea470c3f -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Creating a Data Flow

Create a data flow to move and transform data in an intuitive graphical interface. You can drag and drop sources from the *Source Browser*, join them as appropriate, add other operators to remove or create columns, aggregate data, and do Python scripting, before writing the data to the target table.



<a name="loioe30fd1417e954577baae3246ea470c3f__context_rpc_sxj_pwb"/>

## Context

> ### Remember:  
> Data flows don't support delta processing. If you want to load delta data from an external source into SAP Datasphere, use a replication flow instead. See [Creating a Replication Flow](creating-a-replication-flow-25e2bd7.md)

> ### Note:  
> For optimal performance, it is recommended that you consider staggering the scheduled run time of tasks such as data flows or task chains that may contain these tasks. Make sure to distribute your work such as scheduling and running tasks. There isn't a specific numerical limit on how many tasks can be scheduled.. There could be a resource distribution issue caused by too many tasks running at once. Check your system monitor to look at your workload distribution. For more information see, [Monitoring SAP Datasphere](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/28910cded17a42a0bf16225309cb8bf6.html "Users with an administrator role have access to various monitoring logs and views and can, if necessary, create database analysis users to help troubleshoot issues.") :arrow_upper_right: or [Persisted Views and Memory Consumption](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/e3d04951a4a344c28b25b2b1b13bf3d8.html "You want to persist a complex view and consider how it affects the memory consumption.") :arrow_upper_right:.

In addition to working with flows in the editor, you can also:

-   List, create, read, update, and delete them using the `datasphere` command line interface \(see [Manage Modeling Objects via the Command Line](https://help.sap.com/viewer/9b8363ae47c347de9a027c0e5567a37a/DEV_CURRENT/en-US/6f5c65f209004751aa48f9682ee2ec45.html "Users with a modeler role can use the datasphere command line interface to list, create, update, and delete modeling objects.") :arrow_upper_right:\).
-   Export and import them via the secure *Transport* app \(see [Transporting Content Between Tenants](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/df12666cf98e41248ef2251c564b0166.html "Users with an administrator or space administrator role can use the Transport app to transfer content between tenants via a private cloud storage area.") :arrow_upper_right:\).
-   Export and import them via CSN files \(see [Importing and Exporting Objects in CSN/JSON Files](../Creating-Finding-Sharing-Objects/importing-and-exporting-objects-in-csn-json-files-f8ff062.md)\).



<a name="loioe30fd1417e954577baae3246ea470c3f__steps_wbn_zjx_1mb"/>

## Procedure

1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(*Data Builder*\), select a space if necessary, and click *New Data Flow* to open the editor.

2.  Drag one or more source objects from the *Source Browser* and drop it into the diagram \(see [Add a Source to a Data Flow](add-a-source-to-a-data-flow-7b50e8e.md)\).

    > ### Restriction:  
    > -   Data flows support loading data exclusively to local tables in the SAP Datasphere repository.
    > 
    > -   Data flow currently doesn't support double quotes in column names, table names, owners, or other identifiers. If the source or target operators in a data flow contains double quotes, we recommend you to create a view in the source or in SAP Datasphere that renames the columns containing double quotes.
    > 
    > -   Data flows don't support spatial data type columns.

3.  Transform your data using one or more operators:

    -   *Join* - Insert a join operator to merge two data sets together using a join definition to match the records. See [Create a Join in a Data Flow](create-a-join-in-a-data-flow-e57633d.md).
    -   *Union* - Insert a union operator to combine two data sets that share the same schema definition. See [Create a Union in a Data Flow](create-a-union-in-a-data-flow-e0a3804.md).
    -   *Projection* - Insert a projection operator to add, remove, reorder, or rename columns. See [Create a Projection in a Data Flow](create-a-projection-in-a-data-flow-912f740.md).
    -   *Aggregation* - Insert an aggregation operator to perform `SUM`, `AVG`, `MIN`, `MAX`, or `COUNT` calculations. See [Create an Aggregation in a Data Flow](create-an-aggregation-in-a-data-flow-328d28f.md).
    -   *Script* - Insert a script operator to transform incoming data with a Python script and output structured data to the next operator. See [Create a Script in a Data Flow](create-a-script-in-a-data-flow-f3e2570.md).

4.  Select an object in the canvas to display its properties in the side panel and to reveal its contextual toolbar, which contains some or all of the following tools:


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
    
    :arrow_right:
    
    </td>
    <td valign="top">
    
    Click to create a flow to another operator in the data flow. Drag and drop the yellow dotted line to the required operator to which you want to connect.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    <span class="FPA-icons-V3"></span> \(Preview Data\)
    
    </td>
    <td valign="top">
    
    Click to preview data of the selected operator. The Data Preview section is displayed.

    > ### Note:  
    > -   If the table is wide or contains a number of large column types, the result in data preview may be truncated in order to avoid out of memory issues.
    > -   Data preview is **not** available for ABAP sources. Except for:
    >     -   CDS views if the source connection is SAP S/4HANA Cloud 2302, SAP S/4HANA on-premise 1909 or higher.
    >     -   SAP Landscape Transformation Replication Server objects if ABAP Add-on DMIS 2018 SP08 / DMIS 2020 SP04 is installed.
    > 
    > -   You can't perform data preview on the transformation operators.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    <span class="FPA-icons-V3"></span> \(Add Table\)
    
    </td>
    <td valign="top">
    
    Create a new target table.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    <span class="FPA-icons-V3"></span> \(Impact and Lineage Analysis\)
    
    </td>
    <td valign="top">
    
    Open the Impact and Lineage Analysis diagram. This diagram enables you to understand the lineage and impacts of the selected object. 

    \(see [Impact and Lineage Analysis](../impact-and-lineage-analysis-9da4892.md).\)
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    <span class="FPA-icons-V3"></span> \(Open in New Tab\)
    
    </td>
    <td valign="top">
    
    Open the selected entity in its own editor in a new tab.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    <span class="FPA-icons-V3"></span> \(Remove\)
    
    </td>
    <td valign="top">
    
    Click to delete the selected operator.

    > ### Note:  
    > You can also delete the selected operator by clicking <span class="FPA-icons-V3"></span> in the toolbar.


    
    </td>
    </tr>
    </table>
    
    > ### Tip:  
    > In the toolbar, you can use <span class="SAP-icons-V5"></span> \(Auto Layout\) and :desktop_computer: to organize the objects in your canvas.

5.  Add or create a target table that the data flow will write its data to.

    > ### Note:  
    > You can only have one target table in a data flow.

    For more information, see [Add or Create a Target Table in a Data Flow](add-or-create-a-target-table-in-a-data-flow-0fa7805.md).

6.  Click on the canva and review your data flow properties in the right panel:

    -   Under *General*:


        <table>
        <tr>
        <th valign="top">

        Property
        
        </th>
        <th valign="top">

        Description
        
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

        To override the default technical name, enter a new one in the field. Technical names can contain only alphanumeric characters and underscores.

        > ### Note:  
        > Once the object is saved, the technical name can no longer be modified.


        
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

        For more information, see [Creating Packages to Export](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/24aba84ceeb3416881736f70f02e3a0a.html "Users with the DW Space Administrator role can create packages to model groups of related objects for transport between tenants. Modelers can add objects to packages via the Package field, which appears in editors when a package is created in their space. Once a package is complete and validated, the space administrator can export it to the Content Network. The structure of your package is preserved and, as the objects it contains evolve, you can easily export updated versions of it.") :arrow_upper_right:.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        Status
        
        </td>
        <td valign="top">
        
        \[read-only\] Displays the deployment and error status of the object. 

        For more information, see [Saving and Deploying Objects](../saving-and-deploying-objects-7c0b560.md).
        
        </td>
        </tr>
        </table>
        
    -   Under Run Status:

        Displays the status of the flow run:

        -   *Running*: The flow is currently running.
        -   *Completed*: The flow is completed successfully.
        -   *Failed*: Something goes wrong during the flow run and it could not be completed. Go to the details screen of your flow run and check the logs to identify to issue.

    -   Under Input Parameters:Create a new input parameter or modify an existing one. For more information, see [Create an Input Parameter in a Data Flow](create-an-input-parameter-in-a-data-flow-a6fb3e7.md)
    -   Under Advanced Properties
        -   *Dynamic Memory Allocation* You can allocate memory usage manually. Set the *Expected Data Volume* to *Small*, *Medium*, or *Large*.

            > ### Note:  
            > -   Dynamic memory allocation should be done only if your data flow run is facing out-of-memory failures.
            > -   If multiple data flows are scheduled with *Expected Data Volume* as large, it doesn't alter/increase the actual memory needed for the data flow. However, the execution engine will allocate enough memory to handle such large volume of data and only after successful memory allocation, the data flow run is started.
            > 
            >     Execution engine allocates memory based on the data volume configured and the complexity of the operations performed in the data flow.

        -   *Automatic restart on run failure*: Set this option to restart the data flow automatically if there are any failures or system upgrades, for example.


7.  Click <span class="FPA-icons-V3"></span> \(Save\) to save your data flow:

    -   *Save* to save the data flow.
    -   *Save As* to create a local a copy of the data flow. The data flow must have been previously saved at least once. The *Save* dialog opens. Enter new business and technical names and click *Save*.

8.  Click <span class="SAP-icons-V5"></span> \(Deploy\) to deploy the data flow:

    -   Newly created data flows are deployed for the first time.
    -   Data flows that have changes to deploy are redeployed.

    With deployment, you will be able to save draft version of your data flow without affecting the execution.

9.  The tools in the editor toolbar help you work with your object throughout its lifecycle:


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
    
    <span class="FPA-icons-V3"></span> \(Source Browser\)
    
    </td>
    <td valign="top">
    
    Show the *Source Browser* panel to drag sources into the editor. 

    See [Using the Source Browser](../using-the-source-browser-7d2b21d.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    <span class="FPA-icons-V3"></span> \(Preview Data\)
    
    </td>
    <td valign="top">
    
    Open the *Data Preview* panel to preview data in the selected diagram node.

    See [Viewing Object Data](../viewing-object-data-b338e4a.md).
    
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
    </table>
    

