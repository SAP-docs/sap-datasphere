<!-- loio71f4d1599dba4aa59e6682a314650cf7 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Data Product Details

If you're interested in a data product, review its detailed information, such as properties about the data product, like its name and the data provider, the list of entities within the data product, and links to resources for how to use it.



This topic describes the details for data products from systems that are part of an SAP Business Data Cloud formation.

The catalog search results provides high-level information about a data product, including its name, data type, and a short summary. If you want to know more about a data product, select it to view its details page. You'll see different types of information about the data product, including its properties, detailed information about its APIs, and resources that can provide information or examples on how to use it.

For example, when a data modeler reviews the details of a data product, they can check out any of the resources to get information about how to use it. They can also review individual APIs and learn how to extend them.

After you view the data product details, you can choose to install it in your space \(see [Installing Data Products](installing-data-products-ea7cb80.md)\).



The data product details header provides high-level information about the data product and organizes the information as shown in the following table:


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

Name, type, status, and version

</td>
<td valign="top">

Displays the data product's name and type, its lifecycle, release, and functional statuses, and its version number.

</td>
</tr>
<tr>
<td valign="top">

Summary description

</td>
<td valign="top">

Displays a short summary of the data product.

</td>
</tr>
<tr>
<td valign="top">

Extraction system and data provider

</td>
<td valign="top">

Displays the name and type of source system the data product is extracted from and the data provider's name.

</td>
</tr>
<tr>
<td valign="top">

Catalog Activity

</td>
<td valign="top">

Displays the date when the data product was added to the catalog and when it was updated.

</td>
</tr>
</table>

In the header, you'll also be able to see a toolbar with actions available for catalog users.

-   *View Version History*: Opens a dialog that shows the change history for the data product.
-   *Open Impact and Lineage*: Opens a dialog that displays the *Impact and Lineage Analysis* diagram.
-   <span class="FPA-icons-V3"></span> \(Add to Favorites\): Adds frequently used data products to your favorites.



<a name="loio71f4d1599dba4aa59e6682a314650cf7__section_b5q_ytl_bdc"/>

## Data Product Properties and Details

To view the properties of the data product, select *Overview tab* \> *Properties*.

The properties are separated into the following areas: 

-   Data product properties are properties directly related to the data product, such as the name, category, entity types, and more.
-   Source properties are properties about the system.

For more information about properties not described here, see the help documentation for the source systems where the data product is from.

**Data Product Properties**


<table>
<tr>
<th valign="top">

Field

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Business Name

</td>
<td valign="top">

Displays the business name for the data product.

</td>
</tr>
<tr>
<td valign="top">

Lifecycle Status

</td>
<td valign="top">

Displays the lifecycle status of the data product:

-   Active: The data product is synchronized and ready.
-   Beta: The data product is in the testing phase.
-   Inactive: The data product is inactive and can be provisioned \(or installed\).
-   Provisioning: The data product is being provisioned \(or installed\) and is not ready yet.
-   Deprovisioning: The data product is being deprovisioned \(or uninstalled\) and cannot be used.
-   Active with Errors: The data product is provisioned and available but has errors that prevent proper use.
-   Provisioning Error: The provisioning of the data product failed with errors.
-   Deprovisioning Error: The deprovisioning of the data product failed with errors.



</td>
</tr>
<tr>
<td valign="top">

Release Status

</td>
<td valign="top">

Displays the release status of the data product:

-   Active: The data product is available to consumers.
-   Beta: The data product is available to consumers for testing.
-   Deprecated: The data product is available to consumers, but it's not recommended to use it.



</td>
</tr>
<tr>
<td valign="top">

Type

</td>
<td valign="top">

Displays the data product type.

</td>
</tr>
<tr>
<td valign="top">

Input Ports

</td>
<td valign="top">

Displays the input ports for the data product.

</td>
</tr>
<tr>
<td valign="top">

Category

</td>
<td valign="top">

Displays the category for the data product.

</td>
</tr>
<tr>
<td valign="top">

Entity Types

</td>
<td valign="top">

Displays the entity types for the data product.

</td>
</tr>
<tr>
<td valign="top">

ORD ID

</td>
<td valign="top">

Displays the open resource discovery \(ORD\) identifier for the API.

</td>
</tr>
<tr>
<td valign="top">

Description

</td>
<td valign="top">

Displays the long description for the data product.

</td>
</tr>
<tr>
<td valign="top">

Version

</td>
<td valign="top">

