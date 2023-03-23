<!-- loio5c1e3d4a49554fcd8fcf199d664d1109 -->

# Modeling Data in the Data Builder

Users with the *DW Modeler* role can add semantic information to their entities and expose them directly or combine, refine, and enrich them in tightly-focused analytic models for consumption in SAP Analytics Cloud and other BI clients.

This topic contains the following sections:

-   [Identify Measures to Analyze in an Analytical Dataset](modeling-data-in-the-data-builder-5c1e3d4.md#loio5c1e3d4a49554fcd8fcf199d664d1109__section_facts)
-   [Prepare Master Data for Grouping in a Dimension](modeling-data-in-the-data-builder-5c1e3d4.md#loio5c1e3d4a49554fcd8fcf199d664d1109__section_dimensions)
-   [Support Translations of Attributes with a Text Entity](modeling-data-in-the-data-builder-5c1e3d4.md#loio5c1e3d4a49554fcd8fcf199d664d1109__section_texts)
-   [Enable Drill-Down with a Hierarchy](modeling-data-in-the-data-builder-5c1e3d4.md#loio5c1e3d4a49554fcd8fcf199d664d1109__section_hierarchies)
-   [Expose Views for Consumption Outside SAP Datasphere](modeling-data-in-the-data-builder-5c1e3d4.md#loio5c1e3d4a49554fcd8fcf199d664d1109__section_expose)
-   [Combine Entities for Consumption in an Analytic Model](modeling-data-in-the-data-builder-5c1e3d4.md#loio5c1e3d4a49554fcd8fcf199d664d1109__section_analytic_model)
-   [Create Objects and Act On Existing Objects](modeling-data-in-the-data-builder-5c1e3d4.md#loio5c1e3d4a49554fcd8fcf199d664d1109__section_tools)



<a name="loio5c1e3d4a49554fcd8fcf199d664d1109__section_facts"/>

## Identify Measures to Analyze in an Analytical Dataset

Analytical datasets are entities that contain numerical measures that can be analyzed and are the principal type of entity that is consumed by BI clients \(see [Creating an Analytical Dataset](creating-an-analytical-dataset-30089bd.md)\).

-   To get started: Select a *Semantic Usage* of *Analytical Dataset* to indicate that your entity contains numerical measures that can be analyzed.
-   You must identify at least one measure \(see [Specify Measures](specify-measures-33f7f29.md)\).
-   You can create associations to dimensions and text entities \(see [Create an Association](../Acquiring-and-Preparing-Data-in-the-Data-Builder/create-an-association-66c6998.md)\).
-   You can expose your analytical dataset for consumption directly, or consume it in an analytic model \(see [Creating an Analytic Model](creating-an-analytic-model-e5fbe9e.md)\).



<a name="loio5c1e3d4a49554fcd8fcf199d664d1109__section_dimensions"/>

## Prepare Master Data for Grouping in a Dimension

Dimensions are entities that contain master data that categorize and group the numerical data contained in your measures \(see [Creating a Dimension](creating-a-dimension-5aae0e9.md)\).

-   To get started: Select a *Semantic Usage* of *Dimension* to indicate that your entity contains attributes that can be used to analyze and categorize measures defined in other entities.

-   You must set at least one key column \(see [Set Key Columns to Uniquely Identify Records](set-key-columns-to-uniquely-identify-records-d9ef2c9.md)\).
-   You can create associations to other dimensions, text entities, and hierarchies \(see [Create an Association](../Acquiring-and-Preparing-Data-in-the-Data-Builder/create-an-association-66c6998.md)\).
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



<a name="loio5c1e3d4a49554fcd8fcf199d664d1109__section_expose"/>

## Expose Views for Consumption Outside SAP Datasphere

Views cannot be seen outside SAP Datasphere unless they are exposed for consumption:

-   To allow your view to be consumed by BI clients, including via the public ODATA API, enable the *Expose for Consumption* switch \(see [Exposing a View For Consumption](exposing-a-view-for-consumption-40ec77e.md)\).

-   To be consumable as a model in SAP Analytics Cloud, your entity must be a view with:

    -   *Semantic Usage* set to *Analytical Dataset* \(see [Creating an Analytical Dataset](creating-an-analytical-dataset-30089bd.md)\).
    -   *Expose for Consumption* enabled.
    -   At least one measure identified \(see [Specify Measures](specify-measures-33f7f29.md)\).




<a name="loio5c1e3d4a49554fcd8fcf199d664d1109__section_analytic_model"/>

## Combine Entities for Consumption in an Analytic Model

Rather than expose an analytical dataset for consumption directly, you can select a subset of its measures and combine them with appropriate dimension attributes for grouping and drill-down in an analytic model \(see [Creating an Analytic Model](creating-an-analytic-model-e5fbe9e.md)\).

-   To get started: In the side navigation area, click ![](../Creating-Finding-Sharing-Objects/images/Data_Builder_f73dc45.png) \(*Data Builder*\), select a space if necessary, and click *New Analytic Model* to open the editor.
-   You must add an analytical dataset as a source and can choose to copy all its measures, attributes and associated dimensions to the analytic model \(see [Add a Source](add-a-source-27075ee.md)\).
-   You can deselect measures and attributes to leave only those that are relevant to answer your particular analytic question.
-   You can create additional calculated and restricted measures \(see [Add Measures](add-measures-e4cc3e8.md)\).
-   You can create multiple tightly-focused analytic models from a single analytical dataset, each providing only the data needed for a particular BI artifact, and enriched with appropriate variables, filters, and additional measures as necessary.



<a name="loio5c1e3d4a49554fcd8fcf199d664d1109__section_tools"/>

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

    -   *Import CSV File* - Import data from a CSV file to create a local table \(see [Creating a Local Table from a CSV File](../Acquiring-and-Preparing-Data-in-the-Data-Builder/creating-a-local-table-from-a-csv-file-8bba251.md)
    -   *Import Objects from CSN/JSON File* - Import table and view definitions from a CSN file to create tables and views or import data flow definitions from a JSON file to create data flows. \(see [Importing Objects from a CSN/JSON File](../Creating-Finding-Sharing-Objects/importing-objects-from-a-csn-json-file-23599e6.md)\).
    -   *Import Remote Tables* - Import remote tables from a connection \(see [Import Remote Tables](../Acquiring-and-Preparing-Data-in-the-Data-Builder/import-remote-tables-fd04efb.md)\).


    
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

    -   Local Table \(see [Creating a Local Table](../Acquiring-and-Preparing-Data-in-the-Data-Builder/creating-a-local-table-2509fe4.md)\)
    -   Graphical View \(see [Creating a Graphical View](../Acquiring-and-Preparing-Data-in-the-Data-Builder/creating-a-graphical-view-27efb47.md)\)
    -   SQL View \(see [Creating an SQL View](../Acquiring-and-Preparing-Data-in-the-Data-Builder/creating-an-sql-view-81920e4.md)\)
    -   Data Access Control \(see [Create a Data Access Control](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/internal/en-US/5246328ec59045cb9c2aa693daee2557.html "Space administrators can create data access controls to define criteria on which data can be displayed to users.") :arrow_upper_right:\)
    -   Analytic Model
    -   Task Chain \(see [Creating a Task Chain](../Acquiring-and-Preparing-Data-in-the-Data-Builder/creating-a-task-chain-d1afbc2.md)\)

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

