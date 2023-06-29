<!-- loiodc061a23484241b1b791f5540b1f38e3 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Evaluating Catalog Assets

As a catalog user in SAP Datasphere, you can select an asset to review its details and the impact and lineage analysis diagram to determine whether the asset is the one you need.

From the <span class="SAP-icons"></span>\(*Catalog*\) home page, you can select the *Assets* filter to find the asset you want.

When you open an individual asset from the catalog home page, you're taken to the details page for that asset. This page presents many different types of information about the asset itself, including the metadata extracted from the underlying source system and additional information added by catalog administrators, such as added description, glossary term, tag, and key performance indicator \(KPI\) relationships applied to the asset, and much more. You can use the information provided to evaluate and make an assessment on whether the data object or story is the right one you need for your business task at hand.

For example, as a data modeler, you can review the details of a catalog asset to determine whether it is the one you need to add to your model. You can also view the lineage diagram for an asset to see other assets that are consumed in the model and which assets are impacted by a change.

 <a name="concept_rfk_4ly_3wb"/>

<!-- concept\_rfk\_4ly\_3wb -->

## Viewing the Catalog Asset Header

The asset header provides high-level information of the asset.

 ![](images/DataAssetHeader_e5ead6c.png) 


<table>
<tr>
<th valign="top">

Section



</th>
<th valign="top">

Description



</th>
</tr>
<tr>
<td valign="top">

Asset Name



</td>
<td valign="top">

Displays the asset name and type with an identifying icon. This name might not match the name of the underlying source object if the catalog administrator edited it.



</td>
</tr>
<tr>
<td valign="top">

Asset Functional Status and Source System



</td>
<td valign="top">

