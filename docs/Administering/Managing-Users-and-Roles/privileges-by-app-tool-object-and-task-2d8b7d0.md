<!-- loio2d8b7d04dcae402f911d119437ce0a74 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Privileges by App, Tool, Object, and Task

Review the privileges needed to work with apps, tools, and features of SAP Datasphere.

This topic contains the following sections:

-   [Repository Explorer Privileges](privileges-by-app-tool-object-and-task-2d8b7d0.md#loio2d8b7d04dcae402f911d119437ce0a74__section_repository_explorer)
-   [Catalog & Marketplace Privileges](privileges-by-app-tool-object-and-task-2d8b7d0.md#loio2d8b7d04dcae402f911d119437ce0a74__section_catalog_marketplace)
-   [Semantic Onboarding Privileges](privileges-by-app-tool-object-and-task-2d8b7d0.md#loio2d8b7d04dcae402f911d119437ce0a74__section_semantic_onboarding)
-   [Business Builder Privileges](privileges-by-app-tool-object-and-task-2d8b7d0.md#loio2d8b7d04dcae402f911d119437ce0a74__section_business_builder)
-   [Data Builder Privileges](privileges-by-app-tool-object-and-task-2d8b7d0.md#loio2d8b7d04dcae402f911d119437ce0a74__section_data_builder)
-   [Data Integration Monitor Privileges](privileges-by-app-tool-object-and-task-2d8b7d0.md#loio2d8b7d04dcae402f911d119437ce0a74__section_data_integration_monitor)
-   [Connections Privileges](privileges-by-app-tool-object-and-task-2d8b7d0.md#loio2d8b7d04dcae402f911d119437ce0a74__section_connections)
-   [Space Management Tool Privileges](privileges-by-app-tool-object-and-task-2d8b7d0.md#loio2d8b7d04dcae402f911d119437ce0a74__section_space_management)
-   [Translation Tool Privileges](privileges-by-app-tool-object-and-task-2d8b7d0.md#loio2d8b7d04dcae402f911d119437ce0a74__section_translation)
-   [Security Tool Privileges](privileges-by-app-tool-object-and-task-2d8b7d0.md#loio2d8b7d04dcae402f911d119437ce0a74__section_security)
-   [Transport Tool Privileges](privileges-by-app-tool-object-and-task-2d8b7d0.md#loio2d8b7d04dcae402f911d119437ce0a74__section_transport)
-   [System Monitor Tool Privileges](privileges-by-app-tool-object-and-task-2d8b7d0.md#loio2d8b7d04dcae402f911d119437ce0a74__section_system_monitor)
-   [Data Sharing Cockpit Tool Privileges](privileges-by-app-tool-object-and-task-2d8b7d0.md#loio2d8b7d04dcae402f911d119437ce0a74__section_data_sharing_cockpit)
-   [System Tool Privileges](privileges-by-app-tool-object-and-task-2d8b7d0.md#loio2d8b7d04dcae402f911d119437ce0a74__section_system)
-   [External Data Consumption](privileges-by-app-tool-object-and-task-2d8b7d0.md#loio2d8b7d04dcae402f911d119437ce0a74__section_external_data_consumption)
-   [The Command Line Interface](privileges-by-app-tool-object-and-task-2d8b7d0.md#loio2d8b7d04dcae402f911d119437ce0a74__section_cli)



<a name="loio2d8b7d04dcae402f911d119437ce0a74__section_repository_explorer"/>

## Repository Explorer Privileges

The following privileges are required to use the <span class="SAP-icons-V5"></span> \(*Repository Explorer*\) app.


<table>
<tr>
<th valign="top">

App/Object/Task

</th>
<th valign="top">

Privileges

</th>
</tr>
<tr>
<td valign="top">

<span class="SAP-icons-V5"></span> \(*Repository Explorer*\)

See [Repository Explorer](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/f8ce0b4a24fe473a962176c8aa3cad42.html "The Repository Explorer gives you access to all your SAP Datasphere objects. You can search and filter the list, open or act on existing objects, and create new objects.") :arrow_upper_right:

</td>
<td valign="top">

To access all your SAP Datasphere objects in the *Repository Explorer*, you must have a scoped role that grants you access to a space with the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Spaces Files* \(`-R------`\) - To access objects in a space.

In addition, if you want to use natural language search, it must be enabled in your tenant \(see [Enable SAP Business AI for SAP Datasphere](../Creating-and-Configuring-Your-Tenant/enable-sap-business-ai-for-sap-datasphere-1b3fe45.md)\) and you must have the following global privilege:

-   *Data Warehouse AI Consumption* \(`----E---`\) - To use SAP Business AI features.

Any role template that gives access to SAP Datasphere grants these scoped privileges and the *DW AI Consumer* global role grants the global privilege. For more information, see [Privileges and Permissions](privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](standard-roles-delivered-with-sap-datasphere-a50a51d.md). 

</td>
</tr>
</table>



<a name="loio2d8b7d04dcae402f911d119437ce0a74__section_catalog_marketplace"/>

## Catalog & Marketplace Privileges

The following privileges are required to use the <span class="SAP-icons-V5"></span>\(*Catalog & Marketplace*\) app.


<table>
<tr>
<th valign="top">

App/Object/Task

</th>
<th valign="top">

Privileges

</th>
</tr>
<tr>
<td valign="top">

Browse data products and assets in the Catalog

See [Searching for Data Products and Assets in the Catalog](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/10478251045b43e782fa15e0f3e113b0.html "The catalog is the place where you can discover data products and assets, such as models and SAP Analytics Cloud stories. By using the search and filtering features to narrow the search results, you can learn more about the objects you find and mark some as your favorite.") :arrow_upper_right: and [Accessing Catalog Assets](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/dc061a23484241b1b791f5540b1f38e3.html "Use the catalog Assets collection to view data and analytic assets for use in your modeling and other projects. You can see detailed metadata, including lineage information, for each assets and, if you have the appropriate permissions, can open the asset in its source system.") :arrow_upper_right:

</td>
<td valign="top">

To browse data products and assets in the catalog, you must have a global role that grants you the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Catalog Asset* \(`–R–––--`\) - To access the catalog and view objects in the *Assets* and *Data Products* collections.
-   *Catalog Glossary Object* \(`–R–––--`\) - To view terms.
-   *Catalog Tag Hierarchy* \(`–R–––--`\) - To view tag hierarchies and tags.
-   *Catalog KPI Object* \(`–R–––--`\) - To view KPIs.

The *Catalog User* global role and the *DW Viewer* role template \(used directly as a global role\) applied together, for example, grant these privileges. For more information, see [Privileges and Permissions](privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](standard-roles-delivered-with-sap-datasphere-a50a51d.md).

</td>
</tr>
<tr>
<td valign="top">

Install data products

See [Installing Data Products](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/ea7cb802cbea47b39a441888873c3a49.html "Use the catalog Data Product collection to view data products for use in your modeling and other projects. You can see detailed metadata for each data product and if you have the appropriate permissions, install it to an SAP Datasphere space.") :arrow_upper_right:

</td>
<td valign="top">

To search for and evaluate objects in the *Data Products* collection, you must have

-   A global role that grants you the following privileges:
    -   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
    -   *Catalog Asset* \(`–R–––--`\) - To access the catalog and view objects in the *Assets* and *Data Products* collections.

-   A scoped role that grants you access to the space or spaces where you can install data products, with the following privileges :
    -   *Spaces* \(`–R–––--`\) - To access a space.
    -   *Space Files* \(`CRUD–--`\) - To install data products in or uninstall data products from a space.
    -   *Data Warehouse Data Builder* \(`CRUD----`\) - To create, edit and delete *Data Builder* objects.


The *Catalog User* global role and the *DW Modeler* scoped role template, applied together for example, grant these privileges. For more information, see [Privileges and Permissions](privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](standard-roles-delivered-with-sap-datasphere-a50a51d.md). 

</td>
</tr>
<tr>
<td valign="top">

Install Marketplace data products

See [Installing Marketplace Data Products](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/92c35efd6a4945a1a78250539aee9a51.html "Use the catalog Data Products (Marketplace) collection to view data products for use in your modeling and other projects. You can see detailed metadata, including lineage information, for each data product, test the sample data sets (if available), and if you have the appropriate permissions, install it to an SAP Datasphere space.") :arrow_upper_right:

</td>
<td valign="top">

To search for and evaluate objects in the *Data Products \(Marketplace\)* collection, you must have:

-   A global role that grants you the following privilege:
    -   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
    -   *Catalog Asset* \(`–R–––--`\) - To access the catalog.

-   A scoped role that grants you access to the space or spaces to install data products, with the following privileges:
    -   *Spaces* \(`–R–––--`\) - To access a space.
    -   *Space Files* \(`CRU––--`\) - To install data products in a space.
    -   *Data Warehouse Data Integration* \(`-RU––--`\) - To acquire data in the space where the data product is installed.
    -   *Data Warehouse Connection* \(`CRU––--`\) - To check the license of installed data products.


The *Catalog User* global role and the *DW Modeler* scoped role template, applied together for example, grant these privileges. For more information, see [Privileges and Permissions](privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](standard-roles-delivered-with-sap-datasphere-a50a51d.md). 

</td>
</tr>
<tr>
<td valign="top">

Govern and enrich Catalog assets

See [Governing Catalog Assets](https://help.sap.com/viewer/aca3ccb4b2f84eb8b6154e8fd2812c0e/cloud/en-US/1218c12e72c34cfd96293e566badb60c.html "Users with a catalog administrator role can set up governance for assets using hierarchical tags and business glossaries, create KPIs to measure progress towards company goals, and publish assets, glossary terms, and KPIs to the catalog.") :arrow_upper_right:

</td>
<td valign="top">

To govern and enrich catalog assets, you must have a global role that grants you the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Catalog Asset* \(`–RU––-M`\) - To edit an asset's name and short and long descriptions and add term, KPI, and tag relationships on the asset details page.
-   *Catalog Glossary* \(`CRUD–--`\) - To add, edit, and delete glossaries.
-   *Catalog Glossary Object* \(`CRUD–-M`\) - To add, edit, and delete categories and terms for glossaries. Also, to publish or unpublish terms.
-   *Catalog KPI Object* \(`CRUD–-M`\) - To add, edit, and delete categories and KPIs. Also, to publish and unpublish KPIs.
-   *Catalog KPI Template* \(`-RU-–--`\) - To edit the KPI template.
-   *Catalog Tag Hierarchy* \(`CRUD–--`\) - To add, edit, and delete tag hierarchies and tags.

The *Catalog Administrator* global role and the *DW Viewer* role template \(used directly as a global role\) applied together, for example, grant these privileges. For more information, see [Privileges and Permissions](privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](standard-roles-delivered-with-sap-datasphere-a50a51d.md). 

</td>
</tr>
<tr>
<td valign="top">

Connect, manage and monitor Catalog source systems

See [Connecting Source Systems](https://help.sap.com/viewer/aca3ccb4b2f84eb8b6154e8fd2812c0e/cloud/en-US/0b5de87f256f466f95b46d4bcaa52640.html "Source systems are connected to the catalog automatically through an SAP Business Data Cloud formation or manually through SAP Datasphere or the SAP Business Data Cloud cockpit on the Metadata Extractions page. After connection, the catalog monitors these systems and extracts metadata for their objects. This process make the objects discoverable in the catalog.") :arrow_upper_right: and [Managing and Monitoring Source Systems](https://help.sap.com/viewer/aca3ccb4b2f84eb8b6154e8fd2812c0e/cloud/en-US/0bdc7d3a6bcb44a09245cb21360d9775.html "As a user with the catalog administrator role, you can manage and monitor data sources that are connected to the catalog. You can ensure that the catalog contains the most up-to-date content and troubleshoot any issues that arise.") :arrow_upper_right:

</td>
<td valign="top">

To connect, manage and monitor catalog source systems, you must have a global role that grants you the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Catalog System* \(`CRUDE--`\) - To create, view, edit, and delete source system connections and manually synchronize source system.
-   *Catalog Log* \(`-R-----`\) - To view source system extraction summary and extraction logs in the system details.

The *Catalog Administrator* global role and the *DW Viewer* role template \(used directly as a global role\) applied together, for example, grant these privileges. For more information, see [Privileges and Permissions](privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](standard-roles-delivered-with-sap-datasphere-a50a51d.md). 

</td>
</tr>
</table>



<a name="loio2d8b7d04dcae402f911d119437ce0a74__section_semantic_onboarding"/>

## Semantic Onboarding Privileges

The following privileges are required to use the <span class="FPA-icons-V3"></span> \(*Semantic Onboarding*\) app.


<table>
<tr>
<th valign="top">

App/Object/Task

</th>
<th valign="top">

Privileges

</th>
</tr>
<tr>
<td valign="top">

Import objects from SAP systems

See [Importing Objects with Semantics from SAP S/4HANA, SAP BW∕4HANA and SAP BW Bridge](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/361729b49aea4519a6e8910b035dbf6c.html "Users with the DW Modeler role (or equivalent privileges) can use the Import Entities wizard to import semantically-rich objects from your SAP S/4HANA Cloud, SAP S/4HANA on-premise, SAP BW∕4HANA, and SAP BW bridge connections. The wizard creates Business Builder and Data Builder entities (along with all the objects on which they depend) in SAP Datasphere.") :arrow_upper_right:

</td>
<td valign="top">

To import objects with semantics from SAP S/4HANA, SAP BW∕4HANA and SAP BW Bridge, you must have a scoped role that grants you access to a space with the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Data Warehouse Connection* \(`-R------`\) - To access remote objects.
-   *Data Warehouse Data Builder* \(`CRUD----`\) - To create, edit and delete *Data Builder* objects.
-   *Data Warehouse Business Builder* \(`CRUD----`\) - To create, edit and delete *Business Builder* objects.
-   *Data Warehouse Business Entity* \(`CRUD----`\) - To create, edit and delete *Business Builder* business entities.
-   *Data Warehouse Consumption Model* \(`CRUD----`\) - To create, edit and delete *Business Builder* consumption models.
-   *Space Files* \(`CRUD----`\) - To create, read, update, and delete objects in your spaces.

The *DW Modeler* role template, for example, grants these privileges. For more information, see [Privileges and Permissions](privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](standard-roles-delivered-with-sap-datasphere-a50a51d.md). 

</td>
</tr>
<tr>
<td valign="top">

Import content from the Content Network

See [Importing SAP and Partner Business Content from the Content Network](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/400078d689bf4454b3fc977a4e201c2f.html "Users with an administrator role or space administrator role, can use the Semantic Onboarding app to import business content and sample content from SAP and partners published to the Content Network.") :arrow_upper_right:

</td>
<td valign="top">

To import content into a space via the *Import* app, you must have either:


<table>
<tr>
<td valign="top">

A global role that allows you to update any space and to create new spaces if necessary, by granting you the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Lifecycle* \(`-R---MS-`\) - To use the *Transport* apps.
-   *Spaces* \(`-------M`\) - To update all spaces and space properties.
-   *Spaces* \(`C-------`\) - To create spaces.
-   *Space Files* \(`-------M`\) - To create, read, update, and delete all objects in all spaces.

The *DW Administrator* role, for example, grants these privileges.

</td>
<td valign="top">

A combination of a global role and a scoped role:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   A global role that grants you the following privileges:
    -   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
    -   *Lifecycle* \(`-R---MS-`\) - To use the *Transport* apps.

-   A scoped role that grants you access to the space or spaces to import into with the following privileges:
    -   *Data Warehouse Data Builder* \(`CRUD--S-`\) - To create, read, update, delete and share data builder objects \(and any other relevant object privileges to allow you to create and update other types of objects contained in the package\).
    -   *Spaces* \(`--U-----`\) - To update your spaces and their properties.
    -   *Space Files* \(`CRUD----`\) - To create, read, update, and delete objects in your spaces.


The *DW Space Administrator* role template, for example, grants this combination of privileges.

</td>
</tr>
</table>

For more information, see [Privileges and Permissions](privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](standard-roles-delivered-with-sap-datasphere-a50a51d.md). 

</td>
</tr>
<tr>
<td valign="top">

Install Marketplace data products

See [Searching for Data Products and Assets in the Catalog](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/10478251045b43e782fa15e0f3e113b0.html "The catalog is the place where you can discover data products and assets, such as models and SAP Analytics Cloud stories. By using the search and filtering features to narrow the search results, you can learn more about the objects you find and mark some as your favorite.") :arrow_upper_right:

</td>
<td valign="top">

To search for and evaluate objects in the *Data Products \(Marketplace\)* collection, you must have:

-   A global role that grants you the following privilege:
    -   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
    -   *Catalog Asset* \(`–R–––--`\) - To access the catalog.

-   A scoped role that grants you access to the space or spaces to install data products, with the following privileges:
    -   *Spaces* \(`–R–––--`\) - To access a space.
    -   *Space Files* \(`CRU––--`\) - To install data products in a space.
    -   *Data Warehouse Data Integration* \(`-RU––--`\) - To acquire data in the space where the data product is installed.
    -   *Data Warehouse Connection* \(`CRU––--`\) - To check the license of installed data products.


The *Catalog User* global role and the *DW Modeler* scoped role template, applied together for example, grant these privileges. For more information, see [Privileges and Permissions](privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](standard-roles-delivered-with-sap-datasphere-a50a51d.md). 

</td>
</tr>
</table>



<a name="loio2d8b7d04dcae402f911d119437ce0a74__section_business_builder"/>

## Business Builder Privileges

The following privileges are required to use the <span class="FPA-icons-V3"></span> \(*Business Builder*\) app.


<table>
<tr>
<th valign="top">

App/Object/Task

</th>
<th valign="top">

Privileges

</th>
</tr>
<tr>
<td valign="top">

Business entities

See [Creating a Business Entity](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/c912cdc1537d4efbb24b08327ea68918.html "You use business entities to build your consumption model for analysis and reporting.") :arrow_upper_right:

</td>
<td valign="top">

To create business entities, you must have a scoped role that grants you access to a space with the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Data Warehouse Business Builder* \(`CRUD----`\) - To create, edit and delete *Business Builder* objects.
-   *Data Warehouse Business Entity* \(`CRUD----`\) - To create, edit and delete *Business Builder* business entities.
-   *Data Warehouse Data Builder* \(`-R------`\) - To open *Data Builder* objects for linking to business entities.
-   *Space Files* \(`CRUD----`\) - To create, read, update, and delete objects in your spaces.

The *DW Modeler* role template, for example, grants these privileges. For more information, see [Privileges and Permissions](privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](standard-roles-delivered-with-sap-datasphere-a50a51d.md). 

</td>
</tr>
<tr>
<td valign="top">

Fact models

See [Creating a Fact Model](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/5bbd14a328b549b2b53fce830ea25c15.html "Fact models are reusable models you can use to streamline the creation of other models within the same business context.") :arrow_upper_right:

</td>
<td valign="top">

To create fact models, you must have a scoped role that grants you access to a space with the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Data Warehouse Business Builder* \(`CRUD----`\) - To create, edit and delete *Business Builder* objects.
-   *Data Warehouse Fact Model* \(`CRUD----`\) - To create, edit and delete *Business Builder* fact models.
-   *Space Files* \(`CRUD----`\) - To create, read, update, and delete objects in your spaces.

The *DW Modeler* role template, for example, grants these privileges. For more information, see [Privileges and Permissions](privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](standard-roles-delivered-with-sap-datasphere-a50a51d.md). 

</td>
</tr>
<tr>
<td valign="top">

Consumption models

See [Creating a Consumption Model](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/337fa99de4a44700ba49e2214a1f3349.html "Consumption models are the basis to consume your data.") :arrow_upper_right:

</td>
<td valign="top">

To create consumption models, you must have a scoped role that grants you access to a space with the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Data Warehouse Business Builder* \(`CRUD----`\) - To create, edit and delete *Business Builder* objects.
-   *Data Warehouse Consumption Model* \(`CRUD----`\) - To create, edit and delete *Business Builder* consumption models.
-   *Space Files* \(`CRUD----`\) - To create, read, update, and delete objects in your spaces.

The *DW Modeler* role template, for example, grants these privileges. For more information, see [Privileges and Permissions](privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](standard-roles-delivered-with-sap-datasphere-a50a51d.md). 

</td>
</tr>
<tr>
<td valign="top">

Authorization scenarios

See [Authorization Scenario](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/46d8c42e1b1f421c9735a7cbc6fdba60.html "Authorization scenarios allow modelers to define which data is relevant to a user's context. They are made available through business entities and can be used in consumption models for specific use-cases.") :arrow_upper_right:

</td>
<td valign="top">

To create authorization scenarios, you must have a scoped role that grants you access to a space with the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Data Warehouse Business Builder* \(`CRUD----`\) - To create, edit and delete *Business Builder* objects.
-   *Data Warehouse Authorization Scenario* \(`CRUD----`\) - To create, edit and delete *Business Builder* authorization scenarios.
-   *Data Warehouse Data Builder* \(`CRUD----`\) - To create, edit and delete *Data Builder* objects.
-   *Space Files* \(`CRUD----`\) - To create, read, update, and delete objects in your spaces.

The *DW Modeler* role template, for example, grants these privileges. For more information, see [Privileges and Permissions](privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](standard-roles-delivered-with-sap-datasphere-a50a51d.md). 

</td>
</tr>
</table>



<a name="loio2d8b7d04dcae402f911d119437ce0a74__section_data_builder"/>

## Data Builder Privileges

The following privileges are required to use the <span class="FPA-icons-V3"></span> \(*Data Builder*\) app.


<table>
<tr>
<th valign="top">

App/Object/Task

</th>
<th valign="top">

Privileges

</th>
</tr>
<tr>
<td valign="top">

Import objects with semantics from SAP S/4HANA, SAP BW∕4HANA and SAP BW Bridge

See [Importing Objects with Semantics from SAP S/4HANA, SAP BW∕4HANA and SAP BW Bridge](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/361729b49aea4519a6e8910b035dbf6c.html "Users with the DW Modeler role (or equivalent privileges) can use the Import Entities wizard to import semantically-rich objects from your SAP S/4HANA Cloud, SAP S/4HANA on-premise, SAP BW∕4HANA, and SAP BW bridge connections. The wizard creates Business Builder and Data Builder entities (along with all the objects on which they depend) in SAP Datasphere.") :arrow_upper_right:

</td>
<td valign="top">

To import objects with semantics from SAP S/4HANA, SAP BW∕4HANA and SAP BW Bridge, you must have a scoped role that grants you access to a space with the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Data Warehouse Connection* \(`-R------`\) - To access remote objects.
-   *Data Warehouse Data Builder* \(`CRUD----`\) - To create, edit and delete *Data Builder* objects.
-   *Data Warehouse Business Builder* \(`CRUD----`\) - To create, edit and delete *Business Builder* objects.
-   *Data Warehouse Business Entity* \(`CRUD----`\) - To create, edit and delete *Business Builder* business entities.
-   *Data Warehouse Consumption Model* \(`CRUD----`\) - To create, edit and delete *Business Builder* consumption models.
-   *Space Files* \(`CRUD----`\) - To create, read, update, and delete objects in your spaces.

The *DW Modeler* role template, for example, grants these privileges. For more information, see [Privileges and Permissions](privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](standard-roles-delivered-with-sap-datasphere-a50a51d.md). 

</td>
</tr>
<tr>
<td valign="top">

Import tables and views from sources

See [Importing Tables and Views from Sources](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/7c4acd33e39a451e99c87f0661772443.html "Import tables and views from a connection, Open SQL schema, HDI container or other source available in your space.") :arrow_upper_right:

</td>
<td valign="top">

To import tables and views from a connection, Open SQL schema, HDI container or another source available in your space, you must have a scoped role that grants you access to a space with the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Data Warehouse Connection* \(`-R------`\) - To import remote tables.
-   *Data Warehouse Data Builder* \(`CRUD----`\) - To create, edit and delete *Data Builder* objects.
-   *Space Files* \(`CRUD----`\) - To create, read, update, and delete objects in your spaces.

The *DW Modeler* role template, for example, grants these privileges. For more information, see [Privileges and Permissions](privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](standard-roles-delivered-with-sap-datasphere-a50a51d.md). 

</td>
</tr>
<tr>
<td valign="top">

Create local tables

See [Creating a Local Table](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/2509fe4d86aa472b9858164b55b38077.html "Create a table and define columns to receive data. You can add data from a flow or a CSV file, or import tables from a connection or a CSN file.") :arrow_upper_right:

</td>
<td valign="top">

To create local tables, you must have a scoped role that grants you access to a space with the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Data Warehouse Data Builder* \(`CRUD----`\) - To create, edit and delete *Data Builder* objects.
-   *Space Files* \(`CRUD----`\) - To create, read, update, and delete objects in your spaces.

The *DW Modeler* role template, for example, grants these privileges. For more information, see [Privileges and Permissions](privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](standard-roles-delivered-with-sap-datasphere-a50a51d.md). 

</td>
</tr>
<tr>
<td valign="top">

Create local tables from a `.csv` file

See [Creating a Local Table from a CSV File](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/8bba251c78874736963703cff56b1b74.html "Import a .csv file to create a table and fill it with the data from the file.") :arrow_upper_right:

</td>
<td valign="top">

To create local tables from a `.csv` file, you must have a scoped role that grants you access to a space with the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Data Warehouse Data Builder* \(`CRUD----`\) - To create, edit and delete *Data Builder* objects.
-   *Data Warehouse Consumption* \(`-RU-----`\) - To upload data in a local table.
-   *Space Files* \(`CRUD----`\) - To create, read, update, and delete objects in your spaces.

The *DW Modeler* role template, for example, grants these privileges. For more information, see [Privileges and Permissions](privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](standard-roles-delivered-with-sap-datasphere-a50a51d.md). 

</td>
</tr>
<tr>
<td valign="top">

Edit local table data

See [Maintain Local Table Data](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/4bd5e641be48409c8c79336df0c4a3c7.html "Use the Data Editor to add, delete, duplicate, or update records in local tables. You can also sort, filter, reorder, and replace data.") :arrow_upper_right:

</td>
<td valign="top">

To edit local tables' data in the *Data Editor*, you must have a scoped role that grants you access to a space with the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Data Warehouse Data Builder* \(`-RU-----`\) - To access the local table *Data Editor* screen in the *Data Builder*.
-   *Data Warehouse Consumption* \(`-RU-E---`\) - To add and delete data in a local table.
-   *Space Files* \(`CRUD----`\) - To create, read, update, and delete objects in your spaces.

The *DW Modeler* role template, for example, grants these privileges. For more information, see [Privileges and Permissions](privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](standard-roles-delivered-with-sap-datasphere-a50a51d.md). 

</td>
</tr>
<tr>
<td valign="top">

Views

See [Creating a Graphical View](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/27efb479c4814252964d3fbc6ca2dfc3.html "Create a view to query sources in an intuitive graphical interface. You can drag and drop sources from the Source Browser, join them as appropriate, add other operators to remove or create columns and filter or aggregate data, and specify measures and other aspects of your output structure in the output node.") :arrow_upper_right: and [Creating an SQL View](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/81920e4d583f45fd8761c662d3c8abab.html "Create a view to query sources in a powerful SQL editor. You can choose between writing a standard SQL query using SELECT statements and operators such as JOIN and UNION, or use SQLScript to produce a table function. You can drag sources from the Source Browser, and specify measures and other aspects of your output structure in the side panel.") :arrow_upper_right:

</td>
<td valign="top">

To create views, you must have a scoped role that grants you access to a space with the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Data Warehouse Data Builder* \(`CRUD----`\) - To create, edit and delete a graphical view.
-   *Space Files* \(`CRUD----`\) - To create, read, update, and delete objects in your spaces.

The *DW Modeler* role template, for example, grants these privileges. For more information, see [Privileges and Permissions](privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](standard-roles-delivered-with-sap-datasphere-a50a51d.md). 

</td>
</tr>
<tr>
<td valign="top">

Entity-relationship models

See [Creating an Entity-Relationship Model](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/a91c042549fb497384e756d5f5c71fde.html "Create an E/R model to import, visualize, edit, and deploy multiple tables and views together. You can use an E/R model to better understand a subset of the entities in your space, and to communicate this information to other stakeholders.") :arrow_upper_right:

</td>
<td valign="top">

To create E/R models, you must have a scoped role that grants you access to a space with the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Data Warehouse Data Builder* \(`CRUD----`\) - To create, edit and delete E/R models.
-   *Space Files* \(`CRUD----`\) - To create, read, update, and delete objects in your spaces.

The *DW Modeler* role template, for example, grants these privileges. For more information, see [Privileges and Permissions](privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](standard-roles-delivered-with-sap-datasphere-a50a51d.md). 

</td>
</tr>
<tr>
<td valign="top">

Analytic models

See [Creating an Analytic Model](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/e5fbe9e2cb93484dab8b1963145e565f.html "Create an analytic model as a basis for consumption in SAP Analytics Cloud.") :arrow_upper_right:

</td>
<td valign="top">

To create analytic models, you must have a scoped role that grants you access to a space with the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Data Warehouse Data Builder* \(`CRUD----`\) - To create, edit and delete *Data Builder* objects.
-   *Space Files* \(`CRUD----`\) - To create, read, update, and delete objects in your spaces.

The *DW Modeler* role template, for example, grants these privileges. For more information, see [Privileges and Permissions](privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](standard-roles-delivered-with-sap-datasphere-a50a51d.md). 

</td>
</tr>
<tr>
<td valign="top">

Flows

See [Creating a Replication Flow](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/25e2bd7a70d44ac5b05e844f9e913471.html "Create a replication flow to copy multiple data assets from a source to a target with support for delta loads.") :arrow_upper_right:, [Creating a Data Flow](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/e30fd1417e954577baae3246ea470c3f.html "Create a data flow to move and transform data in an intuitive graphical interface. You can drag and drop sources from the Source Browser, join them as appropriate, add other operators to remove or create columns, aggregate data, and do Python scripting, before writing the data to the target table.") :arrow_upper_right:, [Creating a Transformation Flow in a File Space](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/b917baf0431343bea8381fa37e12eeb8.html "Create transformation flows with local tables (file), shared local tables (file), shared local tables, and shared remote tables on a Delta Share runtime as sources, apply various transformations, and store the resulted dataset into another local table (file).") :arrow_upper_right: and [Creating a Transformation Flow](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/f7161e6c20204672ac4a6d90c81762e4.html "Create a transformation flow to load data from one or more sources, apply transformations (such as a join), and output the result in a target table. You can load a full set of data from one or more sources to a target table. You can add local tables and views, Open SQL schema objects, and also remote tables located in BW Bridge spaces. You can also load delta changes (including deleted records) from one source table to a target table.") :arrow_upper_right:

</td>
<td valign="top">

To create flows, you must have a scoped role that grants you access to a space with the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Data Warehouse Connection* \(`-R------`\) - To access remote objects.
-   *Data Warehouse Data Builder* \(`CRUD----`\) - To create, edit and delete flows.
-   *Space Files* \(`CRUD----`\) - To create, read, update, and delete objects in your spaces.

To run and schedule flows, you must, in addition, have the following privileges:

-   *Data Warehouse Data Integration* \(`-R------`\) - To view data integration task logs in the *Data Integration Monitor* app.

-   *Data Warehouse Data Integration* \(`--U-----`\) - To manually run data integration tasks.

-   *Data Warehouse Data Integration* \(`----E---`\) - To schedule data integration tasks.


The *DW Modeler* and *DW Integrator* role templates together, for example, grant these privileges. For more information, see [Privileges and Permissions](privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](standard-roles-delivered-with-sap-datasphere-a50a51d.md). 

</td>
</tr>
<tr>
<td valign="top">

Intelligent lookups

See [Creating an Intelligent Lookup](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/8f29f801faea4d48816d0339777f9d16.html "Create an intelligent lookup to merge data from two entities even if there are problems joining them. Intelligent lookup offers a business-centric, interactive data harmonization environment for subject matter experts.") :arrow_upper_right:

</td>
<td valign="top">

To create and run intelligent lookups, you must have a scoped role that grants you access to a space with the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Data Warehouse Data Builder* \(`CRUD----`\) - To create, edit, deploy and delete intelligent lookups.
-   *Data Warehouse Data Integration* \(`--U-----`\) - To run intelligent lookups and process results.
-   *Space Files* \(`CRUD----`\) - To create, read, update, and delete objects in your spaces.

The *DW Modeler* role template, for example, grants the privilege to create and manage intelligent lookups, and the *DW Integrator* role template grants the privilege to run them. For more information, see [Privileges and Permissions](privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](standard-roles-delivered-with-sap-datasphere-a50a51d.md). 

</td>
</tr>
<tr>
<td valign="top">

Task chains

See [Creating a Task Chain](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/d1afbc2b9ee84d44a00b0b777ac243e1.html "Group multiple tasks into a task chain and run them manually once, or periodically, through a schedule.") :arrow_upper_right:

</td>
<td valign="top">

To create task chains, you must have a scoped role that grants you access to a space with the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Data Warehouse Data Builder* \(`CRUD----`\) - To create, edit and delete task chains.
-   *Space Files* \(`CRUD----`\) - To create, read, update, and delete objects in your spaces.

To run and share task chains and configure email notifications, you must, in addition, have the following privileges:

-   *Data Warehouse Data Integration* \(`-R------`\) - To view data integration task logs in the *Data Integration Monitor* app.

-   *Data Warehouse Data Integration* \(`--U-----`\) - To manually run data integration tasks.

-   *Data Warehouse Data Integration* \(`----E---`\) - To schedule data integration tasks.

-   *Data Warehouse Data Builder* \(`------S-`\) - To share task chains to other spaces.
-   *User* \(`R-------`\) - To display and add notification recipients from a list of current tenant members, when setting up email notifications.

The *DW Modeler* and *DW Space Administrator* role templates together, for example, grant these privileges. For more information, see [Privileges and Permissions](privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](standard-roles-delivered-with-sap-datasphere-a50a51d.md). 

</td>
</tr>
<tr>
<td valign="top">

Data access controls

See [Securing Data with Data Access Controls](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/a032e51c730147c7a1fcac125b4cfe14.html "Users with a space administrator role can create data access controls to allow modelers to apply row-level security to Data Builder and Business Builder objects. Once a data access control is applied to an object, any user viewing its data either directly or via an object using it as a source, will see only those records they are authorized to view, based on the specified criteria.") :arrow_upper_right:

</td>
<td valign="top">

To create data access controls, you must have a scoped role that grants you access to a space with the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Data Warehouse Data Builder* \(`-R------`\) - To access the *Data Builder*.
-   *Data Warehouse Data Access Control* \(`CRUD----`\) - To create, read, update, and delete data access controls.

The *DW Space Administrator* role template, for example, grants these privileges. For more information, see [Privileges and Permissions](privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](standard-roles-delivered-with-sap-datasphere-a50a51d.md). 

</td>
</tr>
<tr>
<td valign="top">

Data viewer

See [Viewing Object Data](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/b338e4aa7e7e494eb68c383720ebfd3a.html "You can, at any time, view the data contained in (or output by) your tables, views, and other Data Builder objects. When working in the graphical view editor, you can view the data output by each node in the diagram.") :arrow_upper_right:

</td>
<td valign="top">

To view the data contained in *Data Builder* objects, you must have a scoped role that grants you access to a space with the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Space Files* \(`-R------`\) - To read objects in your spaces.
-   *Data Warehouse Data Builder* \(`-R------`\) - To open *Data Builder* objects.
-   *Data Warehouse Consumption*- To view data in the *Data Viewer* panel. Two levels of access are available:
    -   *Data Warehouse Consumption* \(`-R------`\) - To view only data output by views with the *Expose for Consumption* switch enabled.

        The *DW Viewer* role template, for example, grants this privilege.

    -   *Data Warehouse Consumption* \(`----E---`\) - To view data from any object or diagram node \(where this is supported\).

        The *DW Modeler* role template, for example, grants this privilege.



For more information, see [Privileges and Permissions](privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](standard-roles-delivered-with-sap-datasphere-a50a51d.md). 

</td>
</tr>
</table>



<a name="loio2d8b7d04dcae402f911d119437ce0a74__section_data_integration_monitor"/>

## Data Integration Monitor Privileges

The following privileges are required to use the <span class="FPA-icons-V3"></span> \(*Data Integration Monitor*\) app.


<table>
<tr>
<th valign="top">

Monitor

</th>
<th valign="top">

Privileges

</th>
</tr>
<tr>
<td valign="top">

Local tables

See [Monitoring Local Tables](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/374046156e5b47599fc9b96c8c3a4dce.html "Monitor all the local tables created for a space in the Data Builder and check their metrics.") :arrow_upper_right: and [Monitoring Local Tables (File)](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/6b2d0073a8684ee6a59d6f47d00ec895.html "Monitor your local tables (file). Check how and when they were last updated and if new data has still to be merged.") :arrow_upper_right:

</td>
<td valign="top">

To monitor local tables, you must have a scoped role that grants you access to a space with the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Data Warehouse Data Integration* \(`-R------`\) - To view data integration task logs in the *Data Integration Monitor* app.

-   *Data Warehouse Data Integration* \(`--U-----`\) - To manually run data integration tasks.

-   *Data Warehouse Data Integration* \(`----E---`\) - To schedule data integration tasks.


The *DW Integrator* role template, for example, grants these privileges. For more information, see [Privileges and Permissions](privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](standard-roles-delivered-with-sap-datasphere-a50a51d.md). 

</td>
</tr>
<tr>
<td valign="top">

Remote tables

See [Monitoring Remote Tables](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/4dd95d7bff1f48b399c8b55dbdd34b9e.html "In the Remote Tables monitor, you can find a remote table monitor per space. Here, you can copy data from remote tables that have been deployed in your space into SAP Datasphere, and you can monitor the replication of the data. You can copy or schedule copying the full set of data from the source, or you can set up replication of data changes in real-time via change data capturing (CDC).") :arrow_upper_right:

</td>
<td valign="top">

To replicate data and monitor remote tables, you must have a scoped role that grants you access to a space with the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Data Warehouse Data Integration* \(`-R------`\) - To view data integration task logs in the *Data Integration Monitor* app.

-   *Data Warehouse Data Integration* \(`--U-----`\) - To manually run data integration tasks.

-   *Data Warehouse Data Integration* \(`----E---`\) - To schedule data integration tasks.

-   *Data Warehouse Data Builder* \(`-R------`\) - To work with partitions.

The *DW Space Administrator* role template, for example, grants these privileges. For more information, see [Privileges and Permissions](privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](standard-roles-delivered-with-sap-datasphere-a50a51d.md). 

</td>
</tr>
<tr>
<td valign="top">

Views

See [Persisting and Monitoring Views](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/9af04c990f294fd28c00f46763dd8b0d.html "From Data Integration Monitor > > Views , you can monitor views that have been created in the Data Builder. You can persist these views (direct run or via a schedule) to make them available locally to improve the performance when accessing your data. You can monitor the existing persisted views to keep control of your data sizing and free up memory space.") :arrow_upper_right:

</td>
<td valign="top">

To persist and monitor views, you must have a combination of a global role and a scoped role:

-   A global role that grants you the following privileges:
    -   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
    -   *Data Warehouse Runtime* \(`-R------`\) - To allow users of the *View Analyzer* to download the generated SQL analyzer plan file.

-   A scoped role that grants you access to a space with the following privileges:
    -   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
    -   *Data Warehouse Data Integration* \(`-RU-E---`\) - To perform data replication/persistence actions \(in the *Data Integration Monitor* or *Data Builder*\), and schedule the actions.
    -   *Data Warehouse Data Builder* \(`-R------`\) - To work with partitions.


For example, the *DW Administrator* global role template grants the runtime privilege, the *DW Integrator* scoped role template grants the integration privilege, and the *DW Space Administrator* scoped role template grants the *Data Builder* privilege. For more information, see [Privileges and Permissions](privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](standard-roles-delivered-with-sap-datasphere-a50a51d.md). 

</td>
</tr>
<tr>
<td valign="top">

Flows

See [Monitoring Flows](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/b661ea0766a24c7d839df950330a89fd.html "In the Flows monitor, you can find all the deployed flows per space.") :arrow_upper_right:

</td>
<td valign="top">

To run and schedule flows, you must have a scoped role that grants you access to a space with the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Data Warehouse Data Integration* \(`-R------`\) - To view data integration task logs in the *Data Integration Monitor* app.

-   *Data Warehouse Data Integration* \(`--U-----`\) - To manually run data integration tasks.

-   *Data Warehouse Data Integration* \(`----E---`\) - To schedule data integration tasks.


The *DW Integrator* role template, for example, grants these privileges. For more information, see [Privileges and Permissions](privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](standard-roles-delivered-with-sap-datasphere-a50a51d.md). 

</td>
</tr>
<tr>
<td valign="top">

Remote queries

See [Monitoring Remote Queries](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/806d7f0c45a14f1fb07db0a226b2b822.html "In the Remote Queries monitor, you track the queries sent to your remote connected source systems for your space. You can monitor the communication between the federation layer of SAP HANA Cloud and the connected remote source systems, and analyze them.") :arrow_upper_right:

</td>
<td valign="top">

To monitor remote queries, you must have a scoped role that grants you access to a space with the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Data Warehouse Data Integration* \(`-R------`\) - To view data integration task logs in the *Data Integration Monitor* app.

-   *Data Warehouse Data Integration* \(`--U-----`\) - To manually run data integration tasks.

-   *Data Warehouse Data Integration* \(`----E---`\) - To schedule data integration tasks.


The *DW Integrator* role template, for example, grants these privileges. For more information, see [Privileges and Permissions](privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](standard-roles-delivered-with-sap-datasphere-a50a51d.md). 

</td>
</tr>
<tr>
<td valign="top">

Task chains

See [Monitoring Task Chains](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/4142201ec1aa49faad89a688a2f1852c.html "Monitor the status and progress of running and previously run task chains.") :arrow_upper_right:

</td>
<td valign="top">

To monitor task chains, you must have a scoped role that grants you access to a space with the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Data Warehouse Data Integration* \(`-R------`\) - To view data integration task logs in the *Data Integration Monitor* app.

-   *Data Warehouse Data Integration* \(`--U-----`\) - To manually run data integration tasks.

-   *Data Warehouse Data Integration* \(`----E---`\) - To schedule data integration tasks.


The *DW Integrator* role template, for example, grants these privileges. For more information, see [Privileges and Permissions](privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](standard-roles-delivered-with-sap-datasphere-a50a51d.md). 

</td>
</tr>
</table>



<a name="loio2d8b7d04dcae402f911d119437ce0a74__section_connections"/>

## Connections Privileges

The following privileges are required to use the <span class="FPA-icons-V3"></span> \(*Connections*\) app.


<table>
<tr>
<th valign="top">

App/Object/Task

</th>
<th valign="top">

Privileges

</th>
</tr>
<tr>
<td valign="top">

Create, edit, validate, and delete connections

See [Integrating Data via Connections](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/eb85e157ab654152bd68a8714036e463.html "Users with a space administrator or integrator role can create connections to SAP and non-SAP source systems, including cloud and on-premise systems and partner tools, and to target systems for outbound replication flows. Users with modeler roles can import data via connections for preparation and modeling in SAP Datasphere.") :arrow_upper_right:

</td>
<td valign="top">

To create, edit, validate, and delete connections, you must have a scoped role that grants you access to a space with the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Data Warehouse Connection* \(`CRUD----`\) - To create, edit, validate, or delete connections.
-   *Space Files* \(`CRUD----`\) - To create, read, update, and delete objects in your spaces.

The *DW Space Administrator* and *DW Integrator* role templates, for example, grant these privileges. For more information, see [Privileges and Permissions](privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](standard-roles-delivered-with-sap-datasphere-a50a51d.md). 

</td>
</tr>
</table>



<a name="loio2d8b7d04dcae402f911d119437ce0a74__section_space_management"/>

## Space Management Tool Privileges

The following privileges are required to use the tools inside ![](../images/Space_Management_a868247.png) \(*Space Management*\).


<table>
<tr>
<th valign="top">

Tool/Object/Task

</th>
<th valign="top">

Privileges

</th>
</tr>
<tr>
<td valign="top">

Create spaces

See [Create a Space](../Creating-Spaces-and-Allocating-Storage/create-a-space-bbd41b8.md) and [Create a File Space to Load Data in the Object Store](../Creating-Spaces-and-Allocating-Storage/create-a-file-space-to-load-data-in-the-object-store-9474446.md)

</td>
<td valign="top">

To create spaces, you must have a global role that grants you the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Spaces* \(`C-------`\) - To create spaces.
-   *User* \(`-R------`\) - To initialize the space for assigning users.
-   *Spaces* \(`-------M`\) - To update all spaces and space properties.
-   *Space Files* \(`-------M`\) - To view objects and data in all spaces.

The *DW Administrator* global role, for example, grants these privileges. For more information, see [Privileges and Permissions](privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](standard-roles-delivered-with-sap-datasphere-a50a51d.md). 

</td>
</tr>
<tr>
<td valign="top">

Copy a space

See [Copy a Space and its Contents](../Creating-Spaces-and-Allocating-Storage/copy-a-space-and-its-contents-73068ac.md)

</td>
<td valign="top">

To copy a space and its contents, you must have a global role that grants you the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Spaces* \(`C-------`\) - To create spaces.
-   *User* \(`-R------`\) - To initialize the space for assigning users.
-   *Spaces* \(`-------M`\) - To update all spaces and space properties.
-   *Space Files* \(`-------M`\) - To view objects and data in all spaces.

The *DW Administrator* global role, for example, grants these privileges. For more information, see [Privileges and Permissions](privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](standard-roles-delivered-with-sap-datasphere-a50a51d.md). 

</td>
</tr>
<tr>
<td valign="top">

Allocate storage to a space

See [Allocate Storage to a Space](../Creating-Spaces-and-Allocating-Storage/allocate-storage-to-a-space-f414c3d.md)

</td>
<td valign="top">

To allocate disk and memory storage to spaces, you must have a global role that grants you the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Spaces* \(`-------M`\) - To update all spaces and space properties.
-   *Space Files* \(`-------M`\) - To view objects and data in all spaces.

The *DW Administrator* global role, for example, grants these privileges. For more information, see [Privileges and Permissions](privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](standard-roles-delivered-with-sap-datasphere-a50a51d.md). 

</td>
</tr>
<tr>
<td valign="top">

Set priorities and statement limits for spaces or groups

See [Set Priorities and Statement Limits for Spaces or Groups](../Creating-Spaces-and-Allocating-Storage/set-priorities-and-statement-limits-for-spaces-or-groups-d66ac1e.md)

</td>
<td valign="top">

To set priorities and statement limits for spaces or groups, you must have a global role that grants you the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *System Information* \(`-RU-----`\) - To access the *Configuration* area in the *System* tool.

The *DW Administrator* global role, for example, grants these privileges. For more information, see [Privileges and Permissions](privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](standard-roles-delivered-with-sap-datasphere-a50a51d.md). 

</td>
</tr>
<tr>
<td valign="top">

Control user access to spaces

See [Control User Access to Your Space](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/9d59fe511ae644d98384897443054c16.html "You can assign users to your space and manage them.") :arrow_upper_right:

</td>
<td valign="top">

To assign users to your space and manage them from the *Users* area in your space details page, you must have a scoped role that grants you access to a space with the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Spaces* \(`-RU-----`\) - To open and update your space in the *Space Management* tool.
-   *Space Files* \(`-R------`\) - To view objects in your space.
-   *Scoped Role User Assignment* \(`-------M`\) - To manage the users who can access your space.

The *DW Space Administrator* role template, for example, grants these privileges. For more information, see [Privileges and Permissions](privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](standard-roles-delivered-with-sap-datasphere-a50a51d.md). 

</td>
</tr>
<tr>
<td valign="top">

Create database users

See [Create a Database User](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/798e3fd6707940c3bd2219b2d1ebaac2.html "Users with a space administration role can create database users, granting them privileges to read from and/or write to an Open SQL schema with restricted access to the space schema.") :arrow_upper_right:

</td>
<td valign="top">

To create database users, you must have a scoped role that grants you access to a space with the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Spaces* \(`-RU-----`\) - To open and update your space in the *Space Management* tool.
-   *Space Files* \(`-R------`\) - To view objects in your space.

The *DW Space Administrator* role template, for example, grants these privileges. For more information, see [Privileges and Permissions](privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](standard-roles-delivered-with-sap-datasphere-a50a51d.md). 

</td>
</tr>
<tr>
<td valign="top">

Add an HDI container and access its objects in your space

See [Add an HDI Container and Access its Objects in Your Space](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/5d55da5514b240ff8d3a970bf7dc6705.html "To access calculation views and other HDI objects as sources for your views and data flows, you must add the HDI container to your SAP Datasphere space.") :arrow_upper_right:

</td>
<td valign="top">

To add an HDI container and access its objects in your space, you must have a scoped role that grants you access to a space with the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Spaces* \(`-RU-----`\) - To read and update your spaces.
-   *Space Files* \(`-RU-----`\) - To read and update objects in your spaces.
-   *Data Warehouse Connection* \(`-RU-----`\) - To access remote objects.

The *DW Space Administrator* role template, for example, grants these privileges. For more information, see [Privileges and Permissions](privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](standard-roles-delivered-with-sap-datasphere-a50a51d.md). 

</td>
</tr>
<tr>
<td valign="top">

Create a time table and dimension views

See [Create Time Data and Dimensions](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/c5cfce4d22b04650b2fd6078762cdeb9.html "Create a time table and dimension views in your space to provide standardized time data for your analyses. The time table contains a record for each day in the specified period (by default from 1900 to 2050), and the dimension views allow you to work with this date data at a granularity of day, week, month, quarter, and year, and to drill down and up in hierarchies.") :arrow_upper_right:

</td>
<td valign="top">

To work with the time table and dimensions in your space, you must have a scoped role that grants you access to a space with the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Spaces* \(`-R------`\) - To open your space in the *Space Management* tool.
-   *Space Files* \(`-R------`\) - To view objects in your space.
-   *Data Warehouse Data Builder* \(`-RUD----`\) - To read, update and delete objects in the *Data Builder*.

The *DW Space Administrator* role template, for example, grants these privileges. For more information, see [Privileges and Permissions](privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](standard-roles-delivered-with-sap-datasphere-a50a51d.md). 

</td>
</tr>
<tr>
<td valign="top">

Log read and change actions for audit

See [Logging Read and Change Actions for Audit](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/266553976e1c4db9aaa28a75e2308b77.html "You can enable audit logs for your space so that read and change actions (policies) are recorded. Administrators can then analyze who performed which action at which point in time.") :arrow_upper_right:

</td>
<td valign="top">

To enable audit logs for your space, you must have a scoped role that grants you access to a space with the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Spaces* \(`-RU-----`\) - To open and update your space in the *Space Management* tool.
-   *Space Files* \(`-R------`\) - To view objects in your space.

The *DW Space Administrator* role template, for example, grants these privileges. For more information, see [Privileges and Permissions](privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](standard-roles-delivered-with-sap-datasphere-a50a51d.md). 

</td>
</tr>
<tr>
<td valign="top">

Monitor space storage consumption

See [Monitor Your Space Storage Consumption](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/94fe6c13f6a340288cd50ee355566591.html "See the storage amount assigned to and used by your space.") :arrow_upper_right:

</td>
<td valign="top">

To monitor the storage consumption of your space, you must have a scoped role that grants you access to a space with the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Spaces* \(`-R------`\) - To open your space in the *Space Management* tool.
-   *Space Files* \(`-R------`\) - To view objects in your space.

The *DW Space Administrator* role template, for example, grants these privileges. For more information, see [Privileges and Permissions](privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](standard-roles-delivered-with-sap-datasphere-a50a51d.md). 

</td>
</tr>
<tr>
<td valign="top">

Unlock a locked space

See [Unlock a Locked Space](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/c05b6a6d06db427dbdd3041d61fd5840.html "When a space exceeds its assigned storage or when the audit logs enabled in the space consume too much disk storage, the space is automatically locked after 60 minutes if you do not free up space. Also, when the tenant disk usage has reached a critical threshold, all spaces are automatically locked to protect your tenant from storage-related outages.") :arrow_upper_right:

</td>
<td valign="top">

To manually lock or unlock your space, you must have a scoped role that grants you access to a space with the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Spaces* \(`-RU-----`\) - To open and update your space in the *Space Management* tool.
-   *Space Files* \(`-RU-----`\) - To read and update objects in your space.

The *DW Space Administrator* role template, for example, grants these privileges. For more information, see [Privileges and Permissions](privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](standard-roles-delivered-with-sap-datasphere-a50a51d.md). 

</td>
</tr>
<tr>
<td valign="top">

Delete spaces

See [Delete Your Space](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/3eb19b96e6ba41dfbffd759c5c8370bb.html "Delete a space if you are sure that you no longer need any of its content or data. The space is moved to the recycle bin, from which it can either be restored or permanently deleted from the database.") :arrow_upper_right:

</td>
<td valign="top">

To move your space to the *Recycle Bin* area, you must have a scoped role that grants you access to a space with the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Spaces* \(`-RUD----`\) - To open, update and delete your space in the *Space Management* tool.
-   *Space Files* \(`-R------`\) - To view objects in your space.
-   *Scoped Role User Assignment* \(`-------M`\) - To manage the users who can access your space.

The *DW Space Administrator* role template, for example, grants these privileges. For more information, see [Privileges and Permissions](privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](standard-roles-delivered-with-sap-datasphere-a50a51d.md). 

</td>
</tr>
<tr>
<td valign="top">

Restore spaces from, or empty the recycle bin

See [Restore Spaces from, or Empty the Recycle Bin](../Creating-Spaces-and-Allocating-Storage/restore-spaces-from-or-empty-the-recycle-bin-c4e26c0.md)

</td>
<td valign="top">

To restore spaces, or delete them from the *Recycle Bin*, you must have a global role with the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Spaces* \(`-------M`\) - To access the *Recycle Bin* in the *Space Management* tool.
-   *Space Files* \(`-------M`\) - To view objects and data in all spaces.

The *DW Administrator* role template, for example, grants these privileges. For more information, see [Privileges and Permissions](privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](standard-roles-delivered-with-sap-datasphere-a50a51d.md). 

</td>
</tr>
</table>



<a name="loio2d8b7d04dcae402f911d119437ce0a74__section_translation"/>

## Translation Tool Privileges

The following privileges are required to use the tools inside <span class="SAP-icons-V5"></span> \(*Translation*\).


<table>
<tr>
<th valign="top">

Tool/Object/Task

</th>
<th valign="top">

Privileges

</th>
</tr>
<tr>
<td valign="top">

Enable translation for a space

See [Translating Metadata for SAP Analytics Cloud](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/fe829debe389450394cf7a15860e2caa.html "Users with a scoped role containing the Translation privilege can translate metadata such as business names and column names for dimensions and analytic models, and hierarchy dimension labels for SAP Analytics Cloud stories.") :arrow_upper_right:

</td>
<td valign="top">

To enable translation for your space, and to manage translation in the *Translation* tool, you must have a scoped role that grants you access to a space with the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Spaces* \(`-RU-----`\) - To enable translation and select the source language for your space.
-   *Space Files* \(`-RU-----`\) - To read and update objects in your space.
-   *Data Warehouse Data Builder* \(`-RU-----`\) - To read and update *Data Builder* objects.
-   *Translation* \(`CR-D----`\) - To access the *Translation* tool, select objects to translate, manage and delete translations.

The *DW Space Administrator* role template, for example, grants these privileges. For more information, see [Privileges and Permissions](privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](standard-roles-delivered-with-sap-datasphere-a50a51d.md). 

</td>
</tr>
</table>



<a name="loio2d8b7d04dcae402f911d119437ce0a74__section_security"/>

## Security Tool Privileges

The following privileges are required to use the tools inside <span class="FPA-icons-V3"></span> \(*Security*\).


<table>
<tr>
<th valign="top">

Tool/Object/Task

</th>
<th valign="top">

Privileges

</th>
</tr>
<tr>
<td valign="top">

Users

See [Managing SAP Datasphere Users](managing-sap-datasphere-users-4fb82cb.md)

</td>
<td valign="top">

To manage users, you must have a global role that grants you the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *User* \(`CRUD----`\) - To access the <span class="FPA-icons-V3"></span> \(*Users*\)area in the <span class="FPA-icons-V3"></span> \(*Security*\) tool and to create, update, and delete users.
-   *User* \(`-------M`\) - To assign users to roles.

The *DW Administrator* global role, for example, grants these privileges. For more information, see [Privileges and Permissions](privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](standard-roles-delivered-with-sap-datasphere-a50a51d.md). 

</td>
</tr>
<tr>
<td valign="top">

Roles

See [Managing Roles and Privileges](managing-roles-and-privileges-3740dac.md)

Authorization Overview

See [View Authorizations by User, Role, or Space](view-authorizations-by-user-role-or-space-c6538ea.md)

</td>
<td valign="top">

To manage roles and privileges, you must have a global role that grants you the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Role* \(`CRUD----`\) - To access the <span class="FPA-icons-V3"></span> \(*Roles*\) and <span class="SAP-icons-V5"></span> \(*Authorization Overview*\) areas in the <span class="FPA-icons-V3"></span> \(*Security*\) tool and to create, update, and delete roles.
-   *User* \(`-------M`\) - To add users to roles.
-   *Spaces* \(`-------M`\) - To add spaces to scoped roles.

The *DW Administrator* global role, for example, grants these privileges. For more information, see [Privileges and Permissions](privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](standard-roles-delivered-with-sap-datasphere-a50a51d.md). 

</td>
</tr>
<tr>
<td valign="top">

Activities

See [Monitor Object Changes with Activities](../monitor-object-changes-with-activities-08e607c.md)

</td>
<td valign="top">

To monitor object changes with activities, you must have a global role that grants you the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Activity Log* \(`-R------`\) - To view and download activities. The *DW Administrator* role template, for example, grants this privilege.
-   *Activity Log* \(`---D----`\) - To delete activity logs.

For more information, see [Privileges and Permissions](privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](standard-roles-delivered-with-sap-datasphere-a50a51d.md). 

</td>
</tr>
</table>



<a name="loio2d8b7d04dcae402f911d119437ce0a74__section_transport"/>

## Transport Tool Privileges

The following privileges are required to use the tools inside <span class="FPA-icons-V3"></span> \(*Transport*\).


<table>
<tr>
<th valign="top">

Tool/Object/Task

</th>
<th valign="top">

Privileges

</th>
</tr>
<tr>
<td valign="top">

Packages

See [Creating Packages to Export](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/24aba84ceeb3416881736f70f02e3a0a.html "Users with space administrator privileges can create packages to model groups of related objects for transport between tenants. Modelers can add objects to packages via the Package field, which appears in editors when a package is created in their space. Once a package is complete and validated, the space administrator can export it to the Content Network. The structure of your package is preserved and, as the objects it contains evolve, you can easily export updated versions of it.") :arrow_upper_right:

</td>
<td valign="top">

To create packages, you must have a combination of a global role and a scoped role:

-   A global role that grants you the following privileges:
    -   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
    -   *Lifecycle* \(`-R---MS-`\) - To use the *Transport* apps.

-   A scoped role that grants you access to a space with the following privileges:
    -   *Spaces* \(`-RU-----`\) - To update your spaces and their properties.
    -   *Space Files* \(`CRUD----`\) - To create, read, update, and delete objects in your spaces.
    -   *Data Warehouse Data Builder* \(`-RU-----`\) - To view and update *Data Builder* objects \(and any other relevant object privileges to allow you to update other types of objects contained in the package\).


The *DW Space Administrator* role template, for example, grants this combination of privileges. For more information, see [Privileges and Permissions](privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](standard-roles-delivered-with-sap-datasphere-a50a51d.md). 

</td>
</tr>
<tr>
<td valign="top">

Export

See [Exporting Content for Sharing with Other Tenants](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/44e775c3b7d24d2483caaf02c598bc21.html "You can use the Transport app to export content from one or more spaces for sharing with other tenants.") :arrow_upper_right:

</td>
<td valign="top">

To export content from a space via the *Export* app, you must have either:


<table>
<tr>
<td valign="top">

A global role that allows you to access and export content from any space, by granting you the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Lifecycle* \(`-R---MS-`\) - To use the *Transport* apps.
-   *Spaces* \(`-------M`\) - To update all spaces and space properties.
-   *Space Files* \(`-------M`\) - To create, read, update, and delete all objects in all spaces.

The *DW Administrator* role, for example, grants these privileges.

</td>
<td valign="top">

A combination of a global role and a scoped role:

-   A global role that grants you the following privileges:
    -   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
    -   *Lifecycle* \(`-R---MS-`\) - To use the *Transport* apps.

-   A scoped role that grants you access to the space or spaces to export from with the following privileges:
    -   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
    -   *Data Warehouse Data Builder* \(`-R------`\) - To view Data Builder objects \(and any other relevant object privileges to allow you to create and update other types of objects contained in the package\).
    -   *Spaces Files* \(`-R------`\) - To view specific spaces and their contents.


The *DW Space Administrator* role template, for example, grants this combination of privileges.

</td>
</tr>
</table>

The *DW Space Administrator* role template, for example, grants this combination of privileges. For more information, see [Privileges and Permissions](privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](standard-roles-delivered-with-sap-datasphere-a50a51d.md). 

</td>
</tr>
<tr>
<td valign="top">

Import

See [Importing Content from Another Tenant](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/b607a12931d74c4a93506ea64c55ab4e.html "You can use the Transport app to import content that has been shared from another tenant.") :arrow_upper_right:

</td>
<td valign="top">

To import content into a space via the *Import* app, you must have either:


<table>
<tr>
<td valign="top">

A global role that allows you to update any space and to create new spaces if necessary, by granting you the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Lifecycle* \(`-R---MS-`\) - To use the *Transport* apps.
-   *Spaces* \(`-------M`\) - To update all spaces and space properties.
-   *Spaces* \(`C-------`\) - To create spaces.
-   *Space Files* \(`-------M`\) - To create, read, update, and delete all objects in all spaces.

The *DW Administrator* role, for example, grants these privileges.

</td>
<td valign="top">

A combination of a global role and a scoped role:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   A global role that grants you the following privileges:
    -   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
    -   *Lifecycle* \(`-R---MS-`\) - To use the *Transport* apps.

-   A scoped role that grants you access to the space or spaces to import into with the following privileges:
    -   *Data Warehouse Data Builder* \(`CRUD--S-`\) - To create, read, update, delete and share data builder objects \(and any other relevant object privileges to allow you to create and update other types of objects contained in the package\).
    -   *Spaces* \(`--U-----`\) - To update your spaces and their properties.
    -   *Space Files* \(`CRUD----`\) - To create, read, update, and delete objects in your spaces.


The *DW Space Administrator* role template, for example, grants this combination of privileges.

</td>
</tr>
</table>

For more information, see [Privileges and Permissions](privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](standard-roles-delivered-with-sap-datasphere-a50a51d.md). 

</td>
</tr>
<tr>
<td valign="top">

Monitor

See [Monitoring Transport Jobs](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/fa9015ccf050412ba1c67e9ede012a21.html "You can search through and review the history of transport jobs in the Monitor app.") :arrow_upper_right:

</td>
<td valign="top">

To monitor transport jobs in the *Monitor* app, you must have a global role that grants you the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Lifecycle* \(`-R---MS-`\) - To use the *Transport* apps.

The *DW Space Administrator* role template, for example, grants this combination of privileges. For more information, see [Privileges and Permissions](privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](standard-roles-delivered-with-sap-datasphere-a50a51d.md). 

</td>
</tr>
</table>



<a name="loio2d8b7d04dcae402f911d119437ce0a74__section_system_monitor"/>

## System Monitor Tool Privileges

The following privileges are required to use the tools inside <span class="FPA-icons-V3"></span> \(*System Monitor*\).


<table>
<tr>
<th valign="top">

Tool/Object/Task

</th>
<th valign="top">

Privileges

</th>
</tr>
<tr>
<td valign="top">

System monitor and capacities

See [Monitoring SAP Datasphere in the System Monitor](../Monitoring-SAP-Datasphere/monitoring-sap-datasphere-in-the-system-monitor-28910cd.md)

</td>
<td valign="top">

To monitor SAP Datasphere in the *System Monitor*, you must have a global role that grants you the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *System Information* \(`-RU-----`\) - To access the *System Monitor* tool.

The *DW Administrator* role template, for example, grants these privileges. For more information, see [Privileges and Permissions](privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](standard-roles-delivered-with-sap-datasphere-a50a51d.md). 

</td>
</tr>
</table>



<a name="loio2d8b7d04dcae402f911d119437ce0a74__section_data_sharing_cockpit"/>

## Data Sharing Cockpit Tool Privileges

The following privileges are required to use the tools inside <span class="SAP-icons-V5"></span> \(*Data Sharing Cockpit*\).


<table>
<tr>
<th valign="top">

Tool/Object/Task

</th>
<th valign="top">

Privileges

</th>
</tr>
<tr>
<td valign="top">

Data sharing cockpit

See [Data Sharing Cockpit - Data Provider's Guide](https://help.sap.com/viewer/e4059f908d16406492956e5dbcf142dc/cloud/en-US/e479b7b4c95741c7a7a1d42397984c7e.html "Users with a modeler role can create a data provider profile and publish data products to the Catalog & Marketplace.") :arrow_upper_right:

</td>
<td valign="top">

To use the features in the *Data Sharing Cockpit* area, you must have a scoped role that grants you access to a space with the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Data Warehouse Data Builder* \(`CRU-----`\) - To create and edit *Data Builder* objects.
-   *Spaces* \(`-RU-----`\) - To create a new data provider profile, or edit an existing one.



</td>
</tr>
</table>



## System Tool Privileges

The following privileges are required to use the tools inside <span class="FPA-icons-V3"></span> \(*System*\).


<table>
<tr>
<th valign="top">

Tool/Object/Task

</th>
<th valign="top">

Privileges

</th>
</tr>
<tr>
<td valign="top">

Configuration

</td>
<td valign="top">

To work in the *Configuration* area in the *System* tool, you must have a global role that grants you the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *System Information* \(`-RU-----`\) - To access the *Configuration* area in the *System* tool.

In order to create live data connections of type tunnel, you must, in addition, have a global role that grants you the following privileges:

-   *Connection* \(`CRUD-M--`\) - To create, read, update, and delete live data connections of type *Tunnel*.
-   *Other Data Sources* \(`----E---`\) - To access the *Manage Live Data Connections* dialog.

The *DW Administrator* global role, for example, grants these privileges. For more information, see [Privileges and Permissions](privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](standard-roles-delivered-with-sap-datasphere-a50a51d.md). 

</td>
</tr>
<tr>
<td valign="top">

Administration

</td>
<td valign="top">

To work in the *Administration* area in the *System* tool, you must have a global role that grants you the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *System Information* \(`-RU-----`\) - To access the *System* tool.
-   *User* \(`-R------`\) - To access the *Administration* area in the *System* tool.

The *DW Administrator* global role, for example, grants these privileges. For more information, see [Privileges and Permissions](privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](standard-roles-delivered-with-sap-datasphere-a50a51d.md). 

</td>
</tr>
<tr>
<td valign="top">

About

</td>
<td valign="top">

To access the *About* area, you must have either a scoped or global role that grants you the following privilege:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.

To work with your SAP HANA database, you must have a global role that grants you the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *System Information* \(`-RU-----`\) - To access *More* in the *About* area of the *System* tool.

The *DW Administrator* global role, for example, grants these privileges. For more information, see [Privileges and Permissions](privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](standard-roles-delivered-with-sap-datasphere-a50a51d.md).

</td>
</tr>
</table>

See [Administering SAP Datasphere](../administering-sap-datasphere-70ee87c.md).



<a name="loio2d8b7d04dcae402f911d119437ce0a74__section_external_data_consumption"/>

## External Data Consumption

To consume data exposed by SAP Datasphere in clients, tools and apps, you must have a scoped role that grants you access to a space with the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Space Files* \(`-R------`\) - To view objects in your space.

See [Consuming Data Exposed by SAP Datasphere](https://help.sap.com/viewer/43509d67b8b84e66a30851e832f66911/cloud/en-US/d7d56284bb5148c887ac4054689bfbca.html "All users with any of the standard roles can consume data exposed by spaces they are assigned to. If a user does not need to access SAP Datasphere itself, and only wants to consume data exposed by it, they should be granted a consumer role.") :arrow_upper_right:.



<a name="loio2d8b7d04dcae402f911d119437ce0a74__section_cli"/>

## The Command Line Interface

For information about privileges needed to work with the "datasphere" command line interface, see [Accessing SAP Datasphere via the Command Line](https://help.sap.com/docs/SAP_DATASPHERE/d0ecd6f297ac40249072a44df0549c1a/3f9a42ccde6b4b6aba121e2aab79c36d.html?state=DRAFT&version=DEV).

