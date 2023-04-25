<!-- loio2d8b7d04dcae402f911d119437ce0a74 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Roles and Privileges by App and Feature

Review the standard roles and the privileges needed to access apps, tools, and other features of SAP Datasphere.



<a name="loio2d8b7d04dcae402f911d119437ce0a74__apps"/>

## SAP Datasphere Apps

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



</td>
</tr>
<tr>
<td valign="top">

<span class="SAP-icons"></span> \(*Repository Explorer*\)

See [Repository Explorer](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/f8ce0b4a24fe473a962176c8aa3cad42.html "The Repository Explorer gives you access to all your SAP Datasphere objects. You can search and filter the list, open or act on existing objects, and create new objects.") :arrow_upper_right:



</td>
<td valign="top">

*Data Warehouse Business Catalog* \(-R------\)

 



</td>
<td valign="top">

All roles except *DW Consumer* 



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

-   *Data Warehouse Remote Connection* \(CRUD--S-

-   *Data Warehouse Cloud Data Integration* \(-RU-E---\)




</td>
<td valign="top">

 *DW Integrator* 



</td>
</tr>
<tr>
<td valign="top">

<span class="FPA-icons"></span> \(*Business Builder*\)

Start page

Dimension editor

Analytical dataset editor

Fact model editor

Consumption model editor

Authorization scenario editor

See [Modeling Data in the Business Builder](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/3829d46c48a44f1e94915054bd76b7b9.html "The business layer is the area where business users can define objects with a business approach.") :arrow_upper_right:



</td>
<td valign="top">

Each page or editor requires a separate permission:

-   Start page: *Data Warehouse Business Builder* \(-R------\)
-   Dimension editor: *Data Warehouse Business Entity* \(CRUD----\)
-   Analytical dataset editor: *Data Warehouse Business Entity* \(CRUD----\)
-   Fact model editor: *Data Warehouse Fact Model* \(CRUD----\)
-   Consumption model editor: *Data Warehouse Consumption Model* \(CRUD----\)
-   Authorization scenario editor: *Data Warehouse Authorization Scenario* \(CRUD----\)

The following features need additional permissions \(which are included in the *DW Modeler* role\):

-   Preview data from any object in the *Data Preview* screen - *Data Warehouse Consumption.Execute*

    > ### Note:  
    > The *DW Viewer* role includes Data Warehouse Consumption.Read, which allows these users to preview only data from Fact models and consumption models.




</td>
<td valign="top">

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

See [Acquiring and Preparing Data in the Data Builder](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/1f15a29a25354ec28392ab10ca4e9350.html "Users with the DW Modeler role can import data directly into the Data Builder from connections and other sources or use data flows to extract, transform and load data. They can then use views and intelligent lookups in the Data Builder to combine, clean, and otherwise prepare data.") :arrow_upper_right: and [Modeling Data in the Data Builder](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/5c1e3d4a49554fcd8fcf199d664d1109.html "Users with the DW Modeler role can add semantic information to their entities and expose them directly or combine, refine, and enrich them in tightly-focused analytic models for consumption in SAP Analytics Cloud and other BI clients.") :arrow_upper_right:



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
> The *DW Modeler* role includes *Data Warehouse Cloud Data Integration.Update*, which allows them to do only manual integration tasks. The *DW Integrator* role includes *Data Warehouse Data Access Control.Execute*, which also allows scheduling automated integration tasks.



</td>
<td valign="top">

*DW Integrator*

*DW Modeler* \(manual tasks only\)



</td>
</tr>
<tr>
<td valign="top">

<span class="FPA-icons"></span> \(*Connections*\)

See [Integrating Data via Connections](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/eb85e157ab654152bd68a8714036e463.html "Connections provide access to data from a wide range of sources, cloud as well as on-premise sources, SAP as well as Non-SAP sources, and partner tools. They allow space members to use objects from the connected source to acquire, prepare and access data from those sources in SAP Datasphere. To connect to different sources, SAP Datasphere provides different connection types.") :arrow_upper_right:



</td>
<td valign="top">

 *Data Warehouse Remote Connection* \(CRUD--S-\)



</td>
<td valign="top">

*DW Integrator*

*DW Modeler* \(read-only access\)



</td>
</tr>
</table>

> ### Note:  
> -   In addition to the roles and privileges listed, users who have roles other than *DW Administrator* must also be members of one or more spaces in order to use these apps \(see [Assign Members to Your Space](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/9d59fe511ae644d98384897443054c16.html "As a Space Administrator, you can assign users as members of your space.") :arrow_upper_right:\).
> -   Users with the role *DW Administrator* or *DW Space Administrator* have full access \(with full CRUD permissions\) to all the apps listed in this table.
> -   Users with the *DW Viewer* role have read-only access to all the apps \(except for *Data Access Control*\) listed in this table.
> -   For complete lists of roles, privileges, and permissions, see:
>     -   [Standard Application Roles](standard-application-roles-a50a51d.md)
>     -   [Privileges and Permissions](privileges-and-permissions-d7350c6.md)



<a name="loio2d8b7d04dcae402f911d119437ce0a74__tools"/>

## SAP Datasphere Administration Tools

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

See [Preparing Your Space and Integrating Data](https://help.sap.com/viewer/d4f3c5a0bb074d09ae9b42b2b9bd7a08/cloud/en-US/8cb00503395049029055bb7aceafc080.html "Users with the DW Space Administrator or DW Integrator role can create connections to source systems and databases and use other methods to bring data into their space. They can schedule and monitor data replication and other data integration tasks. Space administrators are responsible for maintaining the list of space members and monitoring and managing the space. They can create data access controls to secure data, and can transport content between tenants.") :arrow_upper_right:



</td>
<td valign="top">

*Spaces* \(CRUD---M\)



</td>
<td valign="top">

*DW Administrator* \(full access, including creating spaces\)

*DW Space Administrator*

> ### Note:  
> -   Users with other roles can view \(but not edit\) the spaces they are members of.
> 
> -   Users with the *DW Integrator* role can create database users.



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

See [Transporting Content Between Tenants](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/df12666cf98e41248ef2251c564b0166.html "Users with the Administrator or Space Administrator role can use the Transport app to transfer content between tenants via a private cloud storage area.") :arrow_upper_right:



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

See [Data Marketplace - Data Provider&apos;s Guide](https://help.sap.com/viewer/e4059f908d16406492956e5dbcf142dc/cloud/en-US/e479b7b4c95741c7a7a1d42397984c7e.html "Start with Data Marketplace as a data provider.") :arrow_upper_right:



</td>
<td valign="top">

*Data Warehouse Data Builder* \(CRU-----\)



</td>
<td valign="top">

*DW Modeler*



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



<a name="loio2d8b7d04dcae402f911d119437ce0a74__section_skj_h4h_y5b"/>

## External Consumption of SAP Datasphere Data

Users can consume data exposed by SAP Datasphere if they are a member of a space and have the Space Files.Read permission, which is included in all standard application roles.


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

See [Consuming Data Exposed by SAP Datasphere](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/d7d56284bb5148c887ac4054689bfbca.html "All users of SAP Datasphere with any of the standard roles can consume data exposed by spaces of which they are a member. If a user does not need to access SAP Datasphere itself, and only wants to consume data exposed by it, they should be granted the DW Consumer role.") :arrow_upper_right:



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



<a name="loio2d8b7d04dcae402f911d119437ce0a74__cli"/>

## The Command Line Interface

To use the command line interface \(see [Create, Read, Update, and Delete Spaces via the Command Line](../Creating-Spaces-and-Allocating-Storage/create-read-update-and-delete-spaces-via-the-command-line-5eac5b7.md)\), a user must have the following standard application role or a custom role containing the listed privileges:


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

Update Space \(members, database users, HDI containers, entity definitions\)



</td>
<td valign="top">

*Spaces* \(-RUD---M\)

*Team* \(-RUD---M\)

*Data Builder* \(CRUD----\)



</td>
<td valign="top">

*DW Space Administrator*

> ### Note:  
> You must also be a member of the space.



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
> You must also be a member of the space.



</td>
</tr>
</table>

