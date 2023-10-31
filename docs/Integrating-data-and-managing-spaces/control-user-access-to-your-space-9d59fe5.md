<!-- loio9d59fe511ae644d98384897443054c16 -->

# Control User Access to Your Space

You can assign users to your space and manage them.



If a DW Administrator has assigned you to a space as a DW Space Administrator via a scoped role, you can assign and manage users in your space. For more information about how a DW Administrator assigns users to roles in particular spaces via scoped roles, see [Create a Scoped Role to Assign Privileges to Users in Spaces](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/b5c4e0b6c462414783ebbfc053815521.html "A scoped role inherits a set of scoped privileges from a standard or custom role and grants these privileges to users for use in the assigned spaces.") :arrow_upper_right:.

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


> ### Restriction:  
> You cannot assign yourself to a scoped role. For this reason, you cannot add yourself to a space.



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




You can also use the SAP Datasphere command line interface, `dwc`, to assign users to a space. For more information, see [Manage Spaces via the Command Line](https://help.sap.com/viewer/9b8363ae47c347de9a027c0e5567a37a/DEV_CURRENT/en-US/5eac5b71e2d34c32b63f3d8d47a0b1d0.html "You can use the SAP Datasphere command line interface, datasphere, to create, read, update, and delete spaces. You can set space properties, assign (or remove) users, create database users, create or update objects (tables, views, and data access controls), and associate HDI containers to a space.") :arrow_upper_right:.

