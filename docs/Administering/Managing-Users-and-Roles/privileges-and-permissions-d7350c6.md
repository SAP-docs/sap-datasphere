<!-- loiod7350c6823a14733a7a5727bad8371aa -->

# Privileges and Permissions

A privilege represents a task or an area in SAP Datasphere and can be assigned to a specific role. The actions that can be performed in the area are determined by the permissions assigned to a privilege.

This topic contains the following sections:

-   [Overview](privileges-and-permissions-d7350c6.md#loiod7350c6823a14733a7a5727bad8371aa__section_e1w_nn1_wkb)
-   [SAP Datasphere Privileges and Permissions](privileges-and-permissions-d7350c6.md#loiod7350c6823a14733a7a5727bad8371aa__section_qrv_ygt_xxb)
-   [Permissions](privileges-and-permissions-d7350c6.md#loiod7350c6823a14733a7a5727bad8371aa__permissions_list)



<a name="loiod7350c6823a14733a7a5727bad8371aa__section_e1w_nn1_wkb"/>

## Overview

A role represents the main tasks that a user performs in SAP Datasphere. Each role has a set of privileges with appropriate levels of permissions. The privileges represent areas of the application like the *Space Management* or the *Business Builder* and the files or objects created in those areas.

The standard application roles provide sets of privileges and permissions that are appropriate for that role. For example, the *DW Administrator* role has all the *Spaces* permissions, while the *DW Viewer* role has none.

You can use the standard application roles to assign sets of privileges and permissions to your users \(see [Standard Application Roles](standard-application-roles-a50a51d.md)\) and create your own custom roles to group together other sets of privileges and permissions \(see [Create a Custom Role](create-a-custom-role-862b88e.md)\).



<a name="loiod7350c6823a14733a7a5727bad8371aa__section_qrv_ygt_xxb"/>

## SAP Datasphere Privileges and Permissions

The following table lists the privileges and the permissions that can be set for each privilege.

> ### Note:  
> Some permissions require others and may automatically set them. For example, setting the *Delete* permission for the *Data Warehouse Data Builder* privilege automatically sets the *Read* permission as well.

**Permissions by Privileges**


<table>
<tr>
<th valign="top">

Privilege



</th>
<th valign="top">

Permissions



</th>
<th valign="top">

Description



</th>
</tr>
<tr>
<td valign="top">

*Spaces* 



</td>
<td valign="top">

`CRUD---M`



</td>
<td valign="top">

Allows access to spaces in the *Space Management* tool.

-   *Read* - To view the *Space Management*.
-   *Create*, *Update*, *Delete* - To create, update or delete spaces.

    To view certain space properties or perform actions on spaces, you need a combination of permissions for the privilege *Spaces* and for other privileges. See [Roles and Privileges by App and Feature](roles-and-privileges-by-app-and-feature-2d8b7d0.md).

-   *Manage* - To view all spaces, not only the spaces a user is assigned to.

    > ### Caution:  
    > The permission *Manage* should be granted only to tenant administrators.


See [Managing Your Space](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/268ea7e3e8d448deaab420219477064d.html "All data acquisition, preparation, and modeling happens inside spaces. A space is a secure area - space data cannot be accessed outside the space unless it is shared to another space or exposed for consumption.") :arrow_upper_right:



</td>
</tr>
<tr>
<td valign="top">

*Space Files* 



</td>
<td valign="top">

`CRUD---M`



</td>
<td valign="top">

Allows access to all objects inside a space, such as views and tables, for users who are assigned to the space.

-   *Read* - To view the objects in the spaces users are assigned to.

-   *Create*, *Update*, *Delete* - To create, update or delete objects in the spaces users are assigned to.

-   *Manage* - To see objects and data in all spaces, not only in the spaces users are assigned to.

    > ### Caution:  
    > The permission *Manage* should be granted only to tenant administrators.


See [Managing Your Space](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/268ea7e3e8d448deaab420219477064d.html "All data acquisition, preparation, and modeling happens inside spaces. A space is a secure area - space data cannot be accessed outside the space unless it is shared to another space or exposed for consumption.") :arrow_upper_right:



</td>
</tr>
<tr>
<td valign="top">

*Data Warehouse Data Builder* 



</td>
<td valign="top">

`CRUD--S-`



</td>
<td valign="top">

Allows access to all objects in the *Data Builder* app.

Users with the *Share* permission can share objects to other spaces.

Also allows access to the *Data Sharing Cockpit* app with the *Create*, *Read* and *Update* permissions.

See [Acquiring Data in the Data Builder](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/1f15a29a25354ec28392ab10ca4e9350.html "Users with the DW Modeler role can import data directly into the Data Builder from connections and other sources, use replication flows to replicate multiple objects, and data flows to extract, transform and load data.") :arrow_upper_right:, [Preparing Data in the Data Builder](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/f2e359c899fa4351b5f514d1d86ed9e2.html "Users with the DW Modeler role can use views and intelligent lookups in the Data Builder to combine, clean, and otherwise prepare data.") :arrow_upper_right: and [Modeling Data in the Data Builder](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/5c1e3d4a49554fcd8fcf199d664d1109.html "Users with the DW Modeler role can add semantic information to their entities and expose them directly to clients, tools, and apps, or combine, refine, and enrich them in tightly-focused analytic models for consumption in SAP Analytics Cloud.") :arrow_upper_right:



</td>
</tr>
<tr>
<td valign="top">

*Data Warehouse Remote Connection* 



</td>
<td valign="top">

`CRUD----`



</td>
<td valign="top">

Allows access to remote and run-time objects:

-   *Read* - To view remote tables in the *Data Builder*.

-   *Create*, *Read*, *Update* and *Delete* - To create, update, or delete a connection in the *Connections* app, and users have to be a member of the space with the corresponding *Space Files* permission.


See [Integrating Data via Connections](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/eb85e157ab654152bd68a8714036e463.html "Connections provide access to data from a wide range of sources, cloud as well as on-premise sources, SAP as well as Non-SAP sources, and partner tools. They allow space members to use objects from the connected source to acquire, prepare and access data from those sources in SAP Datasphere. To connect to different sources, SAP Datasphere provides different connection types.") :arrow_upper_right: and [Acquiring Data in the Data Builder](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/1f15a29a25354ec28392ab10ca4e9350.html "Users with the DW Modeler role can import data directly into the Data Builder from connections and other sources, use replication flows to replicate multiple objects, and data flows to extract, transform and load data.") :arrow_upper_right:



</td>
</tr>
<tr>
<td valign="top">

*Data Warehouse Cloud Data Integration* 



</td>
<td valign="top">

`-RU-E---`



</td>
<td valign="top">

Allows access to the *Data Integration Monitor* app:

-   *Read* - To view the *Data Integration Monitor*.
-   *Update*:
    -   To perform any one-off replication/persistency actions in the *Data Integration Monitor* or *Data Builder*.
    -   To redeploy views in the *Data Builder* where data persistency is used \(including in the view lineage\)

-   *Execute* - To work with schedules.

> ### Note:  
> In addition to these permissions, the following *Data Integration Monitor* actions require the DWC\_DATABUILDER privilege with *Read* permission:
> 
> -   To add a new view in the *View Persistency Monitor*.
> -   To set up or change partitioned data loading in the *Remote Table Monitor*.
> 
> See [Managing and Monitoring Data Integration](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/4cbf7c7fc64645bfa364332827557267.html "From  (Data Integration Monitor), you can run and monitor data replication for remote tables, monitor data flow and task chain runs, add and monitor persisted views, and track the queries sent to your remote connected source systems for your space.") :arrow_upper_right:



</td>
</tr>
<tr>
<td valign="top">

*Data Warehouse Business Catalog* 



</td>
<td valign="top">

`-R------`



</td>
<td valign="top">

Allows access to the *Repository Explorer* app. To see the contents the user also needs to be a member of the space and, therefore, requires *Read* on *Space Files*.

See [Repository Explorer](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/f8ce0b4a24fe473a962176c8aa3cad42.html "The Repository Explorer gives you access to all your SAP Datasphere objects. You can search and filter the list, open or act on existing objects, and create new objects.") :arrow_upper_right:



</td>
</tr>
<tr>
<td valign="top">

*Data Warehouse Cloud Data Access Control* 



</td>
<td valign="top">

`CRUD----`



</td>
<td valign="top">

Allows access to the *Data Access Control* app and objects.

-   *Update* - To see the *Data Access Control* app.

-   *Read* - To use a *Data Access Control* object to protect a view.

-   *Update* - To change a view, in addition to *Read*.


See [Securing Data with Data Access Controls](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/a032e51c730147c7a1fcac125b4cfe14.html "Data access controls allow you to apply row-level security to your objects. When a data access control is applied to a data layer view or a business layer object, any user viewing its data will see only the rows for which they are authorized, based on the specified criteria.") :arrow_upper_right:



</td>
</tr>
<tr>
<td valign="top">

*Data Warehouse Business Builder* 



</td>
<td valign="top">

`-R------`



</td>
<td valign="top">

Allows access to the *Business Builder* app.

See [Modeling Data in the Business Builder](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/3829d46c48a44f1e94915054bd76b7b9.html "Users with the DW Modeler role can use the Business Builder editors to combine, refine, and enrich Data Builder objects and expose lightweight, tightly-focused perspectives for consumption by SAP Analytics Cloud and other BI clients.") :arrow_upper_right:



</td>
</tr>
<tr>
<td valign="top">

*Data Warehouse Business Entity* 



</td>
<td valign="top">

`CRUD----`



</td>
<td valign="top">

Allows access to business objects \(dimensions and analytical datasets defined in the *Business Builder*.

See [Creating a Business Entity](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/c912cdc1537d4efbb24b08327ea68918.html "You use business entities to build your consumption model for analysis and reporting.") :arrow_upper_right:



</td>
</tr>
<tr>
<td valign="top">

*Data Warehouse Authorization Scenario* 



</td>
<td valign="top">

`CRUD----`



</td>
<td valign="top">

Allows access to authorization scenarios defined in the *Business Builder*. Authorization scenarios are modeling abstractions for *Data Access Controls*.

See [Authorization Scenario](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/46d8c42e1b1f421c9735a7cbc6fdba60.html "Authorization scenarios allow modelers to define which data is relevant to a user&apos;s context. They are made available through business entities and can be used in consumption models for specific use-cases.") :arrow_upper_right:



</td>
</tr>
<tr>
<td valign="top">

*Data Warehouse Fact Model* 



</td>
<td valign="top">

`CRUD----`



</td>
<td valign="top">

Allows access to fact models defined in the *Business Builder*. Fact models are shaped like consumption models but offer re-useability in other consumption models.

See [Creating a Fact Model](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/5bbd14a328b549b2b53fce830ea25c15.html "Fact models are reusable models you can use to streamline the creation of other models within the same business context.") :arrow_upper_right:



</td>
</tr>
<tr>
<td valign="top">

*Data Warehouse Consumption Model* 



</td>
<td valign="top">

`CRUD----`



</td>
<td valign="top">

Allows access to consumption models inside the *Business Builder*. Consumption models comprise perspectives which are presented as `DWC_CUBE` objects in the file repository.

See [Creating a Consumption Model](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/337fa99de4a44700ba49e2214a1f3349.html "Consumption models are the basis to consume your data.") :arrow_upper_right:



</td>
</tr>
<tr>
<td valign="top">

*Data Warehouse Folder* 



</td>
<td valign="top">

`CRUD----`



</td>
<td valign="top">

Allows access to folders defined in the *Business Builder*. Folders are used to organize objects inside the *Business Builder*.

See [Business Builder Start Page](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/90e63fd4857543469648dae5a71457f1.html "The Business Builder start page gives you access to the different editors.") :arrow_upper_right:



</td>
</tr>
<tr>
<td valign="top">

*Data Warehouse Consumption* 



</td>
<td valign="top">

`-RU-E---`



</td>
<td valign="top">

Allows access to data in modeling objects:

-   `R` \(*Read*\) - Read data output by *Data Builder* views that have the *Expose for Consumption* switch enabled and data in *Business Builder* fact models and consumption models.

    Users with this permission may not preview data in local or remote tables, in views that are not exposed for consumption, in sources or intermediate nodes of graphical views \(even if those views are exposed for consumption\), or in *Business Builder* business entities.

    This permission is given to users with the standard *DW Viewer* role \(who have read-only access to SAP Datasphere\) and users with the *DW Consumer* role \(who do not have access to SAP Datasphere and merely consume exposed data in SAP Analytics Cloud and other analytics clients\).

-   `U` \(*Update*\) - Upload data from a CSV file to a local table and delete data from a local table.
-   `E` \(*Execute*\) - Access data in all *Data Builder* and *Business Builder* objects and edit data in *Data Builder* local tables.

See [Consuming Data Exposed by SAP Datasphere](https://help.sap.com/viewer/43509d67b8b84e66a30851e832f66911/cloud/en-US/d7d56284bb5148c887ac4054689bfbca.html "All users of SAP Datasphere with any of the standard roles can consume data exposed by spaces of which they are a member. If a user does not need to access SAP Datasphere itself, and only wants to consume data exposed by it, they should be granted the DW Consumer role.") :arrow_upper_right:



</td>
</tr>
<tr>
<td valign="top">

*Data Warehouse General*



</td>
<td valign="top">

`-R------`



</td>
<td valign="top">

Allows users to log into SAP Datasphere. Included in all standard roles except for *DW Consumer*.



</td>
</tr>
<tr>
<td valign="top">

*Role*



</td>
<td valign="top">

`CRUD----`



</td>
<td valign="top">

Allows access to the *Roles* app.

See [Managing Roles and Privileges](managing-roles-and-privileges-3740dac.md)



</td>
</tr>
<tr>
<td valign="top">

*User*



</td>
<td valign="top">

`CRUD---M`



</td>
<td valign="top">

Allows access to lists of users.

-   `R` \(*Read*\) -

    -   To see the list of members in a space, in addition to privileges *Spaces* \(`-R------`\) and *Team* \(`-R------`\).

    -   To see a list of users in a dialog, for example when choosing which users to share a story with, or when choosing users to add to a team.


-   To open the *Security* \> *Users* tools, you need all 4 permissions `CRUD----`. If you have only the Read permission, you cannot see the list of users in *Security* \> *Users*.

    > ### Note:  
    > The permissions `CRUD----` are included in the DW Administrator role. When you create a custom role based on the DW Administrator role, the permissions are automatically included and you cannot edit them.

-   `M` \(*Manage*\) - To permit assigning users to roles, and approving role assignment requests from users.


See [Managing SAP Datasphere Users](managing-sap-datasphere-users-4fb82cb.md)



</td>
</tr>
<tr>
<td valign="top">

*Team*



</td>
<td valign="top">

`CRUD---M`



</td>
<td valign="top">

Allows to assign and remove users to/from a space.

See [Assign Members to Your Space](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/9d59fe511ae644d98384897443054c16.html "As a Space Administrator, you can assign users as members of your space.") :arrow_upper_right:



</td>
</tr>
<tr>
<td valign="top">

*Activity Log*



</td>
<td valign="top">

`-R-D----`



</td>
<td valign="top">

Allows access to the *Activites* area in the *Security* tool.

See [Monitor Object Changes with Activities](../Monitoring-SAP-Datasphere/monitor-object-changes-with-activities-08e607c.md)



</td>
</tr>
<tr>
<td valign="top">

*Lifecycle*



</td>
<td valign="top">

`-R---MS-`



</td>
<td valign="top">

Allows to import and export content via the *Content Network* and *Transport* tools.

-   `M` \(*Maintain*\) - Allows access to the tools *Content Network* and *Transport* \> *Import* so the user can import packages from the*Content Network*.
-   `M` \(*Maintain*\) and `S` \(*Share*\) - Allows access to the tool *Transport* \> *Export* so the user can export packages from *Transport* \> *Export* in the*Content Network*.


> ### Note:  
> The permissions `-R---MS-` are included in the DW Administrator role. When you create a custom role based on the DW Administrator role, the permissions are automatically included and you cannot edit them.

See [Importing SAP and Partner Business Content from the Content Network](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/400078d689bf4454b3fc977a4e201c2f.html "Users with the DW Administrator or DW Space Administrator role can import business content and sample content from SAP and partners from the Content Network.") :arrow_upper_right: and [Transporting Content Between Tenants](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/df12666cf98e41248ef2251c564b0166.html "Users with the Administrator or Space Administrator role can use the Transport app to transfer content between tenants via a private cloud storage area.") :arrow_upper_right:



</td>
</tr>
<tr>
<td valign="top">

*System Information*



</td>
<td valign="top">

`-RU-----`



</td>
<td valign="top">

-   *Read* - To access the *About* area in the *System* tool.

-   *Update* - To access the *Administration*, *Configuration* and *About* areas in the *System* tool.




</td>
</tr>
</table>



<a name="loiod7350c6823a14733a7a5727bad8371aa__permissions_list"/>

## Permissions

The following table displays the available permissions and their definitions.


<table>
<tr>
<th valign="top">

Permission



</th>
<th valign="top">

Description



</th>
</tr>
<tr>
<td valign="top">

Create



</td>
<td valign="top">

Permits creating new objects of this item type. Users need this permission to create spaces, views or tables, upload data into a story, or upload other local files.



</td>
</tr>
<tr>
<td valign="top">

Read



</td>
<td valign="top">

Permits opening and viewing an item and its content.



</td>
</tr>
<tr>
<td valign="top">

Update



</td>
<td valign="top">

Permits editing and updating existing items. Compare this permission with the *Maintain* permission, which doesn't allow changes to the data structure. Note: some object types need the *Maintain* permission to update data. See the Maintain entry.



</td>
</tr>
<tr>
<td valign="top">

Delete



</td>
<td valign="top">

Permits deletion of the item.



</td>
</tr>
<tr>
<td valign="top">

Execute



</td>
<td valign="top">

Permits executing the item to run a process, such as schedules.



</td>
</tr>
<tr>
<td valign="top">

Maintain



</td>
<td valign="top">

Permits the maintenance of data values, for example adding records to a model, without allowing changes to the actual data structure. Compare this permission with the Update permission, which does allow changes to the data structure.

When granted on the Lifecycle privilege, permits importing and exporting objects.



</td>
</tr>
<tr>
<td valign="top">

Share



</td>
<td valign="top">

Permits the sharing of the selected item type.



</td>
</tr>
<tr>
<td valign="top">

Manage



</td>
<td valign="top">

When granted on *Spaces* and *Space Files*, permits to view all spaces and their content \(including data\), regardless of whether the user is assigned to the space or not.

To perform actions on spaces, you need the *Manage* permission in combination with other permissions for *Spaces* and other privileges. See [Roles and Privileges by App and Feature](roles-and-privileges-by-app-and-feature-2d8b7d0.md).

> ### Caution:  
> This permission should be granted only to tenant administrators.



</td>
</tr>
</table>