Displays the latest version number of the data product. Select *View Version History* to see all version changes for the data product.

</td>
</tr>
<tr>
<td valign="top">

Changed On

</td>
<td valign="top">

Displays the date and time when the data product was changed.

</td>
</tr>
<tr>
<td valign="top">

Extensibility

</td>
<td valign="top">

Displays whether the data product is extensible and be enhanced. The data product can be manually or automatically extensible or not extensible at all. If a data product is extensible, you can select an API to view extensibility details.

</td>
</tr>
<tr>
<td valign="top">

Additional Properties

</td>
<td valign="top">

Displays the additional properties for the data product. 

For data products from SAP Datasphere systems, additional properties can include the following:

-   Policy Level
-   Industry: Displays the industries the data product is relevant for.
-   Tags: Displays tags that have been linked to the data product. 
-   Line of Business: Displays one or more business areas where the data product can be used.
-   Data Category: Displays one or more data categories that apply to the data product.

For data products from other SAP or partner systems, additional properties can include custom properties specific to those systems or organizations.

</td>
</tr>
</table>

**Source Properties**


<table>
<tr>
<th valign="top">

Field

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

System Instance Name

</td>
<td valign="top">

Displays the name of the data provider's system. The system can be the name of an SAP system not in the same landscape or third-party system.

</td>
</tr>
<tr>
<td valign="top">

System Type

</td>
<td valign="top">

Displays the system type.

</td>
</tr>
<tr>
<td valign="top">

Deployment Region

</td>
<td valign="top">

Displays the regions where data product has been deployed.

</td>
</tr>
<tr>
<td valign="top">

Application Namespace

</td>
<td valign="top">

Displays the application namespace that identifies the system instance.

</td>
</tr>
<tr>
<td valign="top">

System ID

</td>
<td valign="top">

Displays the system identifier.

</td>
</tr>
<tr>
<td valign="top">

Data Provider

</td>
<td valign="top">

Displays data provider's name. For data products from an SAP Datasphere system, select the link to review the data provider's profile.

</td>
</tr>
</table>

You can view a list of APIs for the data product by selecting *Overview tab* \> *Details*. This table provides high-level information for each data product \(API\), which includes its name, description, version, protocol, functional status and more. If there are more than 20 rows, select *Show All* to see the rest of the rows for the tab in a separate page.


<table>
<tr>
<th valign="top">

Field

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Name

</td>
<td valign="top">

Displays the name for the data product \(API\).

</td>
</tr>
<tr>
<td valign="top">

Description

</td>
<td valign="top">

Displays a description for the use and purpose of the data product \(API\).

</td>
</tr>
<tr>
<td valign="top">

Version

</td>
<td valign="top">

Displays version number of the data product \(API\).

</td>
</tr>
<tr>
<td valign="top">

Protocol

</td>
<td valign="top">

Displays the data product \(API\) protocols.

</td>
</tr>
<tr>
<td valign="top">

Functional Status

</td>
<td valign="top">

Displays the functional status of the data product \(API\).

</td>
</tr>
<tr>
<td valign="top">

Visibility

</td>
<td valign="top">

Displays whether the data product \(API\) is public or private.

</td>
</tr>
<tr>
<td valign="top">

Supported Use Cases

</td>
<td valign="top">

Displays the data product \(API\) use cases, if provided. If you don't see this column, select <span class="FPA-icons-V3"></span> \(Select Columns\) to show it.

</td>
</tr>
<tr>
<td valign="top">

Actions

</td>
<td valign="top">

Select an action:

-   *Install*: Opens the *Import Entities* wizard. Follow the steps to import entities from the data product to your space on the local SAP Datasphere system.
-   *Uninstall*: Opens a dialog, where you select a space to uninstall the data product. You can uninstall a data product from a specific SAP Datasphere space after all its dependent objects have been removed.

The actions to install or uninstall data products appear based on the privileges that are assigned to you \(see [Installing Data Products](installing-data-products-ea7cb80.md)\). 

</td>
</tr>
</table>

You can select a data product's API to view its details page, where you can learn more about it. Information is separated into the following areas:

-   API properties that include all the same high-level information found in the data product's *Details* list plus other information, such as its open resource discovery \(ORD\) identifier.
-   Available objects and their container path and primary key. If the primary key is missing, API cannot be installed.
-   Documentation that provides a more detailed description of the API, links that can give you more information on how to use it, and extensibility information.
-   Actions available for the API appear in a toolbar at the top of the page.



