<!-- loio1f15a29a25354ec28392ab10ca4e9350 -->

# Acquiring and Preparing Data in the Data Builder

Users with the *DW Modeler* role can import data directly into the *Data Builder* from connections and other sources or use data flows to extract, transform and load data. They can then use views and intelligent lookups in the *Data Builder* to combine, clean, and otherwise prepare data.

This topic contains the following sections:

-   [Federate and Replicate Data in Remote Tables](acquiring-and-preparing-data-in-the-data-builder-1f15a29.md#loio1f15a29a25354ec28392ab10ca4e9350__section_federate_replicate)
-   [Extract, Transform, and Load Data with Data Flows](acquiring-and-preparing-data-in-the-data-builder-1f15a29.md#loio1f15a29a25354ec28392ab10ca4e9350__section_etl)
-   [Load Data from Multiple Objects with Replication Flows](acquiring-and-preparing-data-in-the-data-builder-1f15a29.md#loio1f15a29a25354ec28392ab10ca4e9350__section_replication_flows)
-   [Import Data from CSV Files](acquiring-and-preparing-data-in-the-data-builder-1f15a29.md#loio1f15a29a25354ec28392ab10ca4e9350__section_import_csv)
-   [Import Entities from SAP S/4HANA Cloud](acquiring-and-preparing-data-in-the-data-builder-1f15a29.md#loio1f15a29a25354ec28392ab10ca4e9350__section_s4)
-   [Import Entities from SAP BW Bridge](acquiring-and-preparing-data-in-the-data-builder-1f15a29.md#loio1f15a29a25354ec28392ab10ca4e9350__section_bw_bridge)
-   [Purchase Data from Data Marketplace](acquiring-and-preparing-data-in-the-data-builder-1f15a29.md#loio1f15a29a25354ec28392ab10ca4e9350__section_marketplace)
-   [Browse the Catalog for Trusted Data Assets](acquiring-and-preparing-data-in-the-data-builder-1f15a29.md#loio1f15a29a25354ec28392ab10ca4e9350__section_catalog)
-   [Create and Import Objects to Receive and Prepare Data](acquiring-and-preparing-data-in-the-data-builder-1f15a29.md#loio1f15a29a25354ec28392ab10ca4e9350__section_create_tables)
-   [Combine, Filter, and Enrich Data with Views](acquiring-and-preparing-data-in-the-data-builder-1f15a29.md#loio1f15a29a25354ec28392ab10ca4e9350__section_views)
-   [Combine Data via Match Rules in an Intelligent Lookup](acquiring-and-preparing-data-in-the-data-builder-1f15a29.md#loio1f15a29a25354ec28392ab10ca4e9350__section_intelligent_lookups)
-   [Visualize and Understand the Dependencies Between Objects](acquiring-and-preparing-data-in-the-data-builder-1f15a29.md#loio1f15a29a25354ec28392ab10ca4e9350__section_er_models)
-   [Create Objects and Act On Existing Objects](acquiring-and-preparing-data-in-the-data-builder-1f15a29.md#loio1f15a29a25354ec28392ab10ca4e9350__section_tools)

Space administrators and integrators prepare connections and other sources to allow modelers to acquire data \(see [Integrating Data and Managing Spaces in SAP Datasphere](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/internal/en-US/8f98d3c917f94452bafe288055b60b35.html "Users with the DW Space Administrator or DW Integrator role can create connections to source systems and databases and use other methods to bring data into their space and schedule and monitor replication. Space administrators can create data access controls to secure data and import and export content via the Content Network, and are responsible for maintaining the list of space members and monitoring and managing the space.") :arrow_upper_right:\).

For information about identifying the semantic usage of your entities and modeling them for consumption, see [Modeling Data in the Data Builder](../Modeling-Data-in-the-Data-Builder/modeling-data-in-the-data-builder-5c1e3d4.md).



<a name="loio1f15a29a25354ec28392ab10ca4e9350__section_federate_replicate"/>

## Federate and Replicate Data in Remote Tables

Many connections \(including most connections to SAP systems\) support importing remote tables to federate or replicate data \(see [Integrating Data via Connections](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/internal/en-US/eb85e157ab654152bd68a8714036e463.html "Connections provide access to data from a wide range of sources, cloud as well as on-premise sources, SAP as well as Non-SAP sources, and partner tools. They allow space members to use objects from the connected source to acquire, prepare and access data from those sources in SAP Datasphere. To connect to different sources, SAP Datasphere provides different connection types.") :arrow_upper_right:\).

You can import remote tables to make the data available in your space from the *Data Builder* start page, in an entity-relationship model, or directly as a source in a view.

-   To get started: In the side navigation area, click ![](../Creating-Finding-Sharing-Objects/images/Data_Builder_f73dc45.png) \(*Data Builder*\), select a space if necessary, and click *Import* \> *Import Remote Tables* to open the wizard. See [Import Remote Tables](import-remote-tables-fd04efb.md).
-   By default, remote tables federate data, and each time the data is used a call is made to the remote system to load it. You can improve performance by enabling replication to store the data in SAP Datasphere. Some connections support real-time replication and for others, you can keep your data fresh by scheduling regular updates \(see [Replicate Remote Table Data](replicate-remote-table-data-7e258a7.md)\).

-   To optimize replication performance and reduce your data footprint, you can remove unneccessary columns and set filters \(see [Restrict Remote Table Data Loads](restrict-remote-table-data-loads-bd1ece5.md)\).

-   To maximize access performance, you can store the replicated data in-memory \(see [Accelerate Table Data Access with In-Memory Storage](accelerate-table-data-access-with-in-memory-storage-407d1df.md)\).

-   Once a remote table is imported, it is available for use by all members of the space and can be used as a source for views.
-   You can automate sequences of data replication and loading tasks with task chains \(see [Creating a Task Chain](creating-a-task-chain-d1afbc2.md)\).




<a name="loio1f15a29a25354ec28392ab10ca4e9350__section_etl"/>

## Extract, Transform, and Load Data with Data Flows

Many connections \(including most connections to SAP systems\) support loading data to SAP Datasphere via data flows \(see [Integrating Data via Connections](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/internal/en-US/eb85e157ab654152bd68a8714036e463.html "Connections provide access to data from a wide range of sources, cloud as well as on-premise sources, SAP as well as Non-SAP sources, and partner tools. They allow space members to use objects from the connected source to acquire, prepare and access data from those sources in SAP Datasphere. To connect to different sources, SAP Datasphere provides different connection types.") :arrow_upper_right:\).

Data flows support a wide range of extract, transform, and load \(ETL\) operations.

-   To get started: In the side navigation area, click ![](../Creating-Finding-Sharing-Objects/images/Data_Builder_f73dc45.png) \(*Data Builder*\), select a space if necessary, and click *New Data Flow* to open the editor. See see [Creating a Data Flow](creating-a-data-flow-e30fd14.md).
-   To add a source to your data flow, drag it from the *Source Browser* \(see [Using the Source Browser](using-the-source-browser-7d2b21d.md)\).
-   In addition to connections, data flows can load and transform data from the following kinds of sources:
    -   Open SQL schemas \(see [Integrating Data via Database Users/Open SQL Schemas](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/internal/en-US/3de55a78a4614deda589633baea28645.html "Create a database user in your space to read and write directly to the SAP HANA Cloud database on which SAP Datasphere runs. Each database user has an Open SQL schema, which is attached to a space schema and provides a secure method for exchanging data with the space.") :arrow_upper_right:\)
    -   HDI containers \(see [Exchanging Data with SAP SQL Data Warehousing HDI Containers](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/internal/en-US/1aec7ca95af24208a61c1a444b249d95.html "You can enable SAP SQL Data Warehousing on your SAP Datasphere tenant to exchange data between your HDI containers and your SAP Datasphere spaces without the need for data movement.") :arrow_upper_right:\).
    -   Objects that are already in the SAP Datasphere repository \(see [Add Objects from the Repository](add-objects-from-the-repository-13fcecd.md)\).

-   Data flows load data into local tables.
-   You can automate sequences of data replication and loading tasks with task chains \(see [Creating a Task Chain](creating-a-task-chain-d1afbc2.md)\).




<a name="loio1f15a29a25354ec28392ab10ca4e9350__section_replication_flows"/>

## Load Data from Multiple Objects with Replication Flows

Certain connections support loading data from multiple source objects to SAP Datasphere via a replication flow. You can enable a single initial load or request initial and delta loads and perform simple projection operations \(see [Creating a Replication Flow](creating-a-replication-flow-25e2bd7.md)\).



<a name="loio1f15a29a25354ec28392ab10ca4e9350__section_import_csv"/>

## Import Data from CSV Files

You can import data from a CSV file to create a new local table \(see [Creating a Local Table from a CSV File](creating-a-local-table-from-a-csv-file-8bba251.md)\).



<a name="loio1f15a29a25354ec28392ab10ca4e9350__section_s4"/>

## Import Entities from SAP S/4HANA Cloud

The *Import Entities* wizard allows you to import entities from SAP S/4HANA Cloud with rich metadata and all their sources and dependencies \(see [Import Entities from SAP S/4HANA Cloud](import-entities-from-sap-s-4hana-cloud-845fedb.md)\).



<a name="loio1f15a29a25354ec28392ab10ca4e9350__section_bw_bridge"/>

## Import Entities from SAP BW Bridge

SAP BW bridge enables you to use SAP BW functionality in the public cloud and to import SAP BW bridge data models into SAP Datasphere \(see [Using SAP Datasphere, SAP BW Bridge in SAP Datasphere](https://help.sap.com/viewer/1714feae4425415f8e6fd6ab8578e1e6/internal/en-US/b2a2df3c588849a494295aff0aa698a0.html "SAP Datasphere, SAP BW bridge enables you to use SAP BW functionality in the public cloud, to convert SAP BW∕4HANA and SAP BW models into SAP BW bridge models, and to import SAP BW bridge models into SAP Datasphere.") :arrow_upper_right:\).



<a name="loio1f15a29a25354ec28392ab10ca4e9350__section_marketplace"/>

## Purchase Data from Data Marketplace

Purchase data products from providers and download them directly into your space \(see [Purchasing Data from Data Marketplace](../purchasing-data-from-data-marketplace-4096fb8.md)\).

You can become a data provider and offer your own data products for sale in Data Marketplace via the Data Sharing Cockpit \(see [Data Marketplace - Data Provider&apos;s Guide](https://help.sap.com/viewer/bb1899f0b39f415b9de29a845873d7af/internal/en-US/e479b7b4c95741c7a7a1d42397984c7e.html "Start with Data Marketplace as a data provider.") :arrow_upper_right:\).



<a name="loio1f15a29a25354ec28392ab10ca4e9350__section_catalog"/>

## Browse the Catalog for Trusted Data Assets

You can browse the catalog to discover high-quality trusted data assets to use as sources in your views and other objects \(see [Finding and Accessing Data in the Catalog](../Creating-Finding-Sharing-Objects/finding-and-accessing-data-in-the-catalog-1047825.md)\).



<a name="loio1f15a29a25354ec28392ab10ca4e9350__section_create_tables"/>

## Create and Import Objects to Receive and Prepare Data

You can create and import empty tables and views to receive and prepare data:

-   You can create an empty local table ready to receive data from a CSV file or from a data flow \(see [Creating a Local Table](creating-a-local-table-2509fe4.md)\).
-   You can import business content prepared by SAP and partners to support end-to-end business scenarios \(see [Importing SAP and Partner Business Content from the Content Network](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/internal/en-US/400078d689bf4454b3fc977a4e201c2f.html "Users with the DW Administrator or DW Space Administrator role can import business content and sample content from SAP and partners from the Content Network.") :arrow_upper_right:\).
-   You can import object definitions from a CSN/JSON file \(see [Importing Objects from a CSN/JSON File](../Creating-Finding-Sharing-Objects/importing-objects-from-a-csn-json-file-23599e6.md)\).



<a name="loio1f15a29a25354ec28392ab10ca4e9350__section_views"/>

## Combine, Filter, and Enrich Data with Views

You can combine, filter, enrich and otherwise prepare data in views.

-   You can write SQL or SQLScript \(table function\) code in a powerful SQL editor \(see [Creating an SQL View](creating-an-sql-view-81920e4.md)\).

    -   To get started: In the side navigation area, click ![](../Creating-Finding-Sharing-Objects/images/Data_Builder_f73dc45.png) \(*Data Builder*\), select a space if necessary, and click *New SQL View* to open the editor.

    -   SAP Datasphere supports:
        -   A subset of the SQL syntax supported by SAP HANA Cloud \(see [SQL Reference](sql-reference-6a37cc5.md)\).
        -   The SQLScript syntax for table user-defined functions in SAP HANA Cloud \(see[SQLScript Reference](sqlscript-reference-6c46c6a.md)\).


-   You can prepare your data in a graphical no code/low code environment \(see [Creating a Graphical View](creating-a-graphical-view-27efb47.md)\).
    -   To get started: In the side navigation area, click ![](../Creating-Finding-Sharing-Objects/images/Data_Builder_f73dc45.png) \(*Data Builder*\), select a space if necessary, and click *New Graphical View* to open the editor.
    -   You can add and combine your sources by drag and drop \(see [Add a Source](add-a-source-1eee180.md), [Create a Join](create-a-join-947d6d8.md), and [Create a Union](create-a-union-5c3d354.md)\).
    -   You can refine, filter, and enrich your data in the diagram \(see [Reorder, Rename, and Exclude Columns](reorder-rename-and-exclude-columns-b846d0d.md), [Create a Column](create-a-column-3897f48.md), [Filter Data](filter-data-6f6fa18.md), and [Aggregate Data](aggregate-data-7733250.md)\).

-   By default, views are virtual and must be run each time they are accessed. You can improve performance by persisting the view \(see [Persist View Data](persist-view-data-9bd12cf.md)\).




<a name="loio1f15a29a25354ec28392ab10ca4e9350__section_intelligent_lookups"/>

## Combine Data via Match Rules in an Intelligent Lookup

You can join two entities even where there is no appropriate foreign key column or where its data is incomplete or unreliable, with an intelligent lookup. You can iteratively join two entities by defining rules to match records and then reviewing and processing the results \(see [Creating an Intelligent Lookup](creating-an-intelligent-lookup-8f29f80.md)\).



<a name="loio1f15a29a25354ec28392ab10ca4e9350__section_er_models"/>

## Visualize and Understand the Dependencies Between Objects

SAP Datasphere provides various ways to visualize and understand the dependencies between your entities and other objects:

-   You can visualize the objects that your object depends on \(its lineage\) and those that depend on it \(its impacts\) by opening its impact and lineage analysis \(see [Impact and Lineage Analysis](../Creating-Finding-Sharing-Objects/impact-and-lineage-analysis-9da4892.md)\).
-   You can visualize a set of entities and the associations between them by adding them to an entity-relationship model \(see [Creating an Entity-Relationship Model](creating-an-entity-relationship-model-a91c042.md)\).
-   You can trace the source of a column in your graphical view and the transformations it has passed through \(see [Visualize the Lineage of Columns and Input Parameters in a Graphical View](visualize-the-lineage-of-columns-and-input-parameters-in-a-graph-a2426b7.md)\).



<a name="loio1f15a29a25354ec28392ab10ca4e9350__section_tools"/>

## Create Objects and Act On Existing Objects

All the objects you import or create in the *Data Builder* are listed on the *Data Builder* start page. You can act on objects in the list in the following ways:

-   Click one of the tabs to filter the list by object type.
-   Click a tile to create a new object.
-   Enter a string in the *Search* field to filter the list on business and technical names and users.
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

    -   *Import CSV File* - Import data from a CSV file to create a local table \(see [Creating a Local Table from a CSV File](creating-a-local-table-from-a-csv-file-8bba251.md)
    -   *Import Objects from CSN/JSON File* - Import table and view definitions from a CSN file to create tables and views or import data flow definitions from a JSON file to create data flows. \(see [Importing Objects from a CSN/JSON File](../Creating-Finding-Sharing-Objects/importing-objects-from-a-csn-json-file-23599e6.md)\).
    -   *Import Remote Tables* - Import remote tables from a connection \(see [Import Remote Tables](import-remote-tables-fd04efb.md)\).


    
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

    Select one or more entities and deploy them at once.

    Choose from the following entity types:

    -   Local Table \(see [Creating a Local Table](creating-a-local-table-2509fe4.md)\)
    -   Graphical View \(see [Creating a Graphical View](creating-a-graphical-view-27efb47.md)\)
    -   SQL View \(see [Creating an SQL View](creating-an-sql-view-81920e4.md)\)
    -   Data Access Control \(see [Create a Data Access Control](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/internal/en-US/5246328ec59045cb9c2aa693daee2557.html "Space administrators can create data access controls to define criteria on which data can be displayed to users.") :arrow_upper_right:\)
    -   Analytic Model
    -   Task Chain \(see [Creating a Task Chain](creating-a-task-chain-d1afbc2.md)\)

    Other types of entities cannot be deployed.


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    Share


    
    </td>
    <td valign="top">

    Share the selected tables and views to other spaces \(see [Sharing Tables and Views To Other Spaces](../Creating-Finding-Sharing-Objects/sharing-tables-and-views-to-other-spaces-64b318f.md)\).


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    Impact and Lineage Analysis


    
    </td>
    <td valign="top">

    View the objects that depend on an analyzed object \(its impacts\) and the objects on which the analyzed object depends \(its lineage\)\(see [Impact and Lineage Analysis](../Creating-Finding-Sharing-Objects/impact-and-lineage-analysis-9da4892.md)\).


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    Delete


    
    </td>
    <td valign="top">

    Delete the selected objects.

    > ### Note:  
    > If the object is used by one or more other objects then a dialog listing these dependencies opens, and the deletion is canceled.


    
    </td>
    </tr>
    </table>
    

> ### Note:  
> In various places in editors where there is not enough room to show both business and technical names for entities and columns, you can choose which of these names to display. Click *Profile* \> *Settings* \> *UI Settings* and select either *Show Business Name* or *Show Technical Name*.

