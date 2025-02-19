<!-- loio1f15a29a25354ec28392ab10ca4e9350 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Acquiring Data in the Data Builder

Users with a modeler role can import data directly into the *Data Builder* from connections and other sources, and use flows to replicate, extract, transform and load data.

This topic contains the following sections:

-   [Federate and Replicate Data in Remote Tables](acquiring-data-in-the-data-builder-1f15a29.md#loio1f15a29a25354ec28392ab10ca4e9350__section_federate_replicate)
-   [Extract, Transform, and Load Data with Data Flows](acquiring-data-in-the-data-builder-1f15a29.md#loio1f15a29a25354ec28392ab10ca4e9350__section_etl)
-   [Load Data from Multiple Objects with Replication Flows](acquiring-data-in-the-data-builder-1f15a29.md#loio1f15a29a25354ec28392ab10ca4e9350__section_replication_flows)
-   [Load and Transform Data \(Including Delta Change Support\) with Transformation Flows](acquiring-data-in-the-data-builder-1f15a29.md#loio1f15a29a25354ec28392ab10ca4e9350__section_transformation_flows)
-   [Import Entities from SAP S/4HANA](acquiring-data-in-the-data-builder-1f15a29.md#loio1f15a29a25354ec28392ab10ca4e9350__section_s4)
-   [Import Entities from SAP BW Bridge](acquiring-data-in-the-data-builder-1f15a29.md#loio1f15a29a25354ec28392ab10ca4e9350__section_bw_bridge)
-   [Import Data from CSV Files](acquiring-data-in-the-data-builder-1f15a29.md#loio1f15a29a25354ec28392ab10ca4e9350__section_import_csv)
-   [Purchase Data from Data Marketplace](acquiring-data-in-the-data-builder-1f15a29.md#loio1f15a29a25354ec28392ab10ca4e9350__section_marketplace)
-   [Create and Import Objects to Receive and Prepare Data](acquiring-data-in-the-data-builder-1f15a29.md#loio1f15a29a25354ec28392ab10ca4e9350__section_create_tables)
-   [Create Objects and Act On Existing Objects](acquiring-data-in-the-data-builder-1f15a29.md#loio1f15a29a25354ec28392ab10ca4e9350__section_tools)

Space administrators and integrators prepare connections and other sources to allow modelers to acquire data \(see [Integrating Data and Managing Spaces in SAP Datasphere](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/8f98d3c917f94452bafe288055b60b35.html "Users with a space administrator or integrator role can create connections to source systems and databases and can schedule and monitor data replication and other data integration tasks. Space administrators are, additionally, responsible for controlling user access to their space, creating data access controls to secure data, enabling other forms of data integration, transporting content between tenants, and monitoring and otherwise managing the space.") :arrow_upper_right:\).



<a name="loio1f15a29a25354ec28392ab10ca4e9350__section_federate_replicate"/>

## Federate and Replicate Data in Remote Tables

Many connections \(including most connections to SAP systems\) support importing remote tables to federate or replicate data \(see [Integrating Data via Connections](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/eb85e157ab654152bd68a8714036e463.html "Users with a space administrator or integrator role can create connections to SAP and non-SAP source systems, including cloud and on-premise systems and partner tools, and to target systems for outbound replication flows. Users with modeler roles can import data via connections for preparation and modeling in SAP Datasphere.") :arrow_upper_right:\).

You can import remote tables to make the data available in your space from the *Data Builder* start page, in an entity-relationship model, or directly as a source in a view.

-   To get started: In the side navigation area, click <span class="FPA-icons-V3"></span> \(*Data Builder*\), select a space if necessary, and click *Import* \> *Import Remote Tables*. See [Import Remote Tables](import-remote-tables-fd04efb.md).
-   By default, remote tables federate data, and each time the data is used a call is made to the remote system to load it. You can improve performance by enabling replication to store the data in SAP Datasphere. Some connections support real-time replication and for others, you can keep your data fresh by scheduling regular updates \(see [Replicate Remote Table Data](replicate-remote-table-data-7e258a7.md)\).

-   To optimize replication performance and reduce your data footprint, you can remove unneccessary columns and set filters \(see [Restrict Remote Table Data Loads](restrict-remote-table-data-loads-bd1ece5.md)\).

-   To maximize access performance, you can store the replicated data in-memory \(see [Accelerate Table Data Access with In-Memory Storage](accelerate-table-data-access-with-in-memory-storage-407d1df.md)\).

-   Once a remote table is imported, it is available for use by all users of the space and can be used as a source for views.
-   You can automate sequences of data replication and loading tasks with task chains \(see [Creating a Task Chain](creating-a-task-chain-d1afbc2.md)\).




<a name="loio1f15a29a25354ec28392ab10ca4e9350__section_etl"/>

## Extract, Transform, and Load Data with Data Flows

Many connections \(including most connections to SAP systems\) support loading data to SAP Datasphere via data flows \(see [Integrating Data via Connections](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/eb85e157ab654152bd68a8714036e463.html "Users with a space administrator or integrator role can create connections to SAP and non-SAP source systems, including cloud and on-premise systems and partner tools, and to target systems for outbound replication flows. Users with modeler roles can import data via connections for preparation and modeling in SAP Datasphere.") :arrow_upper_right:\).

Data flows support a wide range of extract, transform, and load \(ETL\) operations.

-   To get started: In the side navigation area, click <span class="FPA-icons-V3"></span> \(*Data Builder*\), select a space if necessary, and click *New Data Flow* to open the editor. See see [Creating a Data Flow](creating-a-data-flow-e30fd14.md).
-   To add a source to your data flow, drag it from the *Source Browser* \(see [Using the Source Browser](../using-the-source-browser-7d2b21d.md)\).
-   In addition to connections, data flows can load and transform data from the following kinds of sources:
    -   Open SQL schemas \(see [Integrating Data via Database Users/Open SQL Schemas](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/3de55a78a4614deda589633baea28645.html "Users with a space administrator role can create database users to read data exposed by the space and to write data to Open SQL schemas attached to space, providing a secure method for exchanging data with the space via ODBC access to the run-time SAP HANA Cloud database.") :arrow_upper_right:\)
    -   HDI containers \(see [Exchanging Data with SAP SQL Data Warehousing HDI Containers](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/1aec7ca95af24208a61c1a444b249d95.html "Users with a space administrator role can use SAP SQL Data Warehousing to build calculation views and other SAP HANA Cloud HDI objects directly in the run-time SAP HANA Cloud database and then exchange data between HDI containers and SAP Datasphere spaces. SAP SQL Data Warehousing can be used to bring existing HDI objects into your SAP Datasphere environment, and to allow users familiar with the HDI tools to leverage advanced SAP HANA Cloud features.") :arrow_upper_right:\).
    -   Objects that are already in the SAP Datasphere repository \(see [Add Objects from the Repository](../add-objects-from-the-repository-13fcecd.md)\).

-   Data flows load data into local tables.
-   You can automate sequences of data replication and loading tasks with task chains \(see [Creating a Task Chain](creating-a-task-chain-d1afbc2.md)\).




<a name="loio1f15a29a25354ec28392ab10ca4e9350__section_replication_flows"/>

## Load Data from Multiple Objects with Replication Flows

Certain connections support loading data from multiple source objects to SAP Datasphere via a replication flow. You can enable a single initial load or request initial and delta loads and perform simple projection operations \(see [Creating a Replication Flow](creating-a-replication-flow-25e2bd7.md)\).



<a name="loio1f15a29a25354ec28392ab10ca4e9350__section_transformation_flows"/>

## Load and Transform Data \(Including Delta Change Support\) with Transformation Flows

Create a transformation flow to load data from one or more source repository tables, apply transformations, and output the result to a target table. You can load a full set of data or only delta changes from each source table \(see [Creating a Transformation Flow](../creating-a-transformation-flow-f7161e6.md)\).



<a name="loio1f15a29a25354ec28392ab10ca4e9350__section_s4"/>

## Import Entities from SAP S/4HANA

The *Import Entities* wizard allows you to import entities from  and SAP S/4HANA on-premise systems with rich metadata \(see [Importing Entities with Semantics from SAP S/4HANA](importing-entities-with-semantics-from-sap-s-4hana-845fedb.md)\).



<a name="loio1f15a29a25354ec28392ab10ca4e9350__section_bw_bridge"/>

## Import Entities from SAP BW Bridge

SAP BW bridge enables you to use SAP BW functionality in the public cloud and to import bridge entities into SAP Datasphere \(see[Importing Entities with Semantics from SAP BW∕4HANA or SAP BW Bridge](importing-entities-with-semantics-from-sap-bw-4hana-or-sap-bw-br-7bcd321.md) \).



<a name="loio1f15a29a25354ec28392ab10ca4e9350__section_import_csv"/>

## Import Data from CSV Files

You can import data from a CSV file to create a new local table \(see [Creating a Local Table from a CSV File](creating-a-local-table-from-a-csv-file-8bba251.md)\).



<a name="loio1f15a29a25354ec28392ab10ca4e9350__section_marketplace"/>

## Purchase Data from Data Marketplace

Purchase data products from providers and download them directly into your space \(see [Purchasing Data from Data Marketplace](../purchasing-data-from-data-marketplace-4096fb8.md)\).

You can become a data provider and offer your own data products for sale in Data Marketplace via the Data Sharing Cockpit \(see [Data Marketplace - Data Provider's Guide](https://help.sap.com/viewer/bb1899f0b39f415b9de29a845873d7af/DEV_CURRENT/en-US/e479b7b4c95741c7a7a1d42397984c7e.html "Users with a modeler role can create a data provider profile and publish data products to public, private, and internal Data Marketplaces.") :arrow_upper_right:\).



<a name="loio1f15a29a25354ec28392ab10ca4e9350__section_create_tables"/>

## Create and Import Objects to Receive and Prepare Data

You can create and import empty tables and views to receive and prepare data:

-   You can create an empty local table ready to receive data from a CSV file or from a data flow \(see [Creating a Local Table](creating-a-local-table-2509fe4.md)\).
-   You can import business content prepared by SAP and partners to support end-to-end business scenarios \(see [Importing SAP and Partner Business Content from the Content Network](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/400078d689bf4454b3fc977a4e201c2f.html "Users with an administrator role or space administrator role, can use the Semantic Onboarding app to import business content and sample content from SAP and partners published to the Content Network.") :arrow_upper_right:\).
-   You can import object definitions from a CSN/JSON file \(see [Importing Objects from a CSN/JSON File](../Creating-Finding-Sharing-Objects/importing-objects-from-a-csn-json-file-23599e6.md)\).



<a name="loio1f15a29a25354ec28392ab10ca4e9350__section_tools"/>

## Create Objects and Act On Existing Objects

All the objects you import or create in the *Data Builder* are listed on the *Data Builder* start page. You can act on objects in the list in the following ways:

-   Click one of the tabs to filter the list by object type.
-   Click a tile to create a new object
-   Click <span class="FPA-icons-V3"></span> \(Show filters\) to filter the list on collections and search by criteria. Click *Show More* to open a dialog with additional filter options.
-   Enter one or more characters in the *Search* field and press *Enter* \(or click *Search*\). 
    -   If you've searched for objects before, clicking in the search field shows a list of recently entered searches. As you type, the field will begin proposing objects and search strings. Select an object to open it directly. Click on a string to start a search on it. 

    -   The search is case-insensitive and automatically applies wildcards so that, for example, the string "`lend`" will find objects containing both "`lender`" and "`calendar`".

    -   If natural language search is enabled on your tenant \(and you have the appropriate role\), the search field will propose example natural language strings that are appropriate to your current filter context. Select an example string or enter your own and SAP Datasphere will interpret it and filter your results appropriately. See [Natural Language Search](../Creating-Finding-Sharing-Objects/natural-language-search-04170c6.md).


-   Click a column header to sort or filter the list by values in the column.
-   Select one or more objects and use any of the following tools:


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
    
    New
    
    </td>
    <td valign="top">
    
    Create *Data Builder* objects \(independent of any selection\).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Import
    
    </td>
    <td valign="top">
    
    Import objects from files and connections:

    -   *Import CSV File* - Import data from a CSV file to create a local table \(see [Creating a Local Table from a CSV File](creating-a-local-table-from-a-csv-file-8bba251.md).
    -   *Import Objects from CSN/JSON File* - Import table, view, and other object definitions from a CSN/JSON file \(see [Importing Objects from a CSN/JSON File](../Creating-Finding-Sharing-Objects/importing-objects-from-a-csn-json-file-23599e6.md)\).
    -   *Import Remote Tables* - Import remote tables from a connection \(see [Import Remote Tables](import-remote-tables-fd04efb.md)\).
    -   *Import Permissions* - Import analysis authorizations from SAP BW and and SAP BW∕4HANA systems to create data access controls \(see [Import SAP BW and SAP BW∕4HANA Analysis Authorizations](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/f56e4271dc4943aa9f21223ce5c93873.html "You can import analysis authorizations defined in SAP BW and SAP BW∕4HANA systems into SAP Datasphere to provide row-level protection for data imported from these systems.") :arrow_upper_right:\).


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Edit
    
    </td>
    <td valign="top">
    
    Open the selected object in the appropriate editor. Alternatively, click the object directly in the list.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Deploy
    
    </td>
    <td valign="top">
    
    Select one or more objects and deploy them together.

    Choose from the following entity types:

    -   Local tables \(see [Creating a Local Table](creating-a-local-table-2509fe4.md)\)
    -   Graphical views \(see [Creating a Graphical View](../creating-a-graphical-view-27efb47.md)\)
    -   SQL views \(see [Creating an SQL View](../creating-an-sql-view-81920e4.md)\)
    -   Data access controls \(see [Securing Data with Data Access Controls](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/a032e51c730147c7a1fcac125b4cfe14.html "Users with a space administrator role can create data access controls to allow modelers to apply row-level security to Data Builder and Business Builder objects. Once a data access control is applied to an object, any user viewing its data either directly or via an object using it as a source, will see only those records they are authorized to view, based on the specified criteria.") :arrow_upper_right:\)
    -   Analytic models \(see [Creating an Analytic Model](../Modeling-Data-in-the-Data-Builder/creating-an-analytic-model-e5fbe9e.md)\)
    -   Task chains \(see [Creating a Task Chain](creating-a-task-chain-d1afbc2.md)\)

    Other types of objects can only be deployed via their editors.

    If one or more objects that you have selected cannot be deployed, the *Deploy* dialog opens, allowing you to review your selection. Click *Deploy* to deploy those objects listed on the *Deployable* tab, or *Cancel* to go back and alter your selection.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Share
    
    </td>
    <td valign="top">
    
    Share the selected tables and views to other spaces \(see [Sharing Entities and Task Chains to Other Spaces](../Creating-Finding-Sharing-Objects/sharing-entities-and-task-chains-to-other-spaces-64b318f.md)\).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Impact and Lineage Analysis
    
    </td>
    <td valign="top">
    
    View the objects that depend on the selected object, and those objects on which it depends \(see [Impact and Lineage Analysis](../impact-and-lineage-analysis-9da4892.md)\).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Delete
    
    </td>
    <td valign="top">
    
    Delete the selected objects \(see [Deleting Objects](../deleting-objects-1e69cbb.md)\).
    
    </td>
    </tr>
    </table>
    

> ### Note:  
> In various places in editors where there is not enough room to show both business and technical names for entities and columns, you can choose which of these names to display. Click *Profile* \> *Settings* \> *UI Settings* and select either *Show Business Name* or *Show Technical Name*.