<a name="loio71f4d1599dba4aa59e6682a314650cf7__section_axs_q5l_bdc"/>

## Data Product Documentation

The *Documentation* tab provides supporting documentation and resources for the data product:

-   *Description*: This tab provides a more detailed description of the data product.
-   *External Resources*: This tab provides links to resources that provides more information about the data product and how to use it. For example, images, other file types, sample data, and more.



<a name="loio71f4d1599dba4aa59e6682a314650cf7__section_cxf_5k5_y2c"/>

## Impact and Lineage Analysis Diagram for a Data Product

Select the *Open Impact and Lineage* button in the header to see a diagram for the analyzed data product. This diagram shows the data analysis of the analyzed object and provides an end-to-end visualization of the object dependencies across multiple systems and layers. It can help you better understand the lineage \(also known as data provenance\) and impacts of a selected object in the catalog. Impact and lineage contain information about the source of the object, the transformations it goes through, its final state, and objects affected by changes made to it. Impact and lineage serve distinct purposes.

-   *Lineage* is displayed to the left of the analyzed object \(or below it\). It shows objects that the analyzed object uses as sources. It allows you to trace errors back to the root cause.
-   *Impact* is displayed to the right of the analyzed object \(or above it\). It shows objects that use the analyzed object as a source. It allows you to understand the impact of changes on dependent objects.

![](images/Impact_and_Lineage_Catalog_View_4c0c62d.png)

This diagram provides the data analysis of the impact of an installed data product and contains the following features.


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

Use the toolbar and diagram tools to control the layout of the diagram. Click *Reset* to restore the default layout.

</td>
</tr>
<tr>
<td valign="top">

\(2\) Outermost Container

</td>
<td valign="top">

The outermost container represents a source system \(for example, <span class="FPA-icons-V3"></span> SAP Datasphere or <span class="SAP-icons-V5"></span> SAP Analytics Cloud system\) or a <span class="SAP-icons-V5"></span> data provider.

Systems connected to and monitored by the catalog show their business or technical name. Systems not connected to the catalog show their system type with the text "unmonitored". The number in brackets indicates the total number of objects in the container that are part of the impact or lineage of the analyzed object.

You can expand or collapse the container, using the <span class="FPA-icons-V3"></span> \(Show/Hide All Objects\) menu on the top-right corner of the container.

</td>
</tr>
<tr>
<td valign="top">

\(3\) Inner Container

</td>
<td valign="top">

The inner container represents one of the following:

-   A location in the source system \(for example, <span class="FPA-icons-V3"></span> SAP Datasphere space or <span class="FPA-icons-V3"></span> SAP Analytics Cloud folder\). It contains objects that either appear in the lineage or impact the analyzed object. If an object is located within a sublocation \(for example, a subfolder\), you'll see a series of nested inner containers.
-   A :package: data product. The data product is visible if you have access and view permission for it. For example, you are a member of the context associated with it or if you are a member of the space where it has been installed. Also, you will be able to view the details to see a brief summary of the data product or open the data product page.

You can expand or collapse a container, using the <span class="FPA-icons-V3"></span> \(Show/Hide All Objects\) menu on the top-right corner of the container. The number in brackets indicates the total number of objects in the container that are part of the impact and lineage of the analyzed object.

</td>
</tr>
<tr>
<td valign="top">

\(4\) Authorized Object

\(5\) Analyzed Object

\(6\) Unauthorized Object

</td>
<td valign="top">

Authorized and unauthorized objects appear in the lineage or impact of the analyzed object.

-   Authorized objects are published and can be discovered in the catalog. They have an icon that represents its type \(for example, <span class="FPA-icons-V3"></span> \(View\)\). Click the <span class="FPA-icons-V3"></span> \(Open Object Details\) icon to view the details page for the object.

-   The analyzed object appears as a light blue object. They have an icon that represents its type \(for example, <span class="FPA-icons-V3"></span> \(Story\) or <span class="FPA-icons-V3"></span> \(Transformation\)\).

-   Unauthorized objects are unpublished objects that you don't have access permission to in the source system. They are represented with the :lock: icon.


You can show or hide the objects on either side of any object by clicking the <span class="SAP-icons-V5"></span> \(Show Next Level\) or <span class="SAP-icons-V5"></span> \(Hide All\) on the object.

</td>
</tr>
</table>

For information on how to control the diagram layout and use tools to further analyze the objects, see [Impact and Lineage Analysis](impact-and-lineage-analysis-9da4892.md).

