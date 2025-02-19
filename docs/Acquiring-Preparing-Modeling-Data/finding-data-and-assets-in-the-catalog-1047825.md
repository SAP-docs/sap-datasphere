<!-- loio10478251045b43e782fa15e0f3e113b0 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Finding Data and Assets in the Catalog

Users with a catalog user role can discover data by searching and filtering results. They can also mark which data or assets are their favorite. To find out more about the data and assets that are in the catalog, see [Catalog Concepts](https://help.sap.com/viewer/97d1d2f0e35d410c893e95a5ff3bee6f/DEV_CURRENT/en-US/5772386034824e2ba7146fe7b3109d21.html "Learn about the major concepts related to the catalog and data governance.") :arrow_upper_right:.

Use the catalog to find the single-source of truth for your data domain to build reusable data models. With the catalog, you can find which analytic stories in SAP Analytics Cloud are impacted by your changes. It all begins by finding the data you need.

To access the catalog and search for data and assets, you must be assigned one of the following:

-   The *Catalog User* role.
-   The *DW Viewer*, *DW Modeler*, or *DW Integrator* role.
-   A custom role with the *Read* permission for *Catalog Asset*, *Catalog Tag Hierarchy*, *Catalog Glossary Object*, and *Catalog KPI Object*.

You can search for data and assets by clicking <span class="SAP-icons-V5"></span>\(*Catalog*\)  in the side navigation menu.



<a name="loio10478251045b43e782fa15e0f3e113b0__section_akz_tj2_bxb"/>

## Search by Entering a String

You can find objects globally by using the search bar and entering all or part of the characters in an asset, term, KPI, data product, or data provider. Enter one or more characters in the *Search* field and press *Enter* \(or click *Search*\).

If you've searched for objects before, clicking in the search field shows a list of recently entered searches. As you type, the field will begin proposing objects and search strings. Select an object to open it directly. Click on a string to start a search on it. 

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

SAP Business Data Cloud Data Products

</td>
<td valign="top">

Shows data products from other SAP cloud applications and partners.

</td>
</tr>
<tr>
<td valign="top">

Marketplace Data Products

</td>
<td valign="top">

Shows only marketplace data products that are created and used within SAP Datasphere. This tab appears only in the SAP Datasphere catalog.

Data products must have a lifecycle status of active \(or listed\) before they appear in the catalog. A data product can be created and shared internally or can be licensed for free or at a cost from a third-party provider.

</td>
</tr>
<tr>
<td valign="top">

Data Providers

</td>
<td valign="top">

Shows a list of providers that deliver data products to companies. This tab appears only in the SAP Datasphere catalog.

A data provider is a person or company that offers one or multiple data products.

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

Shows the data and assets that you marked as a favorite.

</td>
</tr>
<tr>
<td valign="top">

Recent

</td>
<td valign="top">

Shows the data and assets that you've recently viewed.

</td>
</tr>
</table>

You can also open a side panel when you click <span class="FPA-icons-V3"></span> \(Show filters\) to filter by these collections and more. Click *Show More* to open a dialog with additional filter options.



<a name="loio10478251045b43e782fa15e0f3e113b0__section_vcp_wg5_zbc"/>

## Search for Third-Party Data

You can use the Datarade Data Finder website to search and request additional third-party data products from various data providers. Access the Datarade website from the catalog by choosing the *Marketplace Data Products* tab or the *Data Providers* tab, and then clicking the *Request External Products* button.

> ### Note:  
> Clicking the *Request External Products* button takes you to the Datarade website. This site is external to our product.



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

For detailed information on the filter categories for the different collections, see [Filter Category Details](filter-category-details-3b5725b.md).



<a name="loio10478251045b43e782fa15e0f3e113b0__section_fkl_st5_cxb"/>

## Define Advanced Filter Conditions

For those filter options that are not related to date or time, you can create a custom filter with specific conditions.

1.  Click *Show More* at the bottom of a filter category to open the Filter Settings dialog. Some filters have a *Select Items* and a *Define Conditions* tab.
2.  On the *Define Conditions* tab, choose an operator and enter a value in the *Filter Condition* box.
3.  Click :heavy_plus_sign: to create an alternative condition. Each condition in one category acts as an `OR` operator, so that an object must meet one of the conditions to be included in the search results. If you define one condition in two categories, then each category acts as an `AND` operator, so that both conditions must be true for the object to be returned in the search results.

You can create advanced filter conditions for multiple filter categories. An object must meet one of the conditions in each of the categories to be included in the search results.

> ### Example:  
> For example, if you are viewing terms and want to create a condition to filter on the keywords “investment” and “stock”, you would click :heavy_plus_sign:. Then choose *Contains*. In the Filter Condition box, enter `investment`. Click :heavy_plus_sign: again. Choose *Contains*. In the Filter Condition box, enter `stock`, and then click *OK*. The new condition is listed in the Keyword group in the filter panel, and the filter results are automatically shown.



<a name="loio10478251045b43e782fa15e0f3e113b0__section_ijd_2qx_kwb"/>

## Change the View for Search Results

You can change how the catalog search results are displayed by selecting one of the views from the **View** toolbar.

-   <span class="SAP-icons-V5"></span> \(Display as Grid\): The grid view is the default view, where all objects in the catalog appear as tiles \(or cards\). Each tile provides the most minimal amount of information about each object, such as the name and description.
-   <span class="FPA-icons-V3"></span> \(Display as List\): The list view shows the most information about each object in the catalog.
-   <span class="SAP-icons-V5"></span> \(Display as Table\): The table view shows all the same information as the list view. However, some of the columns are hidden by default. You can choose which columns you want to show or hide. This display option is not available when viewing the search results for the **All** collection.

The information and actions available in each view differs. See [Information and Actions Available for Search Results](https://help.sap.com/viewer/97d1d2f0e35d410c893e95a5ff3bee6f/DEV_CURRENT/en-US/751357b3c1084ea28eb2a1a1806311e0.html "Information and actions available in the different search result views appear based on your assigned role.") :arrow_upper_right:.

**Related Information**  


[Evaluating and Accessing Catalog Assets](evaluating-and-accessing-catalog-assets-dc061a2.md "When you find an asset that interests you, you can view information about it to make sure it's the right one for your business needs. You can then choose to view or edit the asset in more details in its source system or use it in a data project.")

[Evaluating and Installing Marketplace Data Products](evaluating-and-installing-marketplace-data-products-92c35ef.md "When you find a data product that interests you, review its details page and test the sample data sets (if available) to make sure it's the right one for your business needs. After you evaluate it and decide it's what you need, you can install it to an SAP Datasphere space.")

[Evaluating and Installing SAP Business Data Cloud Data Products](evaluating-and-installing-sap-business-data-cloud-data-products-ea7cb80.md "When you find an SAP Business Data Cloud data product that interests you, you can view information about it to make sure it’s the right one for your business needs. You can then install it in your SAP Datasphere space.")

[System Monitoring and Data Access in the Catalog](https://help.sap.com/viewer/aca3ccb4b2f84eb8b6154e8fd2812c0e/cloud/en-US/563dc55fc3504a9db6ccc525df2c006a.html "Users with a catalog administrator role can monitor and update source systems that are connected to the catalog. They can also view and update the data and assets that are available in the catalog.") :arrow_upper_right:

