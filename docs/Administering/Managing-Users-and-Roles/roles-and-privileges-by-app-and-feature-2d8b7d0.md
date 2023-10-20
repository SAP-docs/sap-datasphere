<!-- loio2d8b7d04dcae402f911d119437ce0a74 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Roles and Privileges by App and Feature

Review the standard roles and the privileges needed to access apps, tools, and other features of SAP Datasphere.

This topic contains the following sections:

-   [Apps](roles-and-privileges-by-app-and-feature-2d8b7d0.md#loio2d8b7d04dcae402f911d119437ce0a74__section_apps)
-   [Administration Tools](roles-and-privileges-by-app-and-feature-2d8b7d0.md#loio2d8b7d04dcae402f911d119437ce0a74__section_tools)
-   [Space Management Privileges and Permissions](roles-and-privileges-by-app-and-feature-2d8b7d0.md#loio2d8b7d04dcae402f911d119437ce0a74__section_space_management_permissions_SDP_ON)
-   [External Data Consumption](roles-and-privileges-by-app-and-feature-2d8b7d0.md#loio2d8b7d04dcae402f911d119437ce0a74__section_external_consumption)
-   [The Command Line Interface](roles-and-privileges-by-app-and-feature-2d8b7d0.md#loio2d8b7d04dcae402f911d119437ce0a74__section_cli)

> ### Note:  
> For complete lists of standard roles, privileges, and permissions, see:
> 
> -   [Standard Roles Delivered with SAP Datasphere](standard-roles-delivered-with-sap-datasphere-a50a51d.md)
> -   [Privileges and Permissions](privileges-and-permissions-d7350c6.md)



<a name="loio2d8b7d04dcae402f911d119437ce0a74__section_apps"/>

## Apps

To access an app, tool, or editor, a user must have the following standard application role or a custom role containing the listed privileges:


<table>
<tr>
<th valign="top">

App



</th>
<th valign="top">

Requires Privileges \(Permissions\)…



</th>
<th valign="top">

Contained in Standard Role...



</th>
</tr>
<tr>
<td valign="top">

<span class="FPA-icons"></span> \(*Home*\) 



</td>
<td valign="top">

*Data Warehouse General* \(-R------\)



</td>
<td valign="top">

All roles except *DW Consumer*

*DW Viewer* \(read-only access\)



</td>
</tr>
<tr>
<td valign="top">

<span class="SAP-icons"></span> \(*Repository Explorer*\)

See [Repository Explorer](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/f8ce0b4a24fe473a962176c8aa3cad42.html "The Repository Explorer gives you access to all your SAP Datasphere objects. You can search and filter the list, open or act on existing objects, and create new objects.") :arrow_upper_right:



</td>
<td valign="top">

*Space Files* \(-R------\)



</td>
<td valign="top">

All roles except *DW Consumer*

*DW Viewer* \(read-only access\)



</td>
</tr>
<tr>
<td valign="top">

<span class="SAP-icons"></span>\(*Catalog*\)

See [Governing and Publishing Catalog Assets](https://help.sap.com/viewer/aca3ccb4b2f84eb8b6154e8fd2812c0e/cloud/en-US/de29b96a9438439682715a93212ae4f4.html "The SAP Datasphere catalog is the central place to discover, enrich, classify, and publish high-quality, trusted data and analytic assets from across your enterprise.") :arrow_upper_right:



</td>
<td valign="top">

Currently, it is not possible to add *Catalog* access to a custom role using privileges. Assign one of the standard application roles instead.



</td>
<td valign="top">

*Catalog Administrator*

*Catalog User* \(read-only access\)

In addition, the following sub-tools require the *Catalog Administrator* role:

-   Tag Hierarchies
-   Monitoring



</td>
</tr>
<tr>
<td valign="top">

:convenience_store: \(*Data Marketplace*\)

See [Purchasing Data from Data Marketplace](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/4096fb8c97dd4d84a7200941c1721368.html "Enrich your own data with third-party data products.") :arrow_upper_right:



</td>
<td valign="top">

-   *Spaces* \(-R------\)

-   *Space Files* \(CRUD----\)

-   *Data Warehouse Remote Connection* \(CRUD--S-\)

-   *Data Warehouse Cloud Data Integration* \(-RU-E---\)

-   *Data Warehouse Data Builder* \(CRU-----\)



</td>
<td valign="top">

*DW Integrator*

*DW Modeler*

*DW Administrator*, *DW Space Administrator* and *DW Viewer* : read-only access



</td>
</tr>
<tr>
<td valign="top">

<span class="FPA-icons"></span> \(*Business Builder*\)

Start page

Dimension editor

Fact editor

Fact model editor

Consumption model editor

Authorization scenario editor

See [Modeling Data in the Business Builder](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/3829d46c48a44f1e94915054bd76b7b9.html "Users with the DW Modeler role can use the Business Builder editors to combine, refine, and enrich Data Builder objects and expose lightweight, tightly-focused perspectives for consumption by SAP Analytics Cloud and other BI clients.") :arrow_upper_right:



</td>
<td valign="top">

Each page or editor requires a separate permission:

-   Start page: *Data Warehouse Business Builder* \(-R------\)
-   Dimension editor: *Data Warehouse Business Entity* \(CRUD----\)
-   Fact editor: *Data Warehouse Business Entity* \(CRUD----\)
-   Fact model editor: *Data Warehouse Fact Model* \(CRUD----\)
-   Consumption model editor: *Data Warehouse Consumption Model* \(CRUD----\)
-   Authorization scenario editor: *Data Warehouse Authorization Scenario* \(CRUD----\)

The following features need additional permissions \(which are included in the *DW Modeler* role\):

-   Preview data from any object in the *Data Preview* screen - *Data Warehouse Consumption.Execute*

    > ### Note:  
    > The *DW Viewer* role includes Data Warehouse Consumption.Read, which allows these users to preview only data from Fact models and consumption models.




</td>
<td valign="top">

*DW Space Administrator*

*DW Modeler*

*DW Viewer* \(read-only access\)



</td>
</tr>
<tr>
<td valign="top">

![](images/Data_Builder_f73dc45.png) \(*Data Builder*\) 

Start Page

Table editor

Graphical view editor

SQL view editor

Entity-relationship model editor

Data flow editor

Intelligent lookup editor

Task chain editor

See [Acquiring Data in the Data Builder](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/1f15a29a25354ec28392ab10ca4e9350.html "Users with the DW Modeler role can import data directly into the Data Builder from connections and other sources, and use flows to replicate, extract, transform and load data.") :arrow_upper_right: and [Modeling Data in the Data Builder](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/5c1e3d4a49554fcd8fcf199d664d1109.html "Users with the DW Modeler role can add semantic information to their entities and expose them directly to clients, tools, and apps, or combine, refine, and enrich them in tightly-focused analytic models for consumption in SAP Analytics Cloud.") :arrow_upper_right:



</td>
<td valign="top">

All pages and editors share a single permission:

-   *Data Warehouse Data Builder* \(CRUD--S-\)

The following features need additional permissions \(which are included in the *DW Modeler* role\):

-   Preview data from any object in the *Data Preview* panel - *Data Warehouse Consumption.Execute*

    > ### Note:  
    > The *DW Viewer* role includes *Data Warehouse Consumption.Read*, which allows these users to preview only data output by views with the *Expose for Consumption* switch enabled.

-   Upload and delete data in a local table - *Data Warehouse Consumption.Update* 
-   Access the local table *Data Editor* screen - *Data Warehouse Data Builder.Update*
-   See remote objects in *Data Builder* editors - *Data Warehouse Remote Connection.Read*

The following features need additional permissions \(which are included in the *DW Integrator* role\):

-   Run an intelligent lookup - *Data Warehouse Data Integration.Update*
-   Run a task chain - *Data Warehouse Data Integration.Update*



</td>
<td valign="top">

*DW Space Administrator*

*DW Modeler*

*DW Viewer* \(read-only access\)



</td>
</tr>
<tr>
<td valign="top">

<span class="SAP-icons"></span> \(*Data Access Controls*\)

See [Securing Data with Data Access Controls](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/a032e51c730147c7a1fcac125b4cfe14.html "Data access controls allow you to apply row-level security to your objects. When a data access control is applied to a data layer view or a business layer object, any user viewing its data will see only the rows for which they are authorized, based on the specified criteria.") :arrow_upper_right:



</td>
<td valign="top">

*Data Warehouse Data Access Control* \(CRUD----\)

> ### Note:  
> The *DW Modeler* role includes *Data Warehouse Data Access Control.Read*, which allows them to apply an existing data access control to a *Data Builder* view.



</td>
<td valign="top">

*DW Space Administrator* 



</td>
</tr>
<tr>
<td valign="top">

<span class="FPA-icons"></span> \(*Data Integration Monitor*\)

See [Managing and Monitoring Data Integration](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/4cbf7c7fc64645bfa364332827557267.html "From  (Data Integration Monitor), you can run and monitor data replication for remote tables, monitor data flow and task chain runs, add and monitor persisted views, and track the queries sent to your remote connected source systems for your space.") :arrow_upper_right:



</td>
<td valign="top">

*Data Warehouse Data Integration* \(-RU-E---\)

> ### Note:  
> The *DW Modeler* role includes *Data Warehouse Cloud Data Integration.Update*, which allows them to do only manual integration tasks. The *DW Integrator* role includes *Data Warehouse Cloud Data Integration.Execute*, which also allows scheduling automated integration tasks.

The following features need additional permissions \(which are included in the *DW Space Administrator* role\):

-   View persistency ** \> ** Add a view - *Data Builder* *Read*
-   View persistency ** \> ** Define partitions - *Data Builder* *Read*
-   View persistency ** \> *View Analyzer* - *Data Builder* *Read*



</td>
<td valign="top">

*DW Space Administrator*

*DW Integrator*

*DW Modeler* \(manual tasks only\)

*DW Viewer* \(read-only access\)



</td>
</tr>
<tr>
<td valign="top">

<span class="FPA-icons"></span> \(*Connections*\)

See [Integrating Data via Connections](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/eb85e157ab654152bd68a8714036e463.html "Connections provide access to data from a wide range of sources, cloud as well as on-premise sources, SAP as well as Non-SAP sources, and partner tools. They allow users assigned to a space to use objects from the connected source to acquire, prepare and access data from those sources in SAP Datasphere. To connect to different sources, SAP Datasphere provides different connection types.") :arrow_upper_right:



</td>
<td valign="top">

*Data Warehouse Remote Connection* \(CRUD--S-\)

The following feature needs an additional permission \(which is included in the *DW Administrator* role\):

-   Select a location ID - *Connection.Read* 



</td>
<td valign="top">

*DW Space Administrator*

*DW Integrator*

*DW Modeler* \(read-only access\)

*DW Viewer* \(read-only access\)



</td>
</tr>
</table>



<a name="loio2d8b7d04dcae402f911d119437ce0a74__section_tools"/>

## Administration Tools

To access an administration tool, a user must have the following standard application role or a custom role containing the listed privileges:


<table>
<tr>
<th valign="top">

Tool



</th>
<th valign="top">

Requires Privileges \(Permissions\)…



</th>
<th valign="top">

Contained in Standard Role...



</th>
</tr>
<tr>
<td valign="top">

![](../images/Space_Management_a868247.png) \(*Space Management*\)

See [Preparing Your Space and Integrating Data](https://help.sap.com/viewer/d4f3c5a0bb074d09ae9b42b2b9bd7a08/cloud/en-US/8cb00503395049029055bb7aceafc080.html "Users with the DW Space Administrator or DW Integrator role can create connections to source systems and databases and can schedule and monitor data replication and other data integration tasks. Space administrators use other methods to integrate data into their space and are responsible for maintaining the list of space users and monitoring and managing the space. They can create data access controls to secure data, and can transport content between tenants.") :arrow_upper_right:



</td>
<td valign="top">

*Spaces* \(CRUD---M\)

> ### Note:  
> For detailed information on permissions for *Spaces*, see [Space Management Privileges and Permissions](roles-and-privileges-by-app-and-feature-2d8b7d0.md#loio2d8b7d04dcae402f911d119437ce0a74__section_space_management_permissions_SDP_ON)



</td>
<td valign="top">

*DW Administrator* \(can create spaces\)

*DW Space Administrator*

*DW Integrator* and *DW Modeler*: have read-only access to the page for their space \(though they cannot see all its properties\).



</td>
</tr>
<tr>
<td valign="top">

<span class="FPA-icons"></span> \(*System Monitor*\)

See [Monitoring SAP Datasphere](../Monitoring-SAP-Datasphere/monitoring-sap-datasphere-28910cd.md)



</td>
<td valign="top">

*System Information* \(-RU-----\)



</td>
<td valign="top">

*DW Administrator*



</td>
</tr>
<tr>
<td valign="top">

<span class="FPA-icons"></span> \(*Content Network*\)

See [Importing SAP and Partner Business Content from the Content Network](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/400078d689bf4454b3fc977a4e201c2f.html "Users with the DW Administrator or DW Space Administrator role can import business content and sample content from SAP and partners from the Content Network.") :arrow_upper_right:



</td>
<td valign="top">

*Lifecycle* \(-R---MS-\)



</td>
<td valign="top">

*DW Administrator*

*DW Space Administrator*



</td>
</tr>
<tr>
<td valign="top">

<span class="FPA-icons"></span> \(*Security*\)

Users \(see [Managing SAP Datasphere Users](managing-sap-datasphere-users-4fb82cb.md)\)

Roles \(see [Managing Roles and Privileges](managing-roles-and-privileges-3740dac.md)\)

Activities \(see [Monitor Object Changes with Activities](../Monitoring-SAP-Datasphere/monitor-object-changes-with-activities-08e607c.md)\)



</td>
<td valign="top">

Each sub-tool requires a separate permission:

-   Users: *User* \(CRUD---M\)
-   Roles: *Role* \(CRUD----\)
-   Activities: *Activity Log* \(-R-D----\)



</td>
<td valign="top">

*DW Administrator* \(full access\)



</td>
</tr>
<tr>
<td valign="top">

<span class="FPA-icons"></span> \(*Transport*\)

See [Transporting Content Between Tenants](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/df12666cf98e41248ef2251c564b0166.html "Users with the DW Administrator or DW Space Administrator role can use the Transport app to transfer content between tenants via a private cloud storage area.") :arrow_upper_right:



</td>
<td valign="top">

*Lifecycle* \(-R---MS-\)



</td>
<td valign="top">

*DW Administrator* 

*DW Space Administrator* 



</td>
</tr>
<tr>
<td valign="top">

<span class="SAP-icons"></span> \(*Data Sharing Cockpit*\)

See [Data Marketplace - Data Provider's Guide](https://help.sap.com/viewer/e4059f908d16406492956e5dbcf142dc/cloud/en-US/e479b7b4c95741c7a7a1d42397984c7e.html "Start with Data Marketplace as a data provider.") :arrow_upper_right:



</td>
<td valign="top">

*Data Warehouse Data Builder* \(CRU-----\)

> ### Note:  
> To create a new data provider profile, or edit an existing one, you must have the **Spaces \(Update\)** privilege assigned to your role.
> 
> See [Maintaining your Data Provider Profile](https://help.sap.com/viewer/e4059f908d16406492956e5dbcf142dc/cloud/en-US/4d298f8654fe4a6c9b6a4399a9e14c77.html "Provide information as you would like to present it to consumers of Data Marketplace. Provide company and business contact information as well as general information about the data you offer.") :arrow_upper_right:.



</td>
<td valign="top">

*DW Modeler*

*DW Space Administrator*



</td>
</tr>
<tr>
<td valign="top">

<span class="FPA-icons"></span> \(*System*\)

Configuration

Administration

About

See [Administering SAP Datasphere](../administering-sap-datasphere-70ee87c.md)



</td>
<td valign="top">

*System Information* \(-RU-----\)

> ### Note:  
> -   The Read \(R\) permission gives access to the *About* dialog.
> 
> -   The Update \(U\) permission gives access to all areas.



</td>
<td valign="top">

*DW Administrator*

> ### Note:  
> Users with any role can view the *About* dialog.



</td>
</tr>
</table>



<a name="loio2d8b7d04dcae402f911d119437ce0a74__section_space_management_permissions_SDP_ON"/>

## Space Management Privileges and Permissions

Users with different roles have different levels of access to the *Space Management* tool:

-   A *DW Consumer* cannot log into SAP Datasphere.

-   A *DW Viewer* can log into SAP Datasphere, but has no *Spaces* permissions. They cannot see the *Space Management* tool.

-   A *DW Modeler* and a *DW Integrator* have *Spaces* `(-R------)` permission. They have read-only access to the page for their space \(though they cannot see all its properties\).

-   A *DW Space Administrator* has *Spaces* `(-RUD----)` permissions. They can see all the space properties, and edit those outside the *General Settings* and *Workload Management* sections.

-   A *DW Administrator* has *Spaces* `(CRUD---M)` permissions. They can create spaces and edit some space properties, including modifying the storage allocated and the space priority.


Various privileges and permissions are required to see and edit different parts of the *Space Management* tool:

> ### Note:  
> The global privilege *Spaces* `(-------M)` enables users to perform the following actions in all the spaces of the tenant: read, update and delete.


<table>
<tr>
<th valign="top">

Action



</th>
<th valign="top">

Requires Privilege \(Permission\)



</th>
<th valign="top">

Contained in Standard Role



</th>
</tr>
<tr>
<td valign="top">

Create a Space

See [Create a Space](../Creating-Spaces-and-Allocating-Storage/create-a-space-bbd41b8.md)



</td>
<td valign="top">

Global privileges *Spaces* `(C------M)` and *User* `(-R------)`.



</td>
<td valign="top">

DW Administrator



</td>
</tr>
<tr>
<td valign="top">

View Space Properties



</td>
<td valign="top">

Global privilege *Spaces* `(-------M)`

or scoped privilege *Spaces* `(-R------)`

> ### Note:  
> In addition, you also need the following permissions to view these properties:
> 
> -   *Users*: Global privileges *Role* `(-R------)` or scoped privileges *Scoped Role User Assignment* `(-------M)`
> 
> -   *Data Consumption* and *Database Users*: Global privilege *Spaces* `(-------M)` or scoped privilege *Spaces* `(-R------)`
> 
> -   *HDI Containers*:Scoped privileges *Spaces* `(-R------)` and *Remote Connection* `(-R------)`
> 
>     > ### Note:  
>     > A DW Administrator cannot see the *HDI Containers* area in a space.
> 
> -   *Time Data*: Scoped privileges *Spaces* `(-R------)` and *Data Builder* `(-R------)`
> 
>     > ### Note:  
>     > A DW Administrator cannot see the *Time Data* area in a space.
> 
> -   *Auditing*: Global privilege *Spaces* `(-------M)` or scoped privilege *Spaces* `(--R-----)`



</td>
<td valign="top">

DW Administrator and DW Space Administrator

> ### Note:  
> A user with the role DW Modeler or DW Integrator have read-only access to the page for their space but they cannot view all its properties.



</td>
</tr>
<tr>
<td valign="top">

Modify *General Settings* \(except for *Storage Assignment*\)

See [Create a Space](../Creating-Spaces-and-Allocating-Storage/create-a-space-bbd41b8.md)



</td>
<td valign="top">

Global privilege *Spaces* `(-------M)` 

or scoped privilege *Spaces* `(-RU-----)`



</td>
<td valign="top">

DW Administrator and DW Space Administrator



</td>
</tr>
<tr>
<td valign="top">

Modify *Storage Assignment*, *Data Lake Access*, *Workload Management*

See [Create a Space](../Creating-Spaces-and-Allocating-Storage/create-a-space-bbd41b8.md), [Allocate Storage to a Space](../Creating-Spaces-and-Allocating-Storage/allocate-storage-to-a-space-f414c3d.md) and [Set a Priority and Statement Limits for a Space](../Creating-Spaces-and-Allocating-Storage/set-a-priority-and-statement-limits-for-a-space-d66ac1e.md)



</td>
<td valign="top">

Global privilege *Spaces* `(-------M)`



</td>
<td valign="top">

DW Administrator



</td>
</tr>
<tr>
<td valign="top">

Modify *Users*



</td>
<td valign="top">

Global privileges *Spaces* `(-------M)` and *Role* `(-------M)` 

or scoped privileges *Spaces* `(--U-----)` and *Scoped Role User Assignment* `(-------M)`



</td>
<td valign="top">

DW Administrator and DW Space Administrator



</td>
</tr>
<tr>
<td valign="top">

Modify *Data Consumption* and *Database Users*

See [Create a Database User](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/798e3fd6707940c3bd2219b2d1ebaac2.html "Users with the DW Space Administrator role can create database users, granting them privileges to read from and/or write to an Open SQL schema with restricted access to the space schema.") :arrow_upper_right:



</td>
<td valign="top">

Global privilege *Spaces* `(-------M)`

or scoped privileges *Spaces* `(-RU-----)`



</td>
<td valign="top">

DW Administrator, DW Space Administrator

> ### Note:  
> A user with the DW Integrator role needs in addition the privilege *Spaces* `(--U-----)` to create database users.



</td>
</tr>
<tr>
<td valign="top">

Modify *HDI Containers*

See [Prepare Your HDI Project for Exchanging Data with Your Space](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/a94e1637db484a5c8ec2da83cfa75156.html "To allow your SAP Datasphere space to read from and, if appropriate, write to the HDI container, you must configure your HDI project to build on your SAP Datasphere tenant and define the appropriate roles.") :arrow_upper_right:



</td>
<td valign="top">

Scoped privileges *Spaces* `(--U-----)` and *Remote Connection* `(--U-----)`



</td>
<td valign="top">

DW Space Administrator

> ### Note:  
> A DW Administrator cannot access the *HDI Containers* area in a space.



</td>
</tr>
<tr>
<td valign="top">

Modify *Time Data*

See [Create Time Data and Dimensions](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/c5cfce4d22b04650b2fd6078762cdeb9.html "Create a time table and dimension views in your space to provide standardized time data for your analyses. The time table contains a record for each day in the specified period (by default from 1900 to 2050), and the dimension views allow you to work with this date data at a granularity of day, week, month, quarter, and year, and to drill down and up in hierarchies.") :arrow_upper_right:



</td>
<td valign="top">

To update time data: scoped privileges *Spaces* `(--U-----)` and *Data Builder* `(--U-----)`

To delete time data: scoped privileges *Spaces*`(--U-----)` and *Data Builder* `(---D----)`



</td>
<td valign="top">

DW Space Administrator

> ### Note:  
> A DW Administrator cannot access the *Time Data* area in a space.



</td>
</tr>
<tr>
<td valign="top">

Modify *Auditing*

See [Enable Audit Logging](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/266553976e1c4db9aaa28a75e2308b77.html "You can enable audit logs for your space so that read and change actions (policies) are recorded. Administrators can then analyze who did what and when in the database.") :arrow_upper_right:



</td>
<td valign="top">

Global privilege *Spaces* `(-------M)` or scoped privilege *Spaces* `(-RU-----)`



</td>
<td valign="top">

DW Administrator and DW Space Administrator



</td>
</tr>
<tr>
<td valign="top">

Monitor a Space

See [Monitor Your Space Storage Consumption](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/94fe6c13f6a340288cd50ee355566591.html "See the storage amount assigned to and used by your space.") :arrow_upper_right:



</td>
<td valign="top">

Scoped privilege *Spaces* `(-R------)`

> ### Note:  
> With *Spaces* `(-R-----M)`, a user with the DW Administrator role can monitor the tenant and space storage by seeing the bars about used/assigned disk/memory at the top of the *Space Management* tool \(see [Monitor Tenant and Space Storage](../Creating-Spaces-and-Allocating-Storage/monitor-tenant-and-space-storage-39b08d3.md)\).



</td>
<td valign="top">

DW Administrator, DW Space Administrator, DW Integrator and DW Modeler



</td>
</tr>
<tr>
<td valign="top">

Lock or Unlock a Space

See [Lock or Unlock Your Space](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/c05b6a6d06db427dbdd3041d61fd5840.html "If a space exceeds its assigned storage or if the audit logs enabled in the space consume too much disk storage, the space is automatically locked.") :arrow_upper_right:



</td>
<td valign="top">

Global privileges *Spaces* `(-------M)` 

or scoped privilege *Spaces* `(--U-----)`



</td>
<td valign="top">

DW Administrator and DW Space Administrator



</td>
</tr>
<tr>
<td valign="top">

Delete a Space

See [Delete Your Space](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/3eb19b96e6ba41dfbffd759c5c8370bb.html "Delete a space if you are sure that you no longer need any of its content or data.") :arrow_upper_right:



</td>
<td valign="top">

Global privileges *Spaces* `(-------M)` and *User* `(-------M)` 

or scoped privileges *Spaces* `(---D----)` and *Scoped Role User Assignement* `(-------M)`



</td>
<td valign="top">

DW Administrator and DW Space Administrator

> ### Note:  
> A user with a space administrator role can delete only the spaces they’re assigned via a scoped role.
> 
> A user with a tenant administrator role can delete any space as *Spaces* `(-------M)` is included in the role.



</td>
</tr>
</table>



<a name="loio2d8b7d04dcae402f911d119437ce0a74__section_external_consumption"/>

## External Data Consumption

Users can consume data exposed by SAP Datasphere if they are assigned to a space via a scoped role and have the Space Files.Read permission. 


<table>
<tr>
<th valign="top">

Action



</th>
<th valign="top">

Requires Privileges \(Permissions\)…



</th>
<th valign="top">

Contained in Standard Role...



</th>
</tr>
<tr>
<td valign="top">

Consume data in SAP Analytics Cloud, Microsoft Excel, and other clients, tools, and apps

See [Consuming Data Exposed by SAP Datasphere](https://help.sap.com/viewer/43509d67b8b84e66a30851e832f66911/cloud/en-US/d7d56284bb5148c887ac4054689bfbca.html "All users of SAP Datasphere with any of the standard roles can consume data exposed by spaces they are assigned to. If a user does not need to access SAP Datasphere itself, and only wants to consume data exposed by it, they should be granted the DW Consumer role.") :arrow_upper_right:



</td>
<td valign="top">

*Space Files* \(-R------\)



</td>
<td valign="top">

All roles

> ### Note:  
> If a user does not need to access SAP Datasphere itself, and only wants to consume data exposed by it, they should be granted the *DW Consumer* role.



</td>
</tr>
</table>



<a name="loio2d8b7d04dcae402f911d119437ce0a74__section_cli"/>

## The Command Line Interface

To use the command line interface \(see [Manage Spaces via the Command Line](https://help.sap.com/viewer/d0ecd6f297ac40249072a44df0549c1a/cloud/en-US/5eac5b71e2d34c32b63f3d8d47a0b1d0.html "You can use the SAP Datasphere command line interface, datasphere, to create, read, update, and delete spaces. You can set space properties, assign (or remove) users, create database users, create or update objects (tables, views, and data access controls), and associate HDI containers to a space.") :arrow_upper_right:\), a user must have the following standard application role or a custom role containing the listed privileges:


<table>
<tr>
<th valign="top">

Action



</th>
<th valign="top">

Requires Privileges \(Permissions\)…



</th>
<th valign="top">

Contained in Standard Role...



</th>
</tr>
<tr>
<td valign="top">

Create/Update Space \(all properties\)



</td>
<td valign="top">

*Spaces* \(CRUD---M\)

*Team* \(CRUD---M\)

*Data Builder* \(CRUD----\)



</td>
<td valign="top">

*DW Administrator*

> ### Note:  
> The *DW Administrator* is the only standard role that allows a user to create or assign storage to a space.



</td>
</tr>
<tr>
<td valign="top">

Update Space \(users, database users, HDI containers, entity definitions\)



</td>
<td valign="top">

*Spaces* \(-RUD---M\)

*Team* \(-RUD---M\)

*Data Builder* \(CRUD----\)



</td>
<td valign="top">

*DW Space Administrator*

> ### Note:  
> You must also be assigned to the space.



</td>
</tr>
<tr>
<td valign="top">

Update Space \(entity definitions only\)



</td>
<td valign="top">

*Spaces* \(-R------\)

*Team* \(-R------\)

*Data Builder* \(CRUD----\)



</td>
<td valign="top">

*DW Modeler*

> ### Note:  
> You must also be assigned to the space.



</td>
</tr>
</table>

