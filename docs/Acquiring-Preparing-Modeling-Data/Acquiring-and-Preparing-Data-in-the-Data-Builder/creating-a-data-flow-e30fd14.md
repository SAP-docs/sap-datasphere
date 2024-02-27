<!-- loioe30fd1417e954577baae3246ea470c3f -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Creating a Data Flow

Create a data flow to move and transform data in an intuitive graphical interface. You can drag and drop sources from the *Source Browser*, join them as appropriate, add other operators to remove or create columns, aggregate data, and do Python scripting, before writing the data to the target table.



<a name="loioe30fd1417e954577baae3246ea470c3f__context_rpc_sxj_pwb"/>

## Context

> ### Note:  
> For optimal performance, it is recommended that you consider staggering the scheduled run time of tasks such as data flows and task chains that may contain these tasks. There is a limit on how many tasks can be started at the same time. If you come close to this limit, scheduled task runs may be delayed and, if you go beyond the limit, some scheduled task runs might even be skipped.



<a name="loioe30fd1417e954577baae3246ea470c3f__steps_wbn_zjx_1mb"/>

## Procedure

1.  In the side navigation area, click ![](../Creating-Finding-Sharing-Objects/images/Data_Builder_f73dc45.png) \(*Data Builder*\), select a space if necessary, and click *New Data Flow* to open the editor.

2.  Drag one or more source objects from the *Source Browser* and drop it into the diagram \(see [Add a Source](add-a-source-7b50e8e.md)\).

    > ### Restriction:  
    > -   Data flows support loading data exclusively to local tables in the SAP Datasphere repository.
    > 
    > -   Data flow currently doesn't support double quotes in column names, table names, owners, or other identifiers. If the source or target operators in a data flow contains double quotes, we recommend you to create a view in the source or in SAP Datasphere that renames the columns containing double quotes.
    > 
    > -   Data flows don't support spatial data type columns.

3.  Transform your data using one or more operators:

    -   *Join* - Insert a join operator to merge two data sets together using a join definition to match the records. See [Create a Join Operator](create-a-join-operator-e57633d.md).
    -   *Union* - Insert a union operator to combine two data sets that share the same schema definition. See [Create a Union Operator](create-a-union-operator-e0a3804.md).
    -   *Projection* - Insert a projection operator to add, remove, reorder, or rename columns. See [Create a Projection Operator](create-a-projection-operator-912f740.md).
    -   *Aggregation* - Insert an aggregation operator to perform `SUM`, `AVG`, `MIN`, `MAX`, or `COUNT` calculations. See [Create an Aggregation](create-an-aggregation-328d28f.md).
    -   *Script* - Insert a script operator to transform incoming data with a Python script and output structured data to the next operator. See [Create a Script Operator](create-a-script-operator-f3e2570.md).

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

    \(see [Impact and Lineage Analysis](../Creating-Finding-Sharing-Objects/impact-and-lineage-analysis-9da4892.md).\)
    
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

    For more information, see [Add or Create a Target Table](add-or-create-a-target-table-0fa7805.md).

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

        For more information, see [Saving and Deploying Objects](../Creating-Finding-Sharing-Objects/saving-and-deploying-objects-7c0b560.md).
        
        </td>
        </tr>
        </table>
        
    -   Under Run Status:

        Displays the status of the flow run:

        -   *Running*: The flow is currently running.
        -   *Completed*: The flow is completed successfully.
        -   *Failed*: Something goes wrong during the flow run and it could not be completed. Go to the details screen of your flow run and check the logs to identify to issue.

    -   Under Input Parameters:Create a new input parameter or modify an existing one. For more information, see [Create an Input Parameter](create-an-input-parameter-a6fb3e7.md)
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


