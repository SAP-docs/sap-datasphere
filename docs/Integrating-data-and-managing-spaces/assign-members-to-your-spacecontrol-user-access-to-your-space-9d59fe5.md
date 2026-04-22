<!-- loio9d59fe511ae644d98384897443054c16 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Assign Members to Your SpaceControl User Access to Your Space

As a Space Administrator, you can assign users as members of your space.You can assign users to your space and manage them.

This topic contains the following sections:

-   [Prerequisites](assign-members-to-your-spacecontrol-user-access-to-your-space-9d59fe5.md#loio9d59fe511ae644d98384897443054c16__section_j1n_kz3_42c)
-   [Introduction to Space User Access](assign-members-to-your-spacecontrol-user-access-to-your-space-9d59fe5.md#loio9d59fe511ae644d98384897443054c16__section_sj4_drj_byb)
-   [Access the Users Area in Your Space](assign-members-to-your-spacecontrol-user-access-to-your-space-9d59fe5.md#loio9d59fe511ae644d98384897443054c16__section_wt4_p2t_2yb)
-   [Assign Users to Your Space](assign-members-to-your-spacecontrol-user-access-to-your-space-9d59fe5.md#loio9d59fe511ae644d98384897443054c16__section_hf2_srj_byb)
-   [Change Privileges for a User in Your Space](assign-members-to-your-spacecontrol-user-access-to-your-space-9d59fe5.md#loio9d59fe511ae644d98384897443054c16__section_sk1_wrj_byb)
-   [Unassign Users from Your Space](assign-members-to-your-spacecontrol-user-access-to-your-space-9d59fe5.md#loio9d59fe511ae644d98384897443054c16__section_sbt_wrj_byb)



<a name="loio9d59fe511ae644d98384897443054c16__section_j1n_kz3_42c"/>

## Prerequisites

To assign users to your space and manage them from the *Users* area in your space details page, you must have a scoped role that grants you access to a space with the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Spaces* \(`-RU-----`\) - To open and update your space in the *Space Management* tool.
-   *Space Files* \(`-R------`\) - To view objects in your space.
-   *Scoped Role User Assignment* \(`-------M`\) - To manage the users who can access your space.

The *DW Space Administrator* role template, for example, grants these privileges. For more information, see [Privileges and Permissions](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/d7350c6823a14733a7a5727bad8371aa.html "A privilege represents a task or an area in SAP Datasphere and can be assigned to a specific role. The actions that can be performed in the area are determined by the permissions assigned to a privilege.") :arrow_upper_right: and [Standard Application RolesStandard Roles Delivered with SAP Datasphere](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/a50a51d80d5746c9b805a2aacbb7e4ee.html "SAP Datasphere is delivered with several standard roles. A standard role includes a predefined set of privileges and permissions.") :arrow_upper_right:. 



<a name="loio9d59fe511ae644d98384897443054c16__section_sj4_drj_byb"/>

## Introduction to Space User Access

If a user with an administrator role has assigned you to a space with space administration privileges via a scoped role, you can assign and manage users in your space. For more information about how a DW Administrator assigns users to roles in particular spaces via scoped roles, see [Create a Scoped Role to Assign Privileges to Users in Spaces](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/b5c4e0b6c462414783ebbfc053815521.html "A scoped role inherits a set of scoped privileges from a standard or custom role and grants these privileges to users for use in the assigned spaces.") :arrow_upper_right:.

In this example, based on scoped roles that the DW Administrator has created, users are assigned to spaces with scoped roles as follows:


<table>
<tr>
<th valign="top">

Spaces

</th>
<th valign="top">

Users - Scoped Roles

</th>
</tr>
<tr>
<td valign="top">

Sales US

</td>
<td valign="top">

Sally - Sales Modeler

Bob - Sales Modeler

Joan - Sales Spaces Admin

</td>
</tr>
<tr>
<td valign="top">

Sales Europe

</td>
<td valign="top">

Sally - Sales Modeler

Bob - Sales Modeler

Jim - Senior Sales Modeler

</td>
</tr>
<tr>
<td valign="top">

Sales Asia

</td>
<td valign="top">

Joan - Sales Spaces Admin

</td>
</tr>
</table>

Joan has the role of space administrator for the spaces Sales US and Sales Asia. She can change the user assignment. She can assign any user to her 2 spaces with the scoped roles to which her spaces are assigned: Sales Modeler and Sales Spaces Admin.

She does the following changes in the Sales US space:

-   As Bob no longer needs to work in the space Sales US, Joan unassigns Bob from the space.

-   As Jim needs to work in space Sales US with the modeling privileges, Joan assigns Jim to the space with the Sales Modeler scoped role.


She does the following change in the Sales Asia space:

-   As Bob then needs to manage the space Sales Asia, Joan assigns Bob to the space with the Sales Space Admin scoped role.


With Joan's changes, users are now assigned to spaces with scoped roles as follows:


<table>
<tr>
<th valign="top">

Spaces

</th>
<th valign="top">

Users - Scoped Roles

</th>
</tr>
<tr>
<td valign="top">

Sales US

</td>
<td valign="top">

Sally - Sales Modeler

Jim - Sales Modeler

Joan - Sales Spaces Admin

</td>
</tr>
<tr>
<td valign="top">

Sales Europe

</td>
<td valign="top">

Sally - Sales Modeler

Bob - Sales Modeler

Jim - Senior Sales Modeler

</td>
</tr>
<tr>
<td valign="top">

Sales Asia

</td>
<td valign="top">

Joan - Sales Spaces Admin

Bob - Sales Spaces Admin

</td>
</tr>
</table>



<a name="loio9d59fe511ae644d98384897443054c16__section_wt4_p2t_2yb"/>

## Access the Users Area in Your Space

In the side navigation area, click ![](Integrating-Data-Via-Database-Users/Open-SQL-Schema/images/Space_Management_a868247.png) \(*Space Management*\), locate your space tile, and click *Edit* to open it.

In the *Users* area of the space page, you can see and edit which users are assigned to your space with which scoped roles. You can assign users to your space among all the users in the tenant, with one or more scoped roles to which your space is assigned.

> ### Note:  
> -   *Space Administrator* column - A green tick appears for each user who has space administration privileges for the space, which includes having the privilege \(permission\) *Scoped Role User Assignment* \(Manage\).
> 
> -   *Scoped Role* column - The one or more scoped roles that are assigned with each user to the space are displayed. Only a DW Administrator can click a scoped role, which opens the scoped role page.

All user assignment changes you do in the *Users* area of your space page are reflected in the scoped roles to which your space is assigned.



<a name="loio9d59fe511ae644d98384897443054c16__section_hf2_srj_byb"/>

## Assign Users to Your Space

You can add a user who will have certain privileges in your space by selecting the user and one or more scoped roles.

1.  Click *Add*. All the users created for the tenant are displayed in the dialog that opens.

2.  Select one or more users and click *Next*. All scoped roles to which your space is assigned are displayed.

3.  Select one or more scoped roles and click *Create*.


If a user is logged on to the tenant while you're adding it to the space, they will need to log out and log in again to the tenant in order to access the space.



<a name="loio9d59fe511ae644d98384897443054c16__section_sk1_wrj_byb"/>

## Change Privileges for a User in Your Space

You can change the privileges that the user has in your space by assigning it to another scoped role. A user can be assigned to one or more scoped roles in a space.

1.  Select a user and click *Edit*. All scoped roles to which your space is assigned are displayed.

2.  Select one or more scoped roles and click *Select*.




<a name="loio9d59fe511ae644d98384897443054c16__section_sbt_wrj_byb"/>

## Unassign Users from Your Space

You can unassign a user from your space. The user will be unassigned from the space in the one or more scoped roles which gave access to the space.

1.  Select a user and click *Remove*.

2.  In the confirmation dialog, click *Remove*.




You can also use the SAP Datasphere command line interface to assign users to a space. For more information, see [Manage Spaces and Space Access via the Command Line](https://help.sap.com/viewer/d0ecd6f297ac40249072a44df0549c1a/cloud/en-US/5eac5b71e2d34c32b63f3d8d47a0b1d0.html "Users with an administrator role can use the datasphere command line interface to create, read, update, and delete spaces. Users with a space administrator role can update some space properties, add (or remove) users, database users and HDI containers, and delete spaces.") :arrow_upper_right:.



**Prerequisites**

-   A user with the Administrator role has assigned you as a member of the space.

-   The users that you want to add as members of the space have been created in <span style="font-size:16px;"><span class="FPA-icons-V3"></span></span> *Security* → <span style="font-size:16px;"><span class="FPA-icons-V3"></span></span> *Users*.


**Procedure**

1.  In the side navigation area, click ![](Integrating-Data-Via-Database-Users/Open-SQL-Schema/images/Space_Management_a868247.png) \(*Space Management*\), locate your space tile, and click *Edit* to open it.

2.  In the *Members* section, click *Add*.

3.  Choose the members from the list of SAP Datasphere users and click *Add*.

    Depending on the roles that the users have, they are able to do different actions in the space:

    -   Roles providing privileges to work in SAP Datasphere spaces:
        -   **DW Space Administrator** - Can manage all aspects of a space \(except the *Space Storage* and *Workload Management* properties\) and can create data access controls and use the *Content Network*.
        -   **DW Space Administrator** \(template\) - Can manage all aspects of the spaces users are assigned to \(except the *Space Storage* and *Workload Management* properties\) and can create data access controls.
            -   *DW Scoped Space Administrator* - This predefined scoped role is based on the DW Space Administrator role and inherits its privileges and permissions.

                > ### Note:  
                > Users who are space administrators primarily need scoped permissions to work with spaces, but they also need some global permissions \(such as Lifecycle when transporting content packages\). To provide such users with the full set of permissions they need, they must be assigned to a scoped role \(such as the *DW Scoped Space Administrator*\) to receive the necessary scoped privileges, but they also need to be assigned directly to the *DW Space Administrator* role \(or a custom role that is based on the *DW Space Administrator* role\) in order to receive the additional global privileges.


        -   *DW Integrator* - Can integrate data via connections and can manage and monitor data integration in spaces of which they are a member.
        -   *DW Integrator* \(template\) - Can integrate data via connections and can manage and monitor data integration in a space.
            -   *DW Scoped Integrator* - This predefined scoped role is based on the DW Integrator role and inherits its privileges and permissions.


        -   **DW Modeler** - Can create and edit objects in the *Data Builder* and *Business Builder* and view data in all objects in spaces of which they are a member.
        -   **DW Modeler** \(template\) - Can create and edit objects in the *Data Builder* and *Business Builder* and view data in objects.
            -   *DW Scoped Modeler* - This predefined scoped role is based on the DW Modeler role and inherits its privileges and permissions.


        -   **DW Viewer** - Can view objects in spaces of which they are a member and view data output by views that are exposed for consumption in these spaces.
        -   **DW Viewer** \(template\) - Can view objects and view data output by views that are exposed for consumption in spaces.
            -   *DW Scoped Viewer* - This predefined scoped role is based on the DW Viewer role and inherits its privileges and permissions.



    -   Roles providing privileges to consume the data exposed by SAP Datasphere spaces:
        -   **DW Consumer** - Can consume data exposed by SAP Datasphere spaces of which they are members using SAP Analytics Cloud, and other clients, tools, and apps, but cannot log into SAP Datasphere. This role is intended for business analysts and other users who use SAP Datasphere data to drive their visualizations, but who have no need to access the modeling environment.
        -   **DW Consumer** \(template\) - Can consume data exposed by SAP Datasphere spaces, using SAP Analytics Cloud, and other clients, tools, and apps. Users with this role cannot log into SAP Datasphere. It is intended for business analysts and other users who use SAP Datasphere data to drive their visualizations, but who have no need to access the modeling environment.
            -   *DW Scoped Consumer* - This predefined scoped role is based on the DW Consumer role and inherits its privileges and permissions.





The users you've added as members of the space are dislayed in the table of the *Members* area.

You can also use the SAP Datasphere command line interface to assign members to a space. For more information, see [Manage Spaces and Space Access via the Command Line](https://help.sap.com/viewer/d0ecd6f297ac40249072a44df0549c1a/cloud/en-US/5eac5b71e2d34c32b63f3d8d47a0b1d0.html "Users with an administrator role can use the datasphere command line interface to create, read, update, and delete spaces. Users with a space administrator role can update some space properties, add (or remove) users, database users and HDI containers, and delete spaces.") :arrow_upper_right:.

