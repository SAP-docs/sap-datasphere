<!-- loio10478251045b43e782fa15e0f3e113b0 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Finding and Accessing Data in the Catalog

Discover data by searching and filtering results. Mark your favorite assets, listed data products, terms, and key performance indicators \(KPIs\).

The catalog provides an effective data governance strategy by bringing together an organized inventory of business metadata and data assets to enable business and technical users to unlock the full potential of their enterprise data. The catalog is a central place to discover, classify, understand, and prepare all the data in your enterprise.

Use the catalog to find the single-source of truth for your data domain to build reusable business models. With the catalog, you can find which stories are impacted by your changes. It all begins by finding the data you need.

You can search for assets by clicking <span class="SAP-icons"></span>\(*Catalog*\) in the side navigation menu.

> ### Note:  
> You must be assigned one of the following:
> 
> -   The **Catalog User** role.
> -   A custom role with the *Read* permission for *Catalog Asset*, *Catalog Tag Hierarchy*, *Catalog Glossary Object*, and *Catalog KPI Object*.



<a name="loio10478251045b43e782fa15e0f3e113b0__section_akz_tj2_bxb"/>

## Search by Entering a String

You can find objects globally by using the search bar and entering all or part of the characters in a term, asset, listed data product, or KPI. Enter one or more characters in the *Search* field and press *Enter* \(or click *Search*\).

As you type, the field will begin proposing objects and search strings. Select an object to open it directly. Click on a string to trigger a search on it.

Filter the search results based on selected criteria to limit the number of results. There are five tabs next to the *Filter* icon that you can use to narrow your results:


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

Data Products

</td>
<td valign="top">

Shows only listed data products. Data products must be listed in Data Marketplace before they appear in the catalog. A data product is either free or purchased data from a third-party provider that you can use in this product.

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

Shows the assets, terms, and KPIs that have been marked as a favorite.

</td>
</tr>
<tr>
<td valign="top">

Recent

</td>
<td valign="top">

Shows the assets, terms, and KPIs that have been recently added to the catalog.

</td>
</tr>
</table>

You can also open a side panel when you click <span class="FPA-icons"></span> \(Show filters\) to filter by these categories and more. Click *Show More* to open a dialog with additional filter options.



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

-   <span class="SAP-icons"></span> \(Display as Grid\)
-   <span class="FPA-icons"></span> \(Display as List\)

