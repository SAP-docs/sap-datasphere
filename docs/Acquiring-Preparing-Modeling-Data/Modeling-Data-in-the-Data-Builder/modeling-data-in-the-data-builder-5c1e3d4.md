<!-- loio5c1e3d4a49554fcd8fcf199d664d1109 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Modeling Data in the Data Builder

Users with the *DW Modeler* role can add semantic information to their entities and expose them directly to clients, tools, and apps, or combine, refine, and enrich them in tightly-focused analytic models for consumption in SAP Analytics Cloud, MS Excel, and other clients, apps, and tools.

This topic contains the following sections:

-   [Model Facts, Dimensions, Texts, and Hierarchies](modeling-data-in-the-data-builder-5c1e3d4.md#loio5c1e3d4a49554fcd8fcf199d664d1109__section_star_schema)
-   [Identify Measures to Analyze in a Fact](modeling-data-in-the-data-builder-5c1e3d4.md#loio5c1e3d4a49554fcd8fcf199d664d1109__section_facts)
-   [Prepare Master Data for Grouping in a Dimension](modeling-data-in-the-data-builder-5c1e3d4.md#loio5c1e3d4a49554fcd8fcf199d664d1109__section_dimensions)
-   [Support Translations of Attributes with a Text Entity](modeling-data-in-the-data-builder-5c1e3d4.md#loio5c1e3d4a49554fcd8fcf199d664d1109__section_texts)
-   [Enable Drill-Down with a Hierarchy](modeling-data-in-the-data-builder-5c1e3d4.md#loio5c1e3d4a49554fcd8fcf199d664d1109__section_hierarchies)
-   [Create Heterogeneous Hierarchies with a Hierarchy with Directory](modeling-data-in-the-data-builder-5c1e3d4.md#loio5c1e3d4a49554fcd8fcf199d664d1109__section_hierarchy_with_directory)
-   [Expose View Data for Consumption Outside SAP Datasphere](modeling-data-in-the-data-builder-5c1e3d4.md#loio5c1e3d4a49554fcd8fcf199d664d1109__section_expose)
-   [Combine Entities for Consumption in an Analytic Model](modeling-data-in-the-data-builder-5c1e3d4.md#loio5c1e3d4a49554fcd8fcf199d664d1109__section_analytic_model)
-   [Create Objects and Act On Existing Objects](modeling-data-in-the-data-builder-5c1e3d4.md#loio5c1e3d4a49554fcd8fcf199d664d1109__section_tools)



<a name="loio5c1e3d4a49554fcd8fcf199d664d1109__section_star_schema"/>

## Model Facts, Dimensions, Texts, and Hierarchies

![](images/Star_Schema_9239037.png)

Use the *Semantic Usage* property to indicate the type of data contained in your entity:

-   Select a *Semantic Usage* of *Fact* to indicate that your entity contains numerical measures that can be analyzed.

    In our example, `Acme Sales View` is a fact containing sales data.

-   Select a *Semantic Usage* of *Dimension* to indicate that your entity contains attributes that can be used to analyze and categorize measures defined in other entities.

    In our example, four dimensions surround the fact, allowing us to analyze it by `Salespeople`, `Time`, `Product`, and `Geo` attributes.

-   Select a *Semantic Usage* of *Text* to indicate that your entity contains strings with language identifiers to translate text attributes in other entities.

    In our example, there are four translation entities to translate time and product dimension attributes.

-   Select a *Semantic Usage* of *Hierarchy* to indicate that your entity contains parent-child relationships for members in a dimension.

    In our example, the `Acme Salespeople Hierarchy` provides a hierarchy for the `Salespeople` dimension.




<a name="loio5c1e3d4a49554fcd8fcf199d664d1109__section_facts"/>

## Identify Measures to Analyze in a Fact

Facts are entities that contain numerical measures that can be analyzed and are the principal type of object that is consumed by BI clients \(see [Creating a Fact](creating-a-fact-30089bd.md)\).

-   To get started: Select a *Semantic Usage* of *Fact* to indicate that your entity contains numerical measures that can be analyzed.
-   You must identify at least one measure \(see [Specify Measures](specify-measures-33f7f29.md)\).
-   You can create associations to dimensions and text entities \(see [Create an Association](../create-an-association-66c6998.md)\).
-   To expose your data for consumption in SAP Analytics Cloud, add it to an analytic model \(see [Creating an Analytic Model](creating-an-analytic-model-e5fbe9e.md)\).



<a name="loio5c1e3d4a49554fcd8fcf199d664d1109__section_dimensions"/>

## Prepare Master Data for Grouping in a Dimension

Dimensions are entities that contain master data that categorize and group the numerical data contained in your measures \(see [Creating a Dimension](creating-a-dimension-5aae0e9.md)\).

-   To get started: Select a *Semantic Usage* of *Dimension* to indicate that your entity contains attributes that can be used to analyze and categorize measures defined in other entities.

-   You must set at least one key column \(see [Set Key Columns to Uniquely Identify Records](set-key-columns-to-uniquely-identify-records-d9ef2c9.md)\).
-   You can create associations to other dimensions, text entities, and hierarchies \(see [Create an Association](../create-an-association-66c6998.md)\).
-   You can add parent-child or level-based hierarchies to support drill-down \(see [Add a Hierarchy to a Dimension](add-a-hierarchy-to-a-dimension-218b7e6.md)\).
-   You can make your dimension time-dependent, so that its members can change over time \(see [Enable Time-Dependency for a Dimension or Text Entity](enable-time-dependency-for-a-dimension-or-text-entity-11b2ff4.md)\).



<a name="loio5c1e3d4a49554fcd8fcf199d664d1109__section_texts"/>

## Support Translations of Attributes with a Text Entity

Text entities are entities that contain data to store strings in multiple languages for translating attributes in other entities \(see [Create a Text Entity for Attribute Translation](create-a-text-entity-for-attribute-translation-b25726d.md)\).

-   To get started: Select a *Semantic Usage* of *Text* to indicate that your entity contains strings with language identifiers to translate text attributes in other entities.

-   You must specify attributes and keys to uniquely identify a master data member and a language.
-   You can make your text entity time-dependent, so that the texts it contains can change over time \(see [Enable Time-Dependency for a Dimension or Text Entity](enable-time-dependency-for-a-dimension-or-text-entity-11b2ff4.md)\).



<a name="loio5c1e3d4a49554fcd8fcf199d664d1109__section_hierarchies"/>

## Enable Drill-Down with a Hierarchy

External hierarchies are entities that contain data to define parent-child relationships for a dimension \(see [Creating an External Hierarchy](creating-an-external-hierarchy-dbac7a8.md)\).

-   To get started: Select a *Semantic Usage* of *Hierarchy* to indicate that your entity contains parent-child relationships for members in a dimension.
-   You must specify the parent and child attributes and set the child attribute as a key.

> ### Note:  
> Parent-child and level-based hierarchies can also be defined directly in a dimension. See [Add a Hierarchy to a Dimension](add-a-hierarchy-to-a-dimension-218b7e6.md).



<a name="loio5c1e3d4a49554fcd8fcf199d664d1109__section_hierarchy_with_directory"/>

## Create Heterogeneous Hierarchies with a Hierarchy with Directory

A hierarchy with directory is an entity that contains one or more parent-child hierarchies and has an association to a directory dimension containing a list of the hierarchies. These types of hierarchy entities can include nodes from multiple dimensions \(for example, country, cost center group, and cost center\) and are commonly imported from SAP S/4HANA Cloud and SAP BW systems \(see [Creating a Hierarchy with Directory](creating-a-hierarchy-with-directory-36c39ee.md)\).



<a name="loio5c1e3d4a49554fcd8fcf199d664d1109__section_expose"/>

## Expose View Data for Consumption Outside SAP Datasphere

There are two methods for exposing view data for consumption outside SAP Datasphere:

-   SAP Analytics Cloud \(and Microsoft Excel via an SAP add-in\) do not consume view data directly. Set the *Semantic Usage* of your view to *Fact* and then add it to an analytic model to expose it \(see [Creating an Analytic Model](creating-an-analytic-model-e5fbe9e.md)\). There is no need to enable the *Expose for Consumption* switch.
-   Other third-party BI clients, tools, and apps can consume data from views with any *Semantic Usage* via OData or ODBC if the *Expose for Consumption* switch is enabled.

For more information, see [Consuming Data Exposed by SAP Datasphere](https://help.sap.com/viewer/43509d67b8b84e66a30851e832f66911/cloud/en-US/d7d56284bb5148c887ac4054689bfbca.html "All users of with any of the standard roles can consume data exposed by spaces they are assigned to. If a user does not need to access SAP Datasphere itself, and only wants to consume data exposed by it, they should be granted the DW Consumer role.") :arrow_upper_right:.



<a name="loio5c1e3d4a49554fcd8fcf199d664d1109__section_analytic_model"/>

## Combine Entities for Consumption in an Analytic Model

Once your fact is ready for use, create an analytic model from it to consume its data in SAP Analytics Cloud \(see [Creating an Analytic Model](creating-an-analytic-model-e5fbe9e.md)\).

-   To get started: In the side navigation area, click <span class="FPA-icons-V3"></span> \(*Data Builder*\), select a space if necessary, and click *New Analytic Model* to open the editor.
-   You must add a fact as a source and can choose to copy all its measures, attributes and associated dimensions to the analytic model \(see [Add a Source](add-a-source-27075ee.md)\).
-   You can deselect measures and attributes to leave only those that are relevant to answer your particular analytic question.
-   You can create additional calculated and restricted measures \(see [Add Measures](add-measures-e4cc3e8.md)\).
-   You can create multiple tightly-focused analytic models from a single fact, each providing only the data needed for a particular BI context, and enriched with appropriate variables, filters, and additional measures as necessary.



<a name="loio5c1e3d4a49554fcd8fcf199d664d1109__section_tools"/>

## Create Objects and Act On Existing Objects

All the objects you import or create in the *Data Builder* are listed on the *Data Builder* start page. You can act on objects in the list in the following ways:

-   Click one of the tabs to filter the list by object type.
-   Click a tile to create a new object
-   Click <span class="FPA-icons-V3"></span> \(Show filters\) to filter the list on collections and search by criteria. Click *Show More* to open a dialog with additional filter options.
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

    -   *Import CSV File* - Import data from a CSV file to create a local table \(see [Creating a Local Table from a CSV File](../Acquiring-and-Preparing-Data-in-the-Data-Builder/creating-a-local-table-from-a-csv-file-8bba251.md).
    -   *Import Objects from CSN/JSON File* - Import table, view, and other object definitions from a CSN/JSON file \(see [Importing Objects from a CSN/JSON File](../Creating-Finding-Sharing-Objects/importing-objects-from-a-csn-json-file-23599e6.md)\).
    -   *Import Remote Tables* - Import remote tables from a connection \(see [Import Remote Tables](../Acquiring-and-Preparing-Data-in-the-Data-Builder/import-remote-tables-fd04efb.md)\).
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

    -   Local tables \(see [Creating a Local Table](../Acquiring-and-Preparing-Data-in-the-Data-Builder/creating-a-local-table-2509fe4.md)\)
    -   Graphical views \(see [Creating a Graphical View](../creating-a-graphical-view-27efb47.md)\)
    -   SQL views \(see [Creating an SQL View](../creating-an-sql-view-81920e4.md)\)
    -   Data access controls \(see [Securing Data with Data Access Controls](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/a032e51c730147c7a1fcac125b4cfe14.html "Data access controls allow you to apply row-level security to your objects. When a data access control is applied to a data layer view or a business layer object, any user viewing its data will see only the rows for which they are authorized, based on the specified criteria.") :arrow_upper_right:\)
    -   Analytic models \(see [Creating an Analytic Model](creating-an-analytic-model-e5fbe9e.md)\)
    -   Task chains \(see [Creating a Task Chain](../Acquiring-and-Preparing-Data-in-the-Data-Builder/creating-a-task-chain-d1afbc2.md)\)

    Other types of objects can only be deployed via their editors.

    If one or more objects that you have selected cannot be deployed, the *Deploy* dialog opens, allowing you to review your selection. Click *Deploy* to deploy those objects listed on the *Deployable* tab, or *Cancel* to go back and alter your selection.
    
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

