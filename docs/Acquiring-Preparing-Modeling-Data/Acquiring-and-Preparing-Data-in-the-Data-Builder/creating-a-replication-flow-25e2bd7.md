<!-- loio25e2bd7a70d44ac5b05e844f9e913471 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Creating a Replication Flow

Create a replication flow to copy multiple data assets from a source to a target.



## Context

You can use replication flows to copy data from the following source objects:

-   CDS views \(in ABAP-based SAP systems\) that are enabled for extraction

-   Objects from ODP providers, such as extractors or SAP BW artifacts \(from any SAP system that is based on SAP NetWeaver and has a suitable version of the DMIS add-on, see SAP Note [3412110](https://me.sap.com/notes/3412110)\)

-   Tables that have a primary key.


CDS views and ODP artifacts that do not have a primary key can be used as the source for a replication flow if certain prerequisites are met. For more information, see [Using an Object Without Primary Key As the Source](using-an-object-without-primary-key-as-the-source-2267a9f.md).

For more information about available connection types, sources, and targets, see [Integrating Data via Connections](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/eb85e157ab654152bd68a8714036e463.html "Connections provide access to data from a wide range of remote systems, cloud as well as on-premise, SAP as well as Non-SAP, and partner tools. They allow users assigned to a space to use objects from the connected remote system as source to acquire, prepare and access data from those sources in SAP Datasphere. In addition, you can use certain connections to define targets for replication flows.") :arrow_upper_right:.

> ### Note:  
> Replication flows may not be available in SAP Datasphere tenants provisioned prior to version 2021.03. To request the migration of your tenant, see SAP note [3268282](https://launchpad.support.sap.com/#/notes/3268282).

> ### Note:  
> To make sure that you have the most up-to-date information and important considerations regarding replication flows, please read SAP Note [3297105](https://me.sap.com/notes/3297105) **before** you start creating a replication flow.



<a name="loio25e2bd7a70d44ac5b05e844f9e913471__steps_qxh_dqv_fvb"/>

## Procedure

1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(*Data Builder*\), select a space if necessary, and click *New Replication Flow* to open the editor.

2.  Select a source connection and a source container, then add source objects \(see [Add a Source](add-a-source-7496380.md)\).

    The side panel shows the properties of your replication flow. Complete the missing information as appropriate:


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
    <tr>
    <td valign="top">
    
    Delta Load Interval
    
    </td>
    <td valign="top">
    
    \[only relevant for load type `Initial and Delta`\] Define the time interval for replicating changes from the source to the target. 

    For more information, see [Configure Your Replication Flow](configure-your-replication-flow-3f5ba0c.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Status
    
    </td>
    <td valign="top">
    
    \[read-only\] Displays the overall status of the replication flow run, for example `Not Run Yet`..For more detailed information, go to the flow monitor.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Frequency
    
    </td>
    <td valign="top">
    
    \[read-only\] Displays the run frequency, if applicable, for example `Scheduled`.
    
    </td>
    </tr>
    </table>
    
3.  Select a target connection and target container \(see [Add a Target](add-a-target-ab490fb.md)\).

4.  Click <span class="FPA-icons-V3"></span> \(Browse target settings\) to review the default target settings for your replication flow and change or complete them as appropriate \(see [Configure Your Replication Flow](configure-your-replication-flow-3f5ba0c.md)\).

5.  Select a replication object in the canvas to review its properties in the side panel and change or complete them as appropriate:


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
    
    Projections
    
    </td>
    <td valign="top">
    
    Add a projection to define a filter or mappings.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Delta Capture
    
    </td>
    <td valign="top">
    
    \[only relevant for local tables\] Select this option if you want the system to keep track of changes in your data source.

    For more information, see [Capturing Delta Changes in Your Local Table](capturing-delta-changes-in-your-local-table-154bdff.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Load Type
    
    </td>
    <td valign="top">
    
    Select how you want to load the data \(initial only or initial and delta\).

    For more information, see [Configure Your Replication Flow](configure-your-replication-flow-3f5ba0c.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    ABAP Exit
    
    </td>
    <td valign="top">
    
    \[only relevant for replication of CDS views and if this feature is supported for the source\] Select a BAdI implementation to add your own projection logic for replication of CDS view data.

    For more information, see [Add Customer-Specific Projection Logic](add-customer-specific-projection-logic-970636e.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Truncate
    
    </td>
    <td valign="top">
    
    Enable this option to delete any existing content in the target.

    For more information, see [Configure Your Replication Flow](configure-your-replication-flow-3f5ba0c.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Object Thread Count for Delta Loads
    
    </td>
    <td valign="top">
    
    Enter the number of threads to be used for parallel processing during delta load.

    This option is available for SLT tables, CDS views, and CDS view entities that have load type *Initial and Delta*.

    For more information, see [Configure Your Replication Flow](configure-your-replication-flow-3f5ba0c.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Target Columns
    
    </td>
    <td valign="top">
    
    Lists the target column names. A key symbol next to a column name indicates that this column is a key column.
    
    </td>
    </tr>
    </table>
    
    > ### Note:  
    > Some further properties are only relevant for specific types of targets. You can find a list of these properties in the detailed information for the respective targets:
    > 
    > -   [Using a Cloud Storage Provider As the Target](using-a-cloud-storage-provider-as-the-target-43d93a2.md)
    > 
    > -   [Using Google BigQuery As the Target](using-google-bigquery-as-the-target-56d4472.md)
    > 
    > -   [Using Apache Kafka As the Target](using-apache-kafka-as-the-target-6df55db.md).

6.  Click <span class="FPA-icons-V3"></span> \(Save\).

7.  Click <span class="SAP-icons-V5"></span> \(Deploy\) to make your replication flow ready to run.

    When you deploy your replication flow, it gets saved in the shared repository and is available for other users to view, import, or modify.

    When deploying your replication flow, the system does a series of validation checks and outputs an error message if it finds an issue in the flow configuration.

8.  Click <span class="FPA-icons-V3"></span> \(Run\) to start your replication flow.

    For more information about how to monitor your replication flow run, see [Monitoring Flows](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/b661ea0766a24c7d839df950330a89fd.html "In the Flows monitor, you can find all the deployed flows per space.") :arrow_upper_right:.

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
    
    Add Projection
    
    </td>
    <td valign="top">
    
    Define a projection \(filter or mapping\) for an object by selecting it and choosing *Add Projection*.

    See [Define Filters](define-filters-5a6ef36.md) and [Define Mapping](define-mapping-2c7948f.md)
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    <span class="FPA-icons-V3"></span> \(Open in Data Integration Monitor\)
    
    </td>
    <td valign="top">
    
    Go to the monitor to get status information for your replication flow runs.
    
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
    

