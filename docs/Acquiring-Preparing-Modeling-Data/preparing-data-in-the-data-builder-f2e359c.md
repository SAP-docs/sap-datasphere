<!-- loiof2e359c899fa4351b5f514d1d86ed9e2 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Preparing Data in the Data Builder

Users with a modeler role can use views and intelligent lookups in the *Data Builder* to combine, clean, and otherwise prepare data.

This topic contains the following sections:

-   [Combine, Filter, and Enrich Data with Views](preparing-data-in-the-data-builder-f2e359c.md#loiof2e359c899fa4351b5f514d1d86ed9e2__section_views)
-   [Transform Data \(Including Delta Change Support\) with Transformation Flows](preparing-data-in-the-data-builder-f2e359c.md#loiof2e359c899fa4351b5f514d1d86ed9e2__section_transformation_flows)
-   [Combine Data via Match Rules in an Intelligent Lookup](preparing-data-in-the-data-builder-f2e359c.md#loiof2e359c899fa4351b5f514d1d86ed9e2__section_intelligent_lookups)
-   [Browse the Catalog for Trusted Data Assets](preparing-data-in-the-data-builder-f2e359c.md#loiof2e359c899fa4351b5f514d1d86ed9e2__section_catalog)
-   [Visualize and Understand the Dependencies Between Objects](preparing-data-in-the-data-builder-f2e359c.md#loiof2e359c899fa4351b5f514d1d86ed9e2__section_er_models)
-   [Create Objects and Act On Existing Objects](preparing-data-in-the-data-builder-f2e359c.md#loiof2e359c899fa4351b5f514d1d86ed9e2__section_tools)

For information about identifying the semantic usage of your entities and modeling them for consumption, see [Modeling Data in the Data Builder](Modeling-Data-in-the-Data-Builder/modeling-data-in-the-data-builder-5c1e3d4.md).



<a name="loiof2e359c899fa4351b5f514d1d86ed9e2__section_views"/>

## Combine, Filter, and Enrich Data with Views

You can combine, filter, enrich and otherwise prepare data in views.

-   You can write SQL or SQLScript \(table function\) code in a powerful SQL editor \(see [Creating an SQL View](creating-an-sql-view-81920e4.md)\).

    -   To get started: In the side navigation area, click <span class="FPA-icons-V3"></span> \(*Data Builder*\), select a space if necessary, and click *New SQL View* to open the editor.

    -   SAP Datasphere supports:
        -   A subset of the SQL syntax supported by SAP HANA Cloud \(see [SQL Reference](sql-reference-6a37cc5.md)\).
        -   The SQLScript syntax for table user-defined functions in SAP HANA Cloud \(see[SQLScript Reference](sqlscript-reference-6c46c6a.md)\).


-   You can prepare your data in a graphical no code/low code environment \(see [Creating a Graphical View](creating-a-graphical-view-27efb47.md)\).
    -   To get started: In the side navigation area, click <span class="FPA-icons-V3"></span> \(*Data Builder*\), select a space if necessary, and click *New Graphical View* to open the editor.
    -   You can add and combine your sources by drag and drop \(see [Add a Source to a Graphical View](add-a-source-to-a-graphical-view-1eee180.md), [Create a Join in a Graphical View](create-a-join-in-a-graphical-view-947d6d8.md), and [Create a Union in a Graphical View](create-a-union-in-a-graphical-view-5c3d354.md)\).
    -   You can refine, filter, and enrich your data in the diagram \(see [Reorder, Rename, and Exclude Columns in a Graphical View](reorder-rename-and-exclude-columns-in-a-graphical-view-b846d0d.md), [Create a Calculated Column in a Graphical View](create-a-calculated-column-in-a-graphical-view-3897f48.md), [Filter Data in a Graphical View](filter-data-in-a-graphical-view-6f6fa18.md), and [Aggregate Data in a Graphical View](aggregate-data-in-a-graphical-view-7733250.md)\).

-   By default, views are virtual and must be run each time they are accessed. You can improve performance by persisting the view \(see [Persist Data in a Graphical or SQL View](persist-data-in-a-graphical-or-sql-view-9bd12cf.md)\).




<a name="loiof2e359c899fa4351b5f514d1d86ed9e2__section_transformation_flows"/>

## Transform Data \(Including Delta Change Support\) with Transformation Flows

Create a transformation flow to load data from one or more source repository tables, apply transformations, and output the result to a target table. You can load a full set of data or only delta changes from each source table \(see [Creating a Transformation Flow](creating-a-transformation-flow-f7161e6.md)\).



<a name="loiof2e359c899fa4351b5f514d1d86ed9e2__section_intelligent_lookups"/>

## Combine Data via Match Rules in an Intelligent Lookup

You can join two entities even where there is no appropriate foreign key column or where its data is incomplete or unreliable, with an intelligent lookup. You can iteratively join two entities by defining rules to match records and then reviewing and processing the results \(see [Creating an Intelligent Lookup](creating-an-intelligent-lookup-8f29f80.md)\).



<a name="loiof2e359c899fa4351b5f514d1d86ed9e2__section_catalog"/>

## Browse the Catalog for Trusted Data Assets

You can browse the catalog to discover high-quality trusted data assets to use as sources in your views and other objects \(see [Searching for Data Products and Assets in the Catalog](searching-for-data-products-and-assets-in-the-catalog-1047825.md)\).



<a name="loiof2e359c899fa4351b5f514d1d86ed9e2__section_er_models"/>

## Visualize and Understand the Dependencies Between Objects

SAP Datasphere provides various ways to visualize and understand the dependencies between your entities and other objects:

-   You can visualize the objects that your object depends on \(its lineage\) and those that depend on it \(its impacts\) by opening its impact and lineage analysis \(see [Impact and Lineage Analysis](impact-and-lineage-analysis-9da4892.md)\).
-   You can visualize a set of entities and the associations between them by adding them to an entity-relationship model \(see [Creating an Entity-Relationship Model](creating-an-entity-relationship-model-a91c042.md)\).
-   You can trace the source of a column in your graphical view and the transformations it has passed through \(see [Visualize Column and Input Parameter Lineages in a Graphical View](visualize-column-and-input-parameter-lineages-in-a-graphical-view-a2426b7.md)\).



<a name="loiof2e359c899fa4351b5f514d1d86ed9e2__section_tools"/>

## Create Objects and Act On Existing Objects

All the objects you import or create in the *Data Builder* are listed on the *Data Builder* start page. You can act on objects in the list in the following ways:

-   Click one of the tabs to filter the list by object type.
-   Click a tile to create a new object
-   Click <span class="FPA-icons-V3"></span> \(Show filters\) to filter the list on collections and search by criteria. Click *Show More* to open a dialog with additional filter options.
-   Enter one or more characters in the *Search* field and press *Enter* \(or click *Search*\). 
    -   If you've searched for objects before, clicking in the search field shows a list of recently entered searches. As you type, the field will begin proposing objects and search strings. Select an object to open it directly. Click on a string to start a search on it. 

    -   The search is case-insensitive and automatically applies wildcards so that, for example, the string "`lend`" will find objects containing both "`lender`" and "`calendar`".

    -   If natural language search is enabled on your tenant \(and you have the appropriate role\), the search field will propose example natural language strings that are appropriate to your current filter context. Select an example string or enter your own and SAP Datasphere will interpret it and filter your results appropriately. See [Natural Language Search](Creating-Finding-Sharing-Objects/natural-language-search-04170c6.md).


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

    -   *Import CSV File* - Import data from a CSV file to create a local table \(see [Creating a Local Table from a CSV File](Acquiring-and-Preparing-Data-in-the-Data-Builder/creating-a-local-table-from-a-csv-file-8bba251.md).
    -   *Import Objects from CSN/JSON File* - Import table, view, and other object definitions from a CSN/JSON file \(see [Importing Objects from a CSN/JSON File](Creating-Finding-Sharing-Objects/importing-objects-from-a-csn-json-file-23599e6.md)\).
    -   *Import Remote Tables* - Import remote tables from a connection \(see [Import Remote Tables](Acquiring-and-Preparing-Data-in-the-Data-Builder/import-remote-tables-fd04efb.md)\).
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

    -   Local tables \(see [Creating a Local Table](Acquiring-and-Preparing-Data-in-the-Data-Builder/creating-a-local-table-2509fe4.md)\)
    -   Graphical views \(see [Creating a Graphical View](creating-a-graphical-view-27efb47.md)\)
    -   SQL views \(see [Creating an SQL View](creating-an-sql-view-81920e4.md)\)
    -   Data access controls \(see [Securing Data with Data Access Controls](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/a032e51c730147c7a1fcac125b4cfe14.html "Users with a space administrator role can create data access controls to allow modelers to apply row-level security to Data Builder and Business Builder objects. Once a data access control is applied to an object, any user viewing its data either directly or via an object using it as a source, will see only those records they are authorized to view, based on the specified criteria.") :arrow_upper_right:\)
    -   Analytic models \(see [Creating an Analytic Model](Modeling-Data-in-the-Data-Builder/creating-an-analytic-model-e5fbe9e.md)\)
    -   Task chains \(see [Creating a Task Chain](Acquiring-and-Preparing-Data-in-the-Data-Builder/creating-a-task-chain-d1afbc2.md)\)

    Other types of objects can only be deployed via their editors.

    If one or more objects that you have selected cannot be deployed, the *Deploy* dialog opens, allowing you to review your selection. Click *Deploy* to deploy those objects listed on the *Deployable* tab, or *Cancel* to go back and alter your selection.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Share
    
    </td>
    <td valign="top">
    
    Share the selected tables and views to other spaces \(see [Sharing Entities and Task Chains to Other Spaces](Creating-Finding-Sharing-Objects/sharing-entities-and-task-chains-to-other-spaces-64b318f.md)\).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Impact and Lineage Analysis
    
    </td>
    <td valign="top">
    
    View the objects that depend on the selected object, and those objects on which it depends \(see [Impact and Lineage Analysis](impact-and-lineage-analysis-9da4892.md)\).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Delete
    
    </td>
    <td valign="top">
    
    Delete the selected objects \(see [Deleting Objects](deleting-objects-1e69cbb.md)\).
    
    </td>
    </tr>
    </table>
    

> ### Note:  
> In various places in editors where there is not enough room to show both business and technical names for entities and columns, you can choose which of these names to display. Click *Profile* \> *Settings* \> *UI Settings* and select either *Show Business Name* or *Show Technical Name*.

