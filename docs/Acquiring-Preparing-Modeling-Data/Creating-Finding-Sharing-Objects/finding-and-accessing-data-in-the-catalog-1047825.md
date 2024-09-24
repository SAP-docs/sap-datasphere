<!-- loio10478251045b43e782fa15e0f3e113b0 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Finding and Accessing Data in the Catalog

Discover data by searching and filtering results. Mark your favorite assets, terms, key performance indicators \(KPIs\), Marketplace data products, or data providers. For more information about these objects, see [Catalog Concepts](https://help.sap.com/viewer/97d1d2f0e35d410c893e95a5ff3bee6f/DEV_CURRENT/en-US/5772386034824e2ba7146fe7b3109d21.html "Learn about the major concepts related to the catalog and data governance.") :arrow_upper_right:.

The catalog provides an effective data governance strategy by bringing together an organized inventory of business metadata and data assets to enable business and technical users to unlock the full potential of their enterprise data. The catalog is a central place to discover, classify, understand, and prepare all the data in your enterprise.

Use the catalog to find the single-source of truth for your data domain to build reusable business models. With the catalog, you can find which stories are impacted by your changes. It all begins by finding the data you need.

You can search for assets by clicking <span class="SAP-icons-V5"></span>\(*Catalog*\) in the side navigation menu.

> ### Note:  
> You must be assigned one of the following:
> 
> -   The **Catalog User** role.
> -   A custom role with the *Read* permission for *Catalog Asset*, *Catalog Tag Hierarchy*, *Catalog Glossary Object*, and *Catalog KPI Object*.



<a name="loio10478251045b43e782fa15e0f3e113b0__section_akz_tj2_bxb"/>

## Search by Entering a String

You can find objects globally by using the search bar and entering all or part of the characters in an asset, term, KPI, listed Marketplace data product, or data provider. Enter one or more characters in the *Search* field and press *Enter* \(or click *Search*\).

As you type, the field will begin proposing objects and search strings. Select an object to open it directly. Click on a string to start a search on it.

Filter the search results based on selected criteria to limit the number of results.

There are tabs next to the *Filter* icon that you can use to narrow your results. The tabs shown are based on your permissions:


<table>
<tr>
<th valign="top">

Tab

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

Shows only listed Marketplace data products that are created and used within SAP Datasphere. Data products must be listed in Data Marketplace before they appear in the catalog. A data product can be obtained through internal means or by acquiring free or purchased data from a third-party provider, which can then be utilized within the product.

</td>
</tr>
<tr>
<td valign="top">

Data Providers

</td>
<td valign="top">

Shows a list of providers that deliver data products to companies. A data provider is a person or company that offers one or multiple data products through the Data Marketplace.

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

You can also open a side panel when you click <span class="FPA-icons-V3"></span> \(Show filters\) to filter by these categories and more. Click *Show More* to open a dialog with additional filter options.



<a name="loio10478251045b43e782fa15e0f3e113b0__section_pgp_5l2_bxb"/>

## Filter by Criteria

Filter by any of the categories listed in the *Filter By* area of the left panel.

You can select one or more values in each filter category in the *Filter By* section:

-   Each value selected in a category acts as an `OR` condition.
-   Each value selected in separate categories acts together as `AND` conditions.


<table>
<tr>
<th valign="top">

To Display

</th>
<th valign="top">

Select Filter Criteria

</th>
</tr>
<tr>
<td valign="top">

Assets that are a *Local Table*

</td>
<td valign="top">

*Type:**Local Table*

</td>
</tr>
<tr>
<td valign="top">

Assets that are a *Local Table* or *View*

</td>
<td valign="top">

*Type:**Local Table*, *View*

</td>
</tr>
<tr>
<td valign="top">

Assets that are a *Local Table* or *View* and on the system *SAP Datasphere*

</td>
<td valign="top">

*Type:**Story*, *View*

*System Type:* *SAP Datasphere*

</td>
</tr>
</table>

**Filter Options**


<table>
<tr>
<th valign="top">

Filter Type

</th>
<th valign="top">

Filter Category

</th>
<th valign="top">

Description

</th>
</tr>
</table>



<a name="loio10478251045b43e782fa15e0f3e113b0__section_fkl_st5_cxb"/>

## Define Advanced Filter Conditions

For those filter options that are not related to date or time, you can create a custom filter with specific conditions.

1.  Click *Show More* at the bottom of a filter category to open the Filter Settings dialog. Some filters have a *Select Items* and a *Define Conditions* tab.
2.  On the *Define Conditions* tab, choose an operator and enter a value in the *Filter Condition* box.
3.  Click the plus icon to create an alternative condition. Each condition in one category acts as an `OR` operator, so that an object must meet one of the conditions to be included in the search results. If you define one condition in two categories, then each category acts as an `AND` operator, so that both conditions must be true for the object to be returned in the search results.

You can create advanced filter conditions for multiple filter categories. An object must meet one of the conditions in each of the categories to be included in the search results.

For example, if you are viewing terms and want to create a condition to filter on the keywords “investment” and “stock”, you would click :heavy_plus_sign:. Then choose *Contains all of these words*. In the Filter Condition box, enter `investment`. Click :heavy_plus_sign: again. Choose *Contains all of these words*. In the Filter Condition box, enter `stock`, and then click *OK*. The new condition is listed in the Keyword group in the filter panel, and the filter results are automatically shown.



<a name="loio10478251045b43e782fa15e0f3e113b0__section_ijd_2qx_kwb"/>

## Change the View for Search Results

You can change the view to see different information.

-   <span class="SAP-icons-V5"></span> \(Display as Grid\)
-   <span class="FPA-icons-V3"></span> \(Display as List\)
-   <span class="SAP-icons-V5"></span> \(Display as Table\)



<a name="loio10478251045b43e782fa15e0f3e113b0__section_vcp_wg5_zbc"/>

## Search for Third-Party Data

You can use the Datarade Data Finder website to search and request additional third-party data products from various data providers. Access the Datarade website from the catalog by choosing the *Data Products* tab or the *Data Providers* tab, and then clicking the *Request Data from Datarade* button.

> ### Note:  
> Clicking the *Request Data from Datarade* button takes you to the Datarade website. This site is external to our product.

**Related Information**  


[Evaluating Catalog Assets](evaluating-catalog-assets-dc061a2.md "After finding the asset you want, select it to view an overview of its information, a preview of its detailed metadata, and a diagram illustrating its impact and lineage. This information encompasses metadata extracted from the source system as well as data enrichments incorporated in the catalog.")

[Evaluating Marketplace Data Products](evaluating-marketplace-data-products-92c35ef.md "You can search and browse for marketplace data products. When you find a marketplace data product, you can select it to view information about it to make sure it’s the right one for your business needs.")

