<!-- loiof7161e6c20204672ac4a6d90c81762e4 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Creating a Transformation Flow

Create a transformation flow to load data from one or more source tables, apply transformations \(such as a join\), and output the result in a target table. You can load a full set of data from one or more source tables to a target table. You can also load delta changes \(including deleted records\) from one source table to a target table.



## Context

A transformation flow run is a one-time event that completes when the relevant data is loaded to the target table successfully. You can run a transformation flow multiple times, for example if you are loading delta changes to the target table.

Creating a transformation flow involves two important steps:

-   Using the *View Transform* operator to combine and transform data from one or more source tables.

-   Adding a target table to the transformation flow and mapping the columns from the view transform created in the first step to the target table.


> ### Note:  
> A transformation flow only supports the loading of data to a local table in the SAP Datasphere repository.



## Procedure

1.  In the side navigation area, click ![](../Creating-Finding-Sharing-Objects/images/Data_Builder_f73dc45.png) \(*Data Builder*\), select a space if necessary, and click *New Transformation Flow* to open the editor. The system displays the *New Transformation Flow* screen.

2.  You use the *View Transform* operator to load data from source tables and to transform data. Create a new *View Transform* by clicking the *Define View Transform* button \(see [Create a View Transform](create-a-view-transform-c65e37c.md)\).

3.  Click the *Back* button to return to the *Transformation Flow Editor*. Add or create a target table that the transformation flow will write its data to \(see [Add or Create a Target Table](add-or-create-a-target-table-0950746.md)\).

4.  Click the *Details* button to display the *Transformation Flow Properties* panel.

    In the *General* section, you can view the following properties:


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
    
    Business Name / Technical Name


    
    </td>
    <td valign="top">
    
    Information to identify the transformation flow.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Status


    
    </td>
    <td valign="top">
    
    The deployment and error status of the object. For more information, see [Saving and Deploying Objects](../Creating-Finding-Sharing-Objects/saving-and-deploying-objects-7c0b560.md).


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Load Type


    
    </td>
    <td valign="top">
    
    The following options are possible:

    -   Initial Only

        Loads the full set of data to the target table.

    -   Initial and Delta

        The first time you run the transformation flow, the system will load all the full set of data to the target table. For subsequent runs, the system will only load delta changes to the target table.

        If you want to load delta changes from a source table, you need to ensure that the value of the option *Delta Capture* is *On* for both the source table and for the target table.



    
    </td>
    </tr>
    </table>
    
    In the *Run Status* section, you can view the status of the transformation flow run.

5.  Click <span class="FPA-icons"></span> \(Save\). A dialog box appears. Enter a business name and a technical name for your transformation flow.

    When you enter a business name, the system automatically suggests a corresponding technical name, but you can change the technical name if required. Both names must be unique within the space you work in.

6.  Click <span class="SAP-icons"></span> \(Deploy\) to make your transformation flow ready to run.

    -   Newly created transformation flows are deployed for the first time.

    -   Transformation flows that have changes to deploy are redeployed.


    > ### Note:  
    > You will need to navigate to the *View Transform Editor* to check the validation messages for the transformation flow.

7.  \[optional\] To create a schedule for the transformation flow, click <span class="FPA-icons"></span> \(Schedule\). For example, it may make sense to replicate delta changes to the target table at regular intervals. For more information, see [Schedule a Data Integration Task](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/7c11059ed3314e1fb753736b7867512c.html "You can schedule or unschedule data integration tasks such as remote table replication, persisting views, or data flow execution. You may also pause and then later resume execution of scheduled tasks.") :arrow_upper_right:

8.  Click <span class="FPA-icons"></span> \(Run\) to start your transformation flow.

    You can also start your transformation flows in the *Data Integration Monitor*.

    > ### Note:  
    > You can cancel a running transformation flow in the *Data Integration Monitor*. For more information, see [Cancel a Transformation Flow Run](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/ab885f05210f4a52aebe8306c8cad083.html "") :arrow_upper_right:.

9.  To see more details about the run, open the *Flow Monitor* by clicking <span class="FPA-icons"></span> \(Open in Data Integration Monitor\).


