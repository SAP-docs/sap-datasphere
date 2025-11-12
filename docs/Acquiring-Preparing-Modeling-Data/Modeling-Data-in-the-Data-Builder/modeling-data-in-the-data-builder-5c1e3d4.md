<!-- loio5c1e3d4a49554fcd8fcf199d664d1109 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Modeling Data in the Data Builder

Users with a modeler role can add semantic information to their entities and combine, refine, and enrich them in tightly-focused analytic models for consumption in SAP Analytics Cloud, Microsoft Excel, and other clients, apps, and tools.

This topic contains the following sections:

-   [Model Facts, Dimensions, Texts, and Hierarchies](modeling-data-in-the-data-builder-5c1e3d4.md#loio5c1e3d4a49554fcd8fcf199d664d1109__section_star_schema)
-   [Identify Measures to Analyze in a Fact](modeling-data-in-the-data-builder-5c1e3d4.md#loio5c1e3d4a49554fcd8fcf199d664d1109__section_facts)
-   [Prepare Master Data for Grouping in a Dimension](modeling-data-in-the-data-builder-5c1e3d4.md#loio5c1e3d4a49554fcd8fcf199d664d1109__section_dimensions)
-   [Support Translations of Attributes with a Text Entity](modeling-data-in-the-data-builder-5c1e3d4.md#loio5c1e3d4a49554fcd8fcf199d664d1109__section_texts)
-   [Enable Drill-Down with a Hierarchy](modeling-data-in-the-data-builder-5c1e3d4.md#loio5c1e3d4a49554fcd8fcf199d664d1109__section_hierarchies)
-   [Create Heterogeneous Hierarchies with a Hierarchy with Directory](modeling-data-in-the-data-builder-5c1e3d4.md#loio5c1e3d4a49554fcd8fcf199d664d1109__section_hierarchy_with_directory)
-   [Combine Entities for Consumption in an Analytic Model](modeling-data-in-the-data-builder-5c1e3d4.md#loio5c1e3d4a49554fcd8fcf199d664d1109__section_analytic_model)
-   [Expose Data Outside SAP Datasphere](modeling-data-in-the-data-builder-5c1e3d4.md#loio5c1e3d4a49554fcd8fcf199d664d1109__section_expose)
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

Facts are entities that contain numerical measures that can be analyzed and are the principal type of object that is consumed by BI clients \(see [Create a Fact to Contain Measurable Data](create-a-fact-to-contain-measurable-data-30089bd.md)\).

-   To get started: Select a *Semantic Usage* of *Fact* to indicate that your entity contains numerical measures that can be analyzed.
-   You must identify at least one measure \(see [Specify Measures to Analyze](specify-measures-to-analyze-33f7f29.md)\).
-   You can create associations to dimensions and text entities \(see [Create an Association to Define a Semantic Relationship Between Entities](create-an-association-to-define-a-semantic-relationship-between-entities-66c6998.md)\).
-   To expose your data for consumption in SAP Analytics Cloud, add it to an analytic model \(see [Creating an Analytic Model](creating-an-analytic-model-e5fbe9e.md)\).



<a name="loio5c1e3d4a49554fcd8fcf199d664d1109__section_dimensions"/>

## Prepare Master Data for Grouping in a Dimension

Dimensions are entities that contain master data that categorize and group the numerical data contained in your measures \(see [Create a Dimension to Categorize Data](create-a-dimension-to-categorize-data-5aae0e9.md)\).

-   To get started: Select a *Semantic Usage* of *Dimension* to indicate that your entity contains attributes that can be used to analyze and categorize measures defined in other entities.

-   You must set at least one key column \(see [Set Key Columns to Uniquely Identify Records](set-key-columns-to-uniquely-identify-records-d9ef2c9.md)\).
-   You can create associations to other dimensions, text entities, and hierarchies \(see [Create an Association to Define a Semantic Relationship Between Entities](create-an-association-to-define-a-semantic-relationship-between-entities-66c6998.md)\).
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

External hierarchies are entities that contain data to define parent-child relationships for a dimension \(see [Create an External Hierarchy for Drill-Down](create-an-external-hierarchy-for-drill-down-dbac7a8.md)\).

-   To get started: Select a *Semantic Usage* of *Hierarchy* to indicate that your entity contains parent-child relationships for members in a dimension.
-   You must specify the parent and child attributes and set the child attribute as a key.

> ### Note:  
> Parent-child and level-based hierarchies can also be defined directly in a dimension. See [Add a Hierarchy to a Dimension](add-a-hierarchy-to-a-dimension-218b7e6.md).



<a name="loio5c1e3d4a49554fcd8fcf199d664d1109__section_hierarchy_with_directory"/>

## Create Heterogeneous Hierarchies with a Hierarchy with Directory

A hierarchy with directory is an entity that contains one or more parent-child hierarchies and has an association to a directory dimension containing a list of the hierarchies. These types of hierarchy entities can include nodes from multiple dimensions \(for example, country, cost center group, and cost center\) and are commonly imported from SAP S/4HANA Cloud and SAP BW systems \(see [Create a Hierarchy with Directory](create-a-hierarchy-with-directory-36c39ee.md)\).



<a name="loio5c1e3d4a49554fcd8fcf199d664d1109__section_analytic_model"/>

## Combine Entities for Consumption in an Analytic Model

Once your fact is ready for use, create an analytic model from it to consume its data in SAP Analytics Cloud \(see [Creating an Analytic Model](creating-an-analytic-model-e5fbe9e.md)\).

-   To get started: In the side navigation area, click <span class="FPA-icons-V3"></span> \(*Data Builder*\), select a space if necessary, and click *New Analytic Model* to open the editor.
-   You must add a fact as a source and can choose to copy all its measures, attributes and associated dimensions to the analytic model \(see [Add a Fact to an Analytic Model](add-a-fact-to-an-analytic-model-27075ee.md)\).
-   You can deselect measures and attributes to leave only those that are relevant to answer your particular analytic question.
-   You can create additional calculated and restricted measures \(see [Create a Measure in an Analytic Model](create-a-measure-in-an-analytic-model-e4cc3e8.md)\).
-   You can create multiple tightly-focused analytic models from a single fact, each providing only the data needed for a particular BI context, and enriched with appropriate variables, filters, and additional measures as necessary.



<a name="loio5c1e3d4a49554fcd8fcf199d664d1109__section_expose"/>

## Expose Data Outside SAP Datasphere

Data can be exposed as analytic models, perspectives, and views, which are accessible to clients, tools, and apps as follows:


<table>
<tr>
<th valign="top">

Object

</th>
<th valign="top">

SAP Analytics Cloud

</th>
<th valign="top">

Microsoft Excel

</th>
<th valign="top">

Other Clients, Tools, and Apps

</th>
</tr>
<tr>
<td valign="top">

Analytic models \(see [Creating an Analytic Model](creating-an-analytic-model-e5fbe9e.md)\)

Exposed: Automatically

</td>
<td valign="top">

Live Connection

</td>
<td valign="top">

Live Connection \(via an SAP Add-In\)

</td>
<td valign="top">

OData

</td>
</tr>
<tr>
<td valign="top">

Perspectives \(see [Define Perspectives](../Buisiness-Builder/define-perspectives-ce26fd3.md)\)

Exposed: Automatically

</td>
<td valign="top">

Live Connection

</td>
<td valign="top">

Live Connection \(via an SAP Add-In\)

</td>
<td valign="top">

\-

</td>
</tr>
<tr>
<td valign="top">

Views\* \(see [Exposing Data For Consumption](exposing-data-for-consumption-40ec77e.md)\)

Exposed: When the *Expose for Consumption* switch is enabled

</td>
<td valign="top">

OData\*\*

</td>
<td valign="top">

\-

</td>
<td valign="top">

OData

ODBC/JDBC

</td>
</tr>
<tr>
<td valign="top">

For more information, see:

</td>
<td valign="top">

-   [Consume Data in SAP Analytics Cloud via a Live Connection](https://help.sap.com/viewer/43509d67b8b84e66a30851e832f66911/cloud/en-US/a2c5486c03174620be9de3c8c769ce54.html "You can create a live connection from SAP Analytics Cloud to SAP Datasphere and consume data exposed as analytic models and perspectives to create stories and analytic applications.") :arrow_upper_right:
-   [Integrate with SAP Analytics Cloud for Planning](https://help.sap.com/viewer/43509d67b8b84e66a30851e832f66911/cloud/en-US/f589cdea41674badaecfa1bf02571b6f.html "SAP Datasphere integrates with SAP Analytics Cloud to act as a data source for loading actuals or external data into a planning model, and can also persist your planning data and combine it with live actuals or other data as appropriate.") :arrow_upper_right:



</td>
<td valign="top">

-   [Consume Data in Microsoft Excel via an SAP Add-In](https://help.sap.com/viewer/43509d67b8b84e66a30851e832f66911/cloud/en-US/ef6e226fc32e48a5b3655fdb1102c0d5.html "You can create a live connection from SAP Analytics Cloud to SAP Datasphere and consume data exposed as analytic models and perspectives in Microsoft Excel, via the SAP Analytics Cloud, add-in for Microsoft Excel.") :arrow_upper_right:



</td>
<td valign="top">

-   [Consume Data in Power BI and Other Clients, Tools, and Apps via an OData Service](https://help.sap.com/viewer/43509d67b8b84e66a30851e832f66911/cloud/en-US/add771abf6f54c9d8de4c7e470a0e6f0.html "You can consume data exposed as views in Microsoft Power BI and other third-party clients, tools, and apps via the OData API. You can connect Power BI to SAP Datasphere via an OData service by way of a custom connector or a blank query and consume views that are exposed for consumption.") :arrow_upper_right:
-   [Consume Data in Power BI and Other Clients, Tools, and Apps via ODBC/JDBC](https://help.sap.com/viewer/43509d67b8b84e66a30851e832f66911/cloud/en-US/4db6f5a329af44509ae422ad707877b2.html "You can consume data exposed as views in Microsoft Power BI and other third-party clients, tools, and apps via an Open SQL schema and ODBC/JDBC.") :arrow_upper_right:



</td>
</tr>
</table>

\* The workflow of consuming views with a semantic usage of *Analytical Dataset* in SAP Analytics Cloud and Microsoft Excel via live connection is now deprecated. We recommend that you migrate your analytical datasets to the new *Fact* semantic usage and expose your view data via analytic models \(see [Analytical Datasets \(Deprecated\)](analytical-datasets-deprecated-70dab71.md)\).

\*\* SAP Analytics Cloud primarily uses the consumption of view data via OData for planning \(see [Integrate with SAP Analytics Cloud for Planning](https://help.sap.com/viewer/43509d67b8b84e66a30851e832f66911/cloud/en-US/f589cdea41674badaecfa1bf02571b6f.html "SAP Datasphere integrates with SAP Analytics Cloud to act as a data source for loading actuals or external data into a planning model, and can also persist your planning data and combine it with live actuals or other data as appropriate.") :arrow_upper_right:\).

> ### Note:  
> Before exposing data for consumption, you should consider applying row-level security via data access controls \(see [Securing Data with Data Access Controls](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/a032e51c730147c7a1fcac125b4cfe14.html "Users with a space administrator role can create data access controls to allow modelers to apply row-level security to Data Builder and Business Builder objects. Once a data access control is applied to an object, any user viewing its data either directly or via an object using it as a source, will see only those records they are authorized to view, based on the specified criteria.") :arrow_upper_right:\).



<a name="loio5c1e3d4a49554fcd8fcf199d664d1109__section_tools"/>

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

    -   *Import CSV File* - Import data from a CSV file to create a local table \(see [Creating a Local Table from a CSV File](../Acquiring-and-Preparing-Data-in-the-Data-Builder/creating-a-local-table-from-a-csv-file-8bba251.md).
    -   *Import Objects from CSN/JSON File* - Import table, view, and other object definitions from a CSN/JSON file \(see [Importing Objects from a CSN/JSON File](../Creating-Finding-Sharing-Objects/importing-objects-from-a-csn-json-file-23599e6.md)\).
    -   *Import Remote Tables* - Import remote tables from a connection \(see [Import Remote Tables](../Acquiring-and-Preparing-Data-in-the-Data-Builder/import-remote-tables-fd04efb.md)\).
    -   *Import Permissions* - Import analysis authorizations from SAP BW and and SAP BW∕4HANA systems to create data access controls \(see [Import SAP BW and SAP BW∕4HANA Analysis Authorizations](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/f56e4271dc4943aa9f21223ce5c93873.html "You can import analysis authorizations defined in SAP BW and SAP BW∕4HANA systems into SAP Datasphere to provide row-level protection for data imported from these systems.") :arrow_upper_right:\).


    
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
    -   Data access controls \(see [Securing Data with Data Access Controls](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/a032e51c730147c7a1fcac125b4cfe14.html "Users with a space administrator role can create data access controls to allow modelers to apply row-level security to Data Builder and Business Builder objects. Once a data access control is applied to an object, any user viewing its data either directly or via an object using it as a source, will see only those records they are authorized to view, based on the specified criteria.") :arrow_upper_right:\)
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

