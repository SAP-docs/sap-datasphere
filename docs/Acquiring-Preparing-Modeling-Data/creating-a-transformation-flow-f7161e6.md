<!-- loiof7161e6c20204672ac4a6d90c81762e4 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Creating a Transformation Flow

Create a transformation flow to load data from one or more sources, apply transformations \(such as a join\), and output the result in a target table. You can load a full set of data from one or more sources to a target table. You can add local tables and views, Open SQL schema objects, and also remote tables located in BW Bridge spaces. You can also load delta changes \(including deleted records\) from one source table to a target table.



## Context

A transformation flow run is a one-time event that completes when the relevant data is loaded to the target table successfully. You can run a transformation flow multiple times, for example if you are loading delta changes to the target table.

> ### Note:  
> Views and Open SQL schema objects that reference remote tables \(either directly or indirectly\) are not supported. However, views that reference remote tables in BW Bridge spaces are supported.

> ### Note:  
> Views and Open SQL schema objects are not supported in the following cases:
> 
> -   A data access control has been applied to the view.
> 
> -   A view or Open SQL schema object consumes \(either directly or indirectly\) a view that has a data access control applied to it.

> ### Note:  
> Remote tables located in SAP BW bridge spaces must be shared with the SAP Datasphere space you are using to create your transformation flow.

Creating a transformation flow involves two important steps:

-   Creating a graphical view transform or an SQL view transform to load data from sources and to transform data.

-   Adding a target table to the transformation flow and mapping the columns from the graphical view transform or SQL view transform created in the first step to the target table.


> ### Note:  
> A transformation flow only supports the loading of data to a local table in the SAP Datasphere repository.

> ### Note:  
> A transformation flow generates internal SQL objects that must only be consumed by SAP Datasphere internal apps, and are not allowed for external data access.



## Procedure

1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(*Data Builder*\), select a space if necessary, and click *New Transformation Flow* to open the editor. The system displays the *New Transformation Flow* screen.

2.  Create a graphical view transform or an SQL view transform to load data from sources and to transform data. To create a graphical view transform, click the *Graphical View Transform* button \(see [Create a Graphical View Transform](create-a-graphical-view-transform-c65e37c.md)\). To create an SQL view transform, click the *SQL View Transform* button \(see [Create an SQL View Transform](create-an-sql-view-transform-775e0ab.md)\).

3.  Click the *Back* button to return to the *Transformation Flow Editor*. Add or create a target table that the transformation flow will write its data to \(see [Create or Add a Target Table to Your Transformation Flow](create-or-add-a-target-table-to-your-transformation-flow-0950746.md)\).

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
    
    The deployment and error status of the object. For more information, see [Saving and Deploying Objects](saving-and-deploying-objects-7c0b560.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Load Type 
    
    </td>
    <td valign="top">
    
    Select the relevant load type. 

    The following options are possible:

    -   Initial Only

        Loads the full set of data to the target table.

    -   Initial and Delta

        If you want to load delta changes from a source table, you need to ensure that the value of the option *Delta Capture* is *On* for both the source table and for the target table.

        The first time you run the transformation flow, the system will load all the full set of data to the target table. For subsequent runs, the system will only load delta changes to the target table.



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Runtime
    
    </td>
    <td valign="top">
    
    Runtime used to run the transformation flow. It can be SAP HANA \(for transformation flow\) or Apache Spark \(for transformation flow in file space\).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Run Status 
    
    </td>
    <td valign="top">
    
    View the details of the last run. 

    You can view the details of the last run. You can view the date and time of the run as well as the status, for example *Completed*. In addition, you can choose:

    -   *Schedule*: run your transformation flow at later time, or on regular basis. For more information, see [Running a Flow](Acquiring-and-Preparing-Data-in-the-Data-Builder/running-a-flow-5b591d4.md).
    -   *Simulate Run*: In the *Data Integration Monitor*, you can open the transformation flow and click *Run* \> *Run with Settings* \> *Simulate Run* to test a transformation flow and see if you get the desired outcome. Based on the result, you can decide to resolve errors or to optimize the flow to improve performances. No changes are saved in the target table. For more information, see [Explore Transformation Flows](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/7588192bf4cd4e3db43704239ba4d366.html "Use Run with Settings to explore graphical or SQL views and the entities they consume in a transformation flow.") :arrow_upper_right:


    
    </td>
    </tr>
    </table>
    
    In the *Run Status* section, you can view the status of the transformation flow run.

5.  Click <span class="FPA-icons-V3"></span> \(Save\). A dialog box appears. Enter a business name and a technical name for your transformation flow.

    When you enter a business name, the system automatically suggests a corresponding technical name, but you can change the technical name if required. Both names must be unique within the space you work in.

6.  Click <span class="SAP-icons-V5"></span> \(Deploy\) to make your transformation flow ready to run.

    -   Newly created transformation flows are deployed for the first time.

    -   Transformation flows that have changes to deploy are redeployed.


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

    See [Saving and Deploying Objects](saving-and-deploying-objects-7c0b560.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    <span class="SAP-icons-V5"></span> \(Deploy\)
    
    </td>
    <td valign="top">
    
    Deploy your changes to make them available in the run-time environment.

    See [Saving and Deploying Objects](saving-and-deploying-objects-7c0b560.md).
    
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

    See [Exporting Objects to a CSN/JSON File](Creating-Finding-Sharing-Objects/exporting-objects-to-a-csn-json-file-3916101.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    <span class="FPA-icons-V3"></span> \(Impact and Lineage Analysis\)
    
    </td>
    <td valign="top">
    
    Open the *Impact and Lineage Analysis* graph for the object. 

    See [Impact and Lineage Analysis](impact-and-lineage-analysis-9da4892.md).
    
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
    <tr>
    <td valign="top">
    
    <span class="FPA-icons-V3"></span> Show Sources
    
    </td>
    <td valign="top">
    
    Enable to see the table and views used as sources for the view transform.

    Source objects are in read-only mode in the transformation flow editor. Click a source object to see additional information about them in the *Properties* side panel. Click <span class="FPA-icons-V3"></span> \(Open in New Tab\) to open the source object in its own editor in a new tab.

    > ### Note:  
    > -   Source objects cannot be previewed in the view transform editor. Open them in a new tab to preview the data.
    > -   A SQL view transform with validation error cannot be displayed as a source object.
    > -   The input parameter panel cannot be displayed in an SQL view transform.


    
    </td>
    </tr>
    </table>
    

