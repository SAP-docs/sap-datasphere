<!-- loio10478251045b43e782fa15e0f3e113b0 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Finding and Accessing Data in the Catalog

Discover data by searching and filtering results. Mark your favorite assets, terms, key performance indicators \(KPIs\), marketplace data products, or data providers. For more information about these objects, see [Catalog Concepts](https://help.sap.com/viewer/97d1d2f0e35d410c893e95a5ff3bee6f/DEV_CURRENT/en-US/5772386034824e2ba7146fe7b3109d21.html "Learn about the major concepts related to the catalog and data governance.") :arrow_upper_right:.

The catalog provides an effective data governance strategy by bringing together an organized inventory of business metadata and data assets to enable business and technical users to unlock the full potential of their enterprise data. The catalog is a central place to discover, classify, understand, and prepare all the data in your enterprise.

Use the catalog to find the single-source of truth for your data domain to build reusable business models. With the catalog, you can find which stories are impacted by your changes. It all begins by finding the data you need.

To access the catalog and search for data and assets, you must be assigned one of the following:

-   The *Catalog User* role.
-   The *DW Viewer*, *DW Modeler*, or *DW Integrator* role.
-   A custom role with the *Read* permission for *Catalog Asset*, *Catalog Tag Hierarchy*, *Catalog Glossary Object*, and *Catalog KPI Object*.

You can search for data and assets by clicking <span class="SAP-icons-V5"></span>\(*Catalog*\) in the side navigation menu.



<a name="loio10478251045b43e782fa15e0f3e113b0__section_akz_tj2_bxb"/>

## Search by Entering a String

You can find objects globally by using the search bar and entering all or part of the characters in an asset, term, KPI, data product, or data provider.Enter one or more characters in the *Search* field and press *Enter* \(or click *Search*\).

As you type, the field will begin proposing objects and search strings. Select an object to open it directly. Click on a string to start a search on it.

Filter the search results based on selected criteria to limit the number of results.

Tabs next to the *Filter* icon let you narrow your results by collection. The tabs shown are based on your permissions:


<table>
<tr>
<th valign="top">

Collection

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

All

</td>
<td valign="top">

All the objects in the catalog are shown.

</td>
</tr>
<tr>
<td valign="top">

Assets

</td>
<td valign="top">

Shows only assets. An asset is any data or analytic object made available in the catalog. Assets are the objects that you provide governance around and publish to the catalog for users to discover, evaluate, and ultimately open and start using for their work.

</td>
</tr>
<tr>
<td valign="top">

Marketplace Data Products

</td>
<td valign="top">

Shows only listed marketplace data products that are created and used within SAP Datasphere. Data products must have a lifecycle status of listed before they appear in the catalog. A data product can be obtained through internal means or by acquiring free or purchased data from a third-party provider, which can then be utilized within the product.

</td>
</tr>
<tr>
<td valign="top">

Data Providers

</td>
<td valign="top">

Shows a list of providers that deliver data products to companies. A data provider is a person or company that offers one or multiple data products.

</td>
</tr>
<tr>
<td valign="top">

Terms

</td>
<td valign="top">

Shows only terms. Terms are contained in a business glossary and provide meaning to your data. The business glossary provides a central and shared repository for defining terms and describing how and where they are used in the business.

</td>
</tr>
<tr>
<td valign="top">

KPIs

</td>
<td valign="top">

Shows only key performance indicators \(KPIs\). KPIs measure progress towards a result such as a goal or objective. Use KPIs to track performance and provide an analytical basis for decision-making.

</td>
</tr>
<tr>
<td valign="top">

Favorites

</td>
<td valign="top">

Shows the assets, terms, KPIs, listed marketplace data products, and data providers that have been marked as a favorite.

</td>
</tr>
<tr>
<td valign="top">

Recent

</td>
<td valign="top">

Shows the assets, terms, KPIs, listed marketplace data products, and data providers that have been recently viewed by you.

</td>
</tr>
</table>

You can also open a side panel when you click <span class="FPA-icons-V3"></span> \(Show filters\) to filter by these collections and more. Click *Show More* to open a dialog with additional filter options.



<a name="loio10478251045b43e782fa15e0f3e113b0__section_vcp_wg5_zbc"/>

## Search for Third-Party Data

You can use the Datarade Data Finder website to search and request additional third-party data products from various data providers. Access the Datarade website from the catalog by choosing the *Data Products* tab or the *Data Providers* tab, and then clicking the *Request Data from Datarade* button.

> ### Note:  
> Clicking the *Request Data from Datarade* button takes you to the Datarade website. This site is external to our product.



<a name="loio10478251045b43e782fa15e0f3e113b0__section_pgp_5l2_bxb"/>

## Filter by Criteria

After you use the search and select a collection \(for example, assets or terms\), you can apply other filter options to narrow the results by the different criteria in each collection. You can access the filter options by clicking <span class="FPA-icons-V3"></span> \(Show filters\). Filter by any of the categories listed in the *Filter By* area of the left panel.

You can select one or more values in each filter category in the *Filter By* section:

-   Each value selected in a category acts as an `OR` condition.
-   Each value selected in separate categories acts together as `AND` conditions.


<table>
<tr>
<th valign="top">

To display

</th>
<th valign="top">

Select these filters

</th>
</tr>
<tr>
<td valign="top">

Assets that are a *Local Table*

</td>
<td valign="top">

Under the *Type* filter, select *Local Table*

</td>
</tr>
<tr>
<td valign="top">

Assets that are a *Local Table* or *View*

</td>
<td valign="top">

Under the *Type* filter, select *Local Table* and *View*

</td>
</tr>
<tr>
<td valign="top">

Assets that are a *Local Table* or *View* and in an *SAP Datasphere* system

</td>
<td valign="top">

Under the *Type* filter, select *Story* and *View*

Under the *System Type* filter, select **SAP Datasphere**

</td>
</tr>
</table>

Review the following tables for descriptions of the filter categories for the different collections.

-   [Assets](finding-and-accessing-data-in-the-catalog-1047825.md#loio10478251045b43e782fa15e0f3e113b0__filteroptions_assets)
-   [Marketplace Data Products](finding-and-accessing-data-in-the-catalog-1047825.md#loio10478251045b43e782fa15e0f3e113b0__filteroptions_marketplacedataproducts)
-   [Data Providers](finding-and-accessing-data-in-the-catalog-1047825.md#loio10478251045b43e782fa15e0f3e113b0__filteroptions_dataproviders)
-   [KPIs](finding-and-accessing-data-in-the-catalog-1047825.md#loio10478251045b43e782fa15e0f3e113b0__filteroptions_kpis)
-   [Terms](finding-and-accessing-data-in-the-catalog-1047825.md#loio10478251045b43e782fa15e0f3e113b0__filteroptions_terms)

**Collection: Assets**


<table>
<tr>
<th valign="top">

Filter Category

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Container

</td>
<td valign="top">

Choose a container where the asset is located.

</td>
</tr>
<tr>
<td valign="top">

Type

</td>
<td valign="top">

Choose one of the tabs and specify the options:

*Select Items*: Choose the asset type such as a story, local table, view, remote table, and so on.

*Define Conditions*: Create conditions and enter a value.

</td>
</tr>
<tr>
<td valign="top">

Exposed For Consumption

</td>
<td valign="top">

Choose one of the tabs and specify the options:

*Select Items*: Choose whether the asset is or is not exposed for consumption.

*Define Conditions*: Create conditions and enter a value.

</td>
</tr>
<tr>
<td valign="top">

Semantic Usage

</td>
<td valign="top">

Choose one of the tabs and specify the options:

*Select Items*: Choose how the asset is used, for example, a relational dataset, fact, dimension, and so on.

*Define Conditions*: Create conditions and enter a value.

</td>
</tr>
<tr>
<td valign="top">

Functional Status

</td>
<td valign="top">

Choose one of the tabs and specify the options:

*Select Items*: Select the asset status. You can refine the results in the following ways: enter a functional status in the search bar, sort by name or count, or view the options in a list, bar chart, or pie chart.

-   Unavailable: Asset is not used \(deleted\) on the remote source and is not referenced by other sources.
-   Current: Asset matches the version on the remote source.
-   Outdated: Asset changed on the remote source and is not updated in the catalog.
-   Remotely Deleted: Asset is deleted on the remote source, but the asset is referenced by other sources.

*Define Conditions*: Create conditions and enter a value.

</td>
</tr>
<tr>
<td valign="top">

Publication Status

</td>
<td valign="top">

Choose one of the tabs and specify the options:

*Select Items*: Choose whether the asset is published or unpublished.

*Define Conditions*: Create conditions and enter a value.

</td>
</tr>
<tr>
<td valign="top">

Published On

</td>
<td valign="top">

Select the time range when the asset was published.

</td>
</tr>
<tr>
<td valign="top">

Remote System

</td>
<td valign="top">

Choose one of the tabs and specify the options:

*Select Items*: Choose the source system associated with an asset.

*Define Conditions*: Create conditions and enter a value.

</td>
</tr>
<tr>
<td valign="top">

System Type

</td>
<td valign="top">

Choose one of the tabs and specify the options:

*Select Items*: Choose the system type. For example, SAP Analytics Cloud, SAP Datasphere, and so on.

*Define Conditions*: Create conditions and enter a value.

</td>
</tr>
<tr>
<td valign="top">

Related KPI Name

</td>
<td valign="top">

Choose one of the tabs and specify the options:

*Select Items*: Choose the KPI name associated with an asset.

*Define Conditions*: Create conditions and enter a value.

</td>
</tr>
<tr>
<td valign="top">

Related Term Name

</td>
<td valign="top">

Choose one of the tabs and specify the options:

*Select Items*: Choose the related terms associated with an asset.

*Define Conditions*: Create conditions and enter a value.

</td>
</tr>
<tr>
<td valign="top">

Tag Hierarchies

</td>
<td valign="top">

Choose one of the tabs and specify the options:

*Select Items*: Select one or more tags associated with the asset.

*Define Conditions*: Create conditions and enter a value.

</td>
</tr>
</table>

**Collection: Marketplace Data Products**


<table>
<tr>
<th valign="top">

Filter Category

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Aggregator

</td>
<td valign="top">

Choose one of the tabs and specify the options:

*Select Items*: Choose to see all products belonging to data providers managed by an aggregator.

*Define Conditions*: Create conditions and enter a value.

</td>
</tr>
<tr>
<td valign="top">

Context

</td>
<td valign="top">

Choose one of the tabs and specify the options:

*Select Items*: Choose the context where you are a member. Contexts enable data providers to participate in public, private, or internal data marketplaces. In a private data marketplace only you and others who have joined the corresponding context as members have access to the data products offered by the private data provider.

*Define Conditions*: Create conditions and enter a value.

</td>
</tr>
<tr>
<td valign="top">

Contract Type

</td>
<td valign="top">

Choose one of the tabs and specify the options:

*Select Items*: Choose a contract type.

-   *On Request*: Email the data providor for access.
-   *Free*: Data products that are free of charge are provided without any payment.
-   *License Key*: An activation key provides authorization to access one or multiple data products.

*Define Conditions*: Create conditions and enter a value.

</td>
</tr>
<tr>
<td valign="top">

Data Category

</td>
<td valign="top">

Choose one of the tabs and specify the options:

*Select Items*: Choose a category defined by the data providers to make your search easier and more efficient.

*Define Conditions*: Create conditions and enter a value.

</td>
</tr>
<tr>
<td valign="top">

Data Shipment

</td>
<td valign="top">

Choose one of the tabs and specify the options:

*Select Items*: Choose how the data product was sent to you.

-   *Direct*: The data is copied directly into the space you've selected.
-   *Open SQL*: The data is pushed from the data provider via an OpenSQL schema you created in Space Management directly into your tenant.
-   *External Delivery*: The data is delivered by sharing files outside this product.

*Define Conditions*: Create conditions and enter a value.

</td>
</tr>
<tr>
<td valign="top">

Delivery Mode

</td>
<td valign="top">

Choose one of the tabs and specify the options:

*Select Items*: Choose how frequently the data is updated.

-   *OneTime*: You receive the initial data product without further updates.
-   *Full*: You receive batch updates of the data product.
-   *Live Access*: You receive real-time updates of the data product.

*Define Conditions*: Create conditions and enter a value.

</td>
</tr>
<tr>
<td valign="top">

Delivery Pattern

</td>
<td valign="top">

Choose one of the tabs and specify the options:

*Select Items*: Choose how regularly the data product is updated.

*Define Conditions*: Create conditions and enter a value.

</td>
</tr>
<tr>
<td valign="top">

Industry

</td>
<td valign="top">

Choose one of the tabs and specify the options:

*Select Items*: Choose an industry defined by the data providers to make your search easier and more efficient.

*Define Conditions*: Create conditions and enter a value.

</td>
</tr>
<tr>
<td valign="top">

Provider

</td>
<td valign="top">

Choose one of the tabs and specify the options:

*Select Items*: Choose which data providers and their products you want to include in the search result.

*Define Conditions*: Create conditions and enter a value.

</td>
</tr>
<tr>
<td valign="top">

Regional Coverage

</td>
<td valign="top">

Choose one of the tabs and specify the options:

*Select Items*: Choose the regions or countries you want to include in the search result.

*Define Conditions*: Create conditions and enter a value.

</td>
</tr>
<tr>
<td valign="top">

SAP Application

</td>
<td valign="top">

Choose one of the tabs and specify the options:

*Select Items*: Choose an SAP application defined by the data providers to which their data product fits.

*Define Conditions*: Create conditions and enter a value.

</td>
</tr>
<tr>
<td valign="top">

Size Category

</td>
<td valign="top">

Choose one of the tabs and specify the options:

*Select Items*: Choose the size based on the number of records you want returned.

-   S: less than 1000 records
-   M: between 1000 and 100000 records
-   L: between 100000 and 1 million records
-   XL: between 1 million and 10 million records
-   XXL: between 10 million and 100 million records
-   XXXL: more than 100 million records

*Define Conditions*: Create conditions and enter a value.

</td>
</tr>
</table>

**Collection: Data Providers**


<table>
<tr>
<th valign="top">

Filter Category

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Context

</td>
<td valign="top">

Choose one of the tabs and specify the options:

*Select Items*: Choose the context where you are a member. Contexts enable data providers to participate in public, private, or internal data marketplaces. In a private data marketplace only you and others who have joined the corresponding context as members have access to the data products offered by the private data provider.

*Define Conditions*: Create conditions and enter a value.

</td>
</tr>
<tr>
<td valign="top">

Data Category

</td>
<td valign="top">

Choose one of the tabs and specify the options:

*Select Items*: Choose a category defined by the data providers to make your search easier and more efficient.

*Define Conditions*: Create conditions and enter a value.

</td>
</tr>
<tr>
<td valign="top">

Industry

</td>
<td valign="top">

Choose one of the tabs and specify the options:

*Select Items*: Choose an industry defined by the data providers to make your search easier and more efficient.

*Define Conditions*: Create conditions and enter a value.

</td>
</tr>
<tr>
<td valign="top">

Regional Coverage

</td>
<td valign="top">

Choose one of the tabs and specify the options:

*Select Items*: Choose the regions or countries you want to include in the search result.

*Define Conditions*: Create conditions and enter a value.

</td>
</tr>
<tr>
<td valign="top">

SAP Application

</td>
<td valign="top">

Choose one of the tabs and specify the options:

*Select Items*: Choose an SAP application defined by the data providers to which their data product fits.

*Define Conditions*: Create conditions and enter a value.

</td>
</tr>
</table>

**Collection: KPIs**


<table>
<tr>
<th valign="top">

Filter Category

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Category

</td>
<td valign="top">

SAP Data Products

</td>
</tr>
<tr>
<td valign="top">

Created On

</td>
<td valign="top">

Select a time period or enter a specific date that the KPI was created.

</td>
</tr>
<tr>
<td valign="top">

Changed On

</td>
<td valign="top">

Select a time period or enter a specific date that the KPI was edited.

</td>
</tr>
<tr>
<td valign="top">

Published On

</td>
<td valign="top">

Select the time range when the KPI was published.

</td>
</tr>
<tr>
<td valign="top">

Functional Status

</td>
<td valign="top">

Choose one of the tabs and specify the options:

*Select Items*: Select the KPI status. You can refine the results in one of the following ways: enter a functional status in the search bar, sort by name or count, or view the options in a list, bar chart, or pie chart.

-   Current: KPI does not have any issues.
-   Needs Repair: KPI has a warning or error to be fixed.

*Define Conditions*: Create conditions and enter a value.

</td>
</tr>
<tr>
<td valign="top">

Publication Status

</td>
<td valign="top">

Choose one of the tabs and specify the options:

*Select Items*: Choose whether the KPI is published or unpublished.

*Define Conditions*: Create conditions and enter a value.

</td>
</tr>
<tr>
<td valign="top">

ID

</td>
<td valign="top">

Choose one of the tabs and specify the options:

*Select Items*: Select one or more IDs defined in the KPI. If you have many IDs, you can refine the results in the following ways: enter a search ID, sort by ID, or view the options in a list, bar chart, or pie chart.

*Define Conditions*: Create conditions and enter a value.

</td>
</tr>
<tr>
<td valign="top">

Related KPI Name

</td>
<td valign="top">

Choose one of the tabs and specify the options:

*Select Items*: Choose the KPI name associated with an asset.

*Define Conditions*: Create conditions and enter a value.

</td>
</tr>
<tr>
<td valign="top">

Related Term Name

</td>
<td valign="top">

Choose one of the tabs and specify the options:

*Select Items*: Choose the related terms associated with a KPI.

*Define Conditions*: Create conditions and enter a value.

</td>
</tr>
<tr>
<td valign="top">

Keyword

</td>
<td valign="top">

Choose one of the tabs and specify the options:

*Select Items*: Select one or more keywords defined in the KPI. If you have many keywords, you can refine the results in the following ways: enter a search term, sort by name or count, or view the options in a list, bar chart, or pie chart.

*Define Conditions*: Create conditions and enter a value.

</td>
</tr>
</table>

**Collection: Terms**


<table>
<tr>
<th valign="top">

Filter Category

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Glossary

</td>
<td valign="top">

Choose a glossary that can be expanded to filter on the category hierarchy, and then filter on terms within a category.

</td>
</tr>
<tr>
<td valign="top">

Published On

</td>
<td valign="top">

Select the time range when the term was published.

</td>
</tr>
<tr>
<td valign="top">

Functional Status

</td>
<td valign="top">

Choose one of the tabs and specify the options:

*Select Items*: Select the term or glossary status. You can refine the results in one of the following ways: enter a functional status in the search bar, sort by name or count, or view the options in a list, bar chart, or pie chart.

-   Current: Term does not have any issues.
-   Needs Repair: Term has a warning or error to be fixed.

*Define Conditions*: Create conditions and enter a value.

</td>
</tr>
<tr>
<td valign="top">

Publication Status

</td>
<td valign="top">

Choose one of the tabs and specify the options:

*Select Items*: Choose whether the term is published or unpublished.

*Define Conditions*: Create conditions and enter a value.

</td>
</tr>
<tr>
<td valign="top">

Created On

</td>
<td valign="top">

Select a time period or enter a specific date that the term or glossary was created.

</td>
</tr>
<tr>
<td valign="top">

Changed On

</td>
<td valign="top">

Select a time period or enter a specific date that the term or glossary was modified.

</td>
</tr>
<tr>
<td valign="top">

Keyword

</td>
<td valign="top">

Choose one of the tabs and specify the options:

*Select Items*: Select one or more keywords defined in the term. If you have many keywords, you can refine the results in the following ways: enter a search term, sort by name or count, or view the options in a list, bar chart, or pie chart.

*Define Conditions*: Create conditions and enter a value.

</td>
</tr>
<tr>
<td valign="top">

ID

</td>
<td valign="top">

Choose one of the tabs and specify the options:

*Select Items*: Select one or more IDs defined in the term. If you have many IDs, you can refine the results in the following ways: enter a search ID, sort by ID, or view the options in a list, bar chart, or pie chart.

*Define Conditions*: Create conditions and enter a value.

</td>
</tr>
</table>



<a name="loio10478251045b43e782fa15e0f3e113b0__section_fkl_st5_cxb"/>

## Define Advanced Filter Conditions

For those filter options that are not related to date or time, you can create a custom filter with specific conditions.

1.  Click *Show More* at the bottom of a filter category to open the Filter Settings dialog. Some filters have a *Select Items* and a *Define Conditions* tab.
2.  On the *Define Conditions* tab, choose an operator and enter a value in the *Filter Condition* box.
3.  Click the plus icon to create an alternative condition. Each condition in one category acts as an `OR` operator, so that an object must meet one of the conditions to be included in the search results. If you define one condition in two categories, then each category acts as an `AND` operator, so that both conditions must be true for the object to be returned in the search results.

You can create advanced filter conditions for multiple filter categories. An object must meet one of the conditions in each of the categories to be included in the search results.

> ### Example:  
> For example, if you are viewing terms and want to create a condition to filter on the keywords “investment” and “stock”, you would click :heavy_plus_sign:. Then choose *Contains all of these words*. In the Filter Condition box, enter `investment`. Click :heavy_plus_sign: again. Choose *Contains all of these words*. In the Filter Condition box, enter `stock`, and then click *OK*. The new condition is listed in the Keyword group in the filter panel, and the filter results are automatically shown.



<a name="loio10478251045b43e782fa15e0f3e113b0__section_ijd_2qx_kwb"/>

## Change the View for Search Results

You can change how the catalog search results are displayed by selecting one of the views from the **View** toolbar.

-   <span class="SAP-icons-V5"></span> \(Display as Grid\): The grid view is the default view, where all objects in the catalog appear as tiles \(or cards\). Each tile provides the most minimal amount of information about each object, such as the name and description.
-   <span class="FPA-icons-V3"></span> \(Display as List\): The list view shows the most information about each object in the catalog.
-   <span class="SAP-icons-V5"></span> \(Display as Table\): The table view shows all the same information as the list view. However, some of the columns are hidden by default. You can choose which columns you want to show or hide. This display option is not available when viewing the search results for the **All** collection.

**Related Information**  


[Evaluating and Accessing Catalog Assets](evaluating-and-accessing-catalog-assets-dc061a2.md "When you find an asset that interests you, you can view information about it to make sure it's the right one for your business needs. You can then choose to view or edit the asset in more details in its source system or use it in a data project.")

[Evaluating and Installing Marketplace Data Products](evaluating-and-installing-marketplace-data-products-92c35ef.md "When you find a data product that interests you, review its details page and test the sample data sets (if available) to make sure it's the right one for your business needs. After you evaluate it and decide it's what you need, you can install it to an SAP Datasphere space.")