Displays the functional status of the asset with the source system name and type. For information on the functional statuses, see [Publishing to the Catalog](https://help.sap.com/viewer/aca3ccb4b2f84eb8b6154e8fd2812c0e/cloud/en-US/f31d2d97afb0482a874acb0ec61465fe.html "As a catalog administrator, you determine what content is discoverable and visible to users who are searching in the catalog. Once you&apos;ve enriched asset metadata, applied appropriate classifications, and ensured the overall quality of the asset, you can then publish the asset and associated terms and KPIs for everyone to discover them.") :arrow_upper_right:.



</td>
</tr>
<tr>
<td valign="top">

Tabs



</td>
<td valign="top">

Select a tab to view more information about the asset, such as asset properties and descriptions and the **Impact and Lineage Analysis** diagram.



</td>
</tr>
<tr>
<td valign="top">

Actions



</td>
<td valign="top">

Select the action you want to perform on the asset.

-   *Open*: Opens the asset in the source system where you can view or edit it. This button appears if you have permission to access the asset in the source system.

-   :star:: Adds frequently used assets to your favorites.



</td>
</tr>
</table>

 <a name="concept_qhf_4my_3wb"/>

<!-- concept\_qhf\_4my\_3wb -->

## Viewing the Catalog Asset Overview



Use the *Overview* tab to view general information about the asset and relationship links to the asset. The *Overview* tab is divided into the following sections:

-   Overview

-   Relationships


**Asset Overview**

Displays the properties and description of the asset. This information is extracted from a data source or the catalog.

![](images/CatalogCardPropertyDesc_1acb3e1.png)

**Overview**


<table>
<tr>
<th valign="top">

Section Name



</th>
<th valign="top">

Description



</th>
</tr>
<tr>
<td valign="top">

Properties



</td>
<td valign="top">

Displays asset properties extracted from the data source and description information added by a catalog administrator. 

Source properties common among all assets include:

-   *Name*: The file name of the asset on the source system. Assets in SAP Analytics Cloud have one name that appears, *Name*.

    Assets in SAP Datasphere have two names that appear: **Technical Name**, which is the name that is used in scripts and code and is synchronized with the business name, and *Business Name*, which is the descriptive name of the asset that helps you identify the asset.

-   *Created On*: The date and time on which the asset was created on the source system. The name of the user who created the asset is also shown.

-   *Changed On*: The date and time on which the asset was changed on the source system. The name of the user who changed the asset is also shown.


Source properties that show information about the source system include:

-   *Container Name*: Name of the location of the asset. For assets in SAP Datasphere, this is the space name. For assets in SAP Analytics Cloud, this is the parent folder name.

-   *Container Business Name*: Business name of the location of the asset. For assets in SAP Datasphere, this is a descriptive name for the space.

-   *Path*: Folder location of the asset. This path appears for assets in the SAP Analytics Cloud.

-   *Type*: Type of location where the asset is saved. The location type appears for assets in the SAP Datasphere.


Source properties common among SAP Datasphere assets include:

-   *Semantic Usage*: The way the entity should be used. For example, Fact, Dimension, Hierarchy, or Text.

-   *Exposed for Consumption*: An indicator that shows whether the asset is made available for consumption in SAP Analytics Cloud and other BI clients.

    For more information on these properties, see [Creating a Graphical View](../creating-a-graphical-view-27efb47.md).


If the catalog administrator enriched the asset, the date of the change shows as a catalog property:

-   *Enriched On*: The date and time on which the date asset was modified by a catalog administrator. The name of the user who enriched the asset is also shown.




</td>
</tr>
<tr>
<td valign="top">

Descriptions



</td>
<td valign="top">

Displays the asset description, which has two parts.

-   *Source Description*: This description is extracted from the source system and can't be edited.

-   *Description*: This catalog description is edited by the catalog administrator.




</td>
</tr>
</table>

**Asset Relationships**

Displays the relationships for the asset. These relationships can include glossary terms, tags, and KPIs that are linked to the asset.

> ### Tip:  
> If you're a catalog administrator who wants to manage relationships to assets, see [Enriching, Classifying, and Publishing](https://help.sap.com/viewer/aca3ccb4b2f84eb8b6154e8fd2812c0e/cloud/en-US/1218c12e72c34cfd96293e566badb60c.html "As a catalog administrator, learn how to set up governance for your assets using hierarchical tags and business glossaries, create KPIs to measure progress towards company goals, and publish assets, glossary terms, and KPIs to the catalog.") :arrow_upper_right:.

![](images/Asset_Detail_Term_Tag_ac5b3b4.png)


<table>
<tr>
<th valign="top">

Section Name



</th>
<th valign="top">

Description



</th>
</tr>
<tr>
<td valign="top">

Glossary Terms



</td>
<td valign="top">

 Displays a list of business glossary terms that are linked to the asset. You can use the free text search to see if a particular term is linked to the asset. 



</td>
</tr>
<tr>
<td valign="top">

Tags



</td>
<td valign="top">

 Displays a hierarchical list of all tags that are linked to the asset. Tags help classify the types of assets that are in the catalog. You can use the free text search to see if a particular tag is linked to the asset. 



</td>
</tr>
<tr>
<td valign="top">

KPIs



</td>
<td valign="top">

 Displays a list of all key performance indicators \(KPIs\) that are linked to the asset. KPIs are used to track business requirements or goals. You can use the free text search to see if a particular KPI is linked to the asset. 



</td>
</tr>
</table>

 <a name="concept_ewq_zmy_3wb"/>

<!-- concept\_ewq\_zmy\_3wb -->

## Analyzing Data Impact and Lineage

Use the *Lineage* tab to view the **Impact and Lineage Analysis** diagram. This diagram shows the data analysis of the asset and provides an end-to-end visualization of the asset dependencies across multiple systems and layers. It can help you better understand the lineage \(also known as data provenance\) and impacts of a selected asset in the catalog. Impact and lineage contain information about the source of the asset, the transformations it goes through, its final state, and objects affected by changes made to it. Impact and lineage serve distinct purposes.

-   *Lineage* is displayed to the left of the object \(or below it\). It shows objects that the analyzed asset uses as sources. It allows you to trace errors back to the root cause.
-   *Impact* is displayed to the right of the object \(or above it\). It shows objects that use the analyzed asset as a source. It allows you to understand the impact of changes on dependent objects.

In this example, a user views the diagram to analyze the **Sales Story** asset. The **Sales Story** asset is in the **Public** folder in SAP Analytics Cloud and has two sources that are objects in a SAP Datasphere space.

![](images/Impact_and_Lineage_Catalog_View_4c0c62d.png)

The diagram provides the data analysis of the asset and contains the following features.


<table>
<tr>
<th valign="top">

Feature



</th>
<th valign="top">

Description



</th>
</tr>
<tr>
<td valign="top">

\(1\) Toolbar and Diagram Tools



</td>
<td valign="top">

Use the toolbar and diagram tools to control the layout of the diagram. Click <span class="SAP-icons"></span> \(Refresh\) to update the diagram with the latest changes.



</td>
</tr>
<tr>
<td valign="top">

\(2\) Source System



</td>
<td valign="top">

The source system is the outermost object and has an icon that represents the type of system \(for example, SAP Datasphere or SAP Analytics Cloud tenant\). The number in brackets indicates the total number of objects in the source system that are part of the impact or lineage of the analyzed object.

You can expand or collapse a source system, using the <span class="FPA-icons"></span> \(Show/Hide All Objects\) menu on the top-right corner of the symbol.



</td>
</tr>
<tr>
<td valign="top">

\(3\) Container



</td>
<td valign="top">

The container is directly inside the source system and has an icon that represents its type \(for example, SAP Datasphere space or SAP Analytics Cloud public folder\). It contains assets that appear in the lineage or impacts of the analyzed objects. The number in brackets indicates the total number of objects in the container that are part of the impact or lineage of the analyzed object.

You can expand or collapse a container, using the <span class="FPA-icons"></span> \(Show/Hide All Objects\) menu on the top-right corner of the symbol.



</td>
</tr>
<tr>
<td valign="top">

\(4a\) Authorized Object

\(4b\) Unauthorized Object

\(4c\) Analyzed Object



</td>
<td valign="top">

Authorized and unauthorized objects appear in the lineage or impact of the analyzed object.

Authorized objects are published and can be discovered in the catalog. You can view the asset details by clicking <span class="SAP-icons"></span> \(Open Asset Details\). Unauthorized objects are unpublished and are not available in the catalog. They are shown with the :lock:.

You can show or hide the objects on either side of any object by clicking the <span class="SAP-icons"></span> \(Show Next Level\) or <span class="SAP-icons"></span> \(Hide All\) on the object.



</td>
</tr>
</table>

For information on how to control the diagram layout and use tools to further analyze the objects, see [Impact and Lineage Analysis](impact-and-lineage-analysis-9da4892.md).

 <a name="task_x4m_cny_3wb"/>

<!-- task\_x4m\_cny\_3wb -->

## Viewing or Editing an Asset



<a name="task_x4m_cny_3wb__context_d3z_1dw_hwb"/>

## Context

After you find the asset you want, you can open the asset in the source system to view or edit it. When the source file for an asset has been shared with you, the *Open* button appears in the top-right corner. For information on how to share source files, see:

-   In SAP Datasphere, see [Sharing Tables and Views To Other Spaces](sharing-tables-and-views-to-other-spaces-64b318f.md).

-   In SAP Analytics Cloud, see [Share Files and Folders](https://help.sap.com/docs/SAP_ANALYTICS_CLOUD/00f68c2e08b941f081002fd3691d86a7/35b0bdae69254b04b075e09702d8cb56.html).

> ### Tip:  
> If the source file for the asset has not been shared with you, contact the person who created the asset or the person who most recently changed it. You can find this information in the asset properties.



<a name="task_x4m_cny_3wb__steps_egp_cdw_hwb"/>

## Procedure

1.  In the side navigation area, click <span class="SAP-icons"></span>\(*Catalog*\).

2.  On the *Catalog* home page, use the filters or the search to find the asset you want. For more information, see [Finding and Accessing Data in the Catalog](finding-and-accessing-data-in-the-catalog-1047825.md).

3.  When viewing the asset details, in the top-right corner, click the *Open* button to open the source file in the source system in a new browser tab.

    The *Open* button appears only if the asset has been shared with you in the source system and you have permission to view or edit it.

    ![](images/Asset_Details_-_Open_Button_24913a7.png)

4.  Depending on how the source file is shared with you, you can view the asset in full and explore it, or you can edit it as needed.




<a name="task_x4m_cny_3wb__result_ipq_22w_hwb"/>

## Results

If you edited a file, the catalog automatically detects the change. The metadata for the asset is automatically updated in real time, and the functional status label *Current* is applied.

 <a name="task_zpg_fny_3wb"/>

<!-- task\_zpg\_fny\_3wb -->

## Using the Asset in a Data Project



<a name="task_zpg_fny_3wb__context_lkt_ghw_hwb"/>

## Context

After you evaluate and determine that the asset is the right one for your needs, you can use it as part of a data project to build something new. For example:

-   As a data modeler in SAP Datasphere, you can use the asset as a source for a Data Builder or Business Builder object. For more information, see [Acquiring Data in the Data Builder](../Acquiring-and-Preparing-Data-in-the-Data-Builder/acquiring-data-in-the-data-builder-1f15a29.md) or [Modeling Data in the Data Builder](../Modeling-Data-in-the-Data-Builder/modeling-data-in-the-data-builder-5c1e3d4.md).

-   As a content creator in SAP Analytics Cloud, you can use the asset in data object \(for example, a story or digital boardroom\). For more information, see [Welcome to the SAP Analytics Cloud Help](https://help.sap.com/docs/SAP_ANALYTICS_CLOUD/00f68c2e08b941f081002fd3691d86a7/1fb1f4ce92f44fc983debc25ac1f2cc9.html).


> ### Tip:  
> Before you search for an asset in the catalog, determine which application you want to use the asset in and open it in a new browser tab. By keeping the catalog open in a separate tab, you can find the asset you want and have its property information readily available as you switch between tabs.
> 
> -   To use SAP Datasphere, in the side navigation area, right-click the application you want to use and click *Open App in New Tab*.
> 
> -   To use SAP Analytics Cloud, in the side navigation area, right-click any application and click *Open App in New Tab*. In the shell bar click <span class="SAP-icons"></span> \(*Product Switch*\) and click *Analytics*.



<a name="task_zpg_fny_3wb__steps_dhc_k3w_hwb"/>

## Procedure

1.  In the side navigation area, click <span class="SAP-icons"></span>\(*Catalog*\).

2.  On the *Catalog* home page, use the filters or the search to find the asset you want. For more information, see [Finding and Accessing Data in the Catalog](finding-and-accessing-data-in-the-catalog-1047825.md).

3.  Go to the tab where SAP Datasphere or SAP Analytics Cloud is open and find and open an existing file or data object or create a new one and add the asset. If you haven't opened the application in a new tab, do that now.

4.  Save the file or data object.

    -   In SAP Datasphere, save and then deploy the source file. Only files that have been saved and deployed can be added to the catalog. For more information, see [Saving and Deploying Objects](saving-and-deploying-objects-7c0b560.md).

    -   In SAP Analytics Cloud, save the source file in the *Public* folder. Only files that have been saved in the *Public* folder can be added to the catalog.





<a name="task_zpg_fny_3wb__result_xcb_gmw_hwb"/>

## Results

The catalog automatically detects the change in real time:

-   If you created a new file, a new unpublished catalog asset is created and the functional status is set to *Current*. This asset won't be available in the catalog until the catalog administrator enriches the metadata and publishes it.

-   If you edited an existing file, the metadata for the asset is automatically updated.


