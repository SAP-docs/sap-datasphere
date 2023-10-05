<!-- loioe30fd1417e954577baae3246ea470c3f -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Creating a Data Flow

Create a data flow to move and transform data in an intuitive graphical interface. You can drag and drop sources from the *Source Browser*, join them as appropriate, add other operators to remove or create columns, aggregate data, and do Python scripting, before writing the data to the target table.



<a name="loioe30fd1417e954577baae3246ea470c3f__context_rpc_sxj_pwb"/>

## Context

> ### Note:  
> Data flows support loading data exclusively to local tables in the SAP Datasphere repository.



<a name="loioe30fd1417e954577baae3246ea470c3f__steps_wbn_zjx_1mb"/>

## Procedure

1.  In the side navigation area, click ![](../Creating-Finding-Sharing-Objects/images/Data_Builder_f73dc45.png) \(*Data Builder*\), select a space if necessary, and click *New Data Flow* to open the editor.

2.  Add one or more objects from the *Source Browser* panel on the left of the screen as sources \(see [Add a Source](add-a-source-7b50e8e.md)\).

    > ### Note:  
    > Data flow currently doesn't support double quotes in column names, table names, owners, or other identifiers. If the source or target operators in a data flow contains double quotes, we recommend you to create a view in the source or in SAP Datasphere that renames the columns containing double quotes.

    > ### Restriction:  
    > Data flows don't support spatial data type columns.

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
    
    <span class="FPA-icons"></span> \(Preview Data\)


    
    </td>
    <td valign="top">
    
    Click to preview data of the selected operator. The Data Preview section is displayed.

    > ### Note:  
    > -   If the table is wide or contains a number of large column types, the result in data preview may be truncated in order to avoid out of memory issues.
    > -   Data preview is **not** available for ABAP sources. Also you can't perform data preview on the transformation operators.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    <span class="FPA-icons"></span> \(Remove\)


    
    </td>
    <td valign="top">
    
    Click to delete the selected operator.

    > ### Note:  
    > You can also delete the selected operator by clicking <span class="FPA-icons"></span> in the toolbar.


    
    </td>
    </tr>
    </table>
    
    > ### Tip:  
    > In the toolbar, you can use <span class="SAP-icons"></span> \(Auto Layout\) and :desktop_computer: to organize the objects in your canvas.

5.  Add or create a target table that the data flow will write its data to \(see [Add or Create a Target Table](add-or-create-a-target-table-0fa7805.md)\).

6.  Click <span class="FPA-icons"></span> \(Save\) to save the data flow:

    -   *Save* to save the data flow.
    -   *Save As* to create a local a copy of the data flow. The data flow must have been previously saved at least once. The *Save* dialog opens. Enter new business and technical names and click *Save*.

7.  Click <span class="SAP-icons"></span> \(Deploy\) to deploy the data flow:

    -   Newly created data flows are deployed for the first time.
    -   Data flows that have changes to deploy are redeployed.

    With deployment, you will be able to save draft version of your data flow without affecting the execution.

    > ### Note:  
    > In very rare situations, an error may occur the first time that a scheduled data flow is run in a space. In this case, you should run the data flow manually once. Subsequent scheduled runs will not require further intervention.

8.  To create schedule for the data flow, click <span class="FPA-icons"></span> \(Schedule\):

    -   *Create Schedule*: Create a schedule to run the data flow asynchronously and recurrently in the background according to the settings defined in the schedule.

        For more information, see [Scheduling Data Integration Tasks](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/7fa07621d9c0452a978cb2cc8e4cd2b1.html "Schedule data integration tasks to run periodically at a specified date or time.") :arrow_upper_right:.

    -   *Edit Schedule*: Change how the schedule is specified, or change the owner of the schedule.

        For more information, see [Take Over the Ownership of a Schedule](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/4b660c0395454bd0923f732eef4ee4b2.html "Per default, the user who creates a task schedule owns the schedule which means that the job scheduling component runs the task on the owner's behalf according to the defined schedule. You can assign the ownership of the schedule to yourself.") :arrow_upper_right:.

    -   *Delete Schedule*: Delete the schedule if necessary .

    > ### Note:  
    > For optimal performance, it is recommended that you consider staggering the scheduled run time of tasks such as data flows and task chains that may contain these tasks. There is a limit on how many tasks can be started at the same time. If you come close to this limit, scheduled task runs may be delayed and, if you go beyond the limit, some scheduled task runs might even be skipped.

9.  To run the data flow, click *Run*.

    If the data flow contains input parameters, a dialog box appears prompting the user to enter a value for each input parameter. You can either keep the default value or override it \(see [Create an Input Parameter](create-an-input-parameter-a6fb3e7.md)\).

10. To view the *Run Status* section in the data flow properties panel, click the diagram background.

11. To see more details about the run, open the *Data Flow Monitor* by clicking <span class="FPA-icons"></span> \(Open in Data Integration Monitor\).

    > ### Note:  
    > -   The initialization time for executing a data flow takes an average of 20 seconds even with smaller data loads causing longer runtime for the data flow.
    > -   Metrics are displayed only for source and target tables and can be used for further analysis.
    > -   In your data flow, if a source view or an underlying view of the source view has data access controls applied to it, then no data is read from the view during the execution of the data flow. This results in incorrect data or no data in the output.
    > 
    >     For more information, see [Securing Data with Data Access Controls](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/a032e51c730147c7a1fcac125b4cfe14.html "Data access controls allow you to apply row-level security to your objects. When a data access control is applied to a data layer view or a business layer object, any user viewing its data will see only the rows for which they are authorized, based on the specified criteria.") :arrow_upper_right:.

12. You can configure more properties for a data flow, in the *Advanced Properties* section of the *Properties* panel.

    -   To allocate memory usage for your data flow manually, enable the *Dynamic Memory Allocation* option.

        -   Set the *Expected Data Volume* to *Small*, *Medium*, or *Large*.

        > ### Note:  
        > -   Dynamic memory allocation should be done only if your data flow run is facing out-of-memory failures.
        > -   If multiple data flows are scheduled with *Expected Data Volume* as large, it doesn't alter/increase the actual memory needed for the data flow. However, the execution engine will allocate enough memory to handle such large volume of data and only after successful memory allocation, the data flow run is started.
        > 
        >     Execution engine allocates memory based on the data volume configured and the complexity of the operations performed in the data flow.

    -   To restart the data flow automatically if there are any failures or system upgrades, enable the *Automatic restart on run failure* checkbox.


