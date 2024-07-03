<!-- loio6f7c6dfa3cb249debb749c729025bae0 -->

# Automated Conversion to Scoped Roles

For SAP Datasphere tenants that were created before version 2023.21, the roles and user assignment to spaces have been converted so that users can continue to perform the same actions as before in their spaces.

This topic contains the following sections:

-   [Introduction to Automated Conversion to Scoped Roles](automated-conversion-to-scoped-roles-6f7c6df.md#loio6f7c6dfa3cb249debb749c729025bae0__section_bd2_xc4_fyb)
-   [Converted Roles](automated-conversion-to-scoped-roles-6f7c6df.md#loio6f7c6dfa3cb249debb749c729025bae0__section_wmx_hmn_fyb)
-   [Example of a Converted Scoped Role](automated-conversion-to-scoped-roles-6f7c6df.md#loio6f7c6dfa3cb249debb749c729025bae0__section_fx4_1mn_fyb)
-   [Adapting Converted Scoped Roles](automated-conversion-to-scoped-roles-6f7c6df.md#loio6f7c6dfa3cb249debb749c729025bae0__section_zxd_cnw_dzb)



<a name="loio6f7c6dfa3cb249debb749c729025bae0__section_bd2_xc4_fyb"/>

## Introduction to Automated Conversion to Scoped Roles

The way a DW Administrator gives privileges to users to do certain actions in spaces has changed.

![](images/SDP_ObjectModel_1ImageBeforeAfter_dc61358.png)


<table>
<tr>
<th valign="top">

Before Conversion

</th>
<th valign="top">

After Conversion

</th>
</tr>
<tr>
<td valign="top">

A DW Administrator assigned a role to a user and assigned the user as a member of a space.

As a consequence:

-   A user had the same one or more roles in all the spaces he was a member of.

-   A DW Administrator assigned users space by space by going in each space page.




</td>
<td valign="top">

A DW Administrator assigns a role to one or more users and one or more spaces within a new role: a scoped role.

As a consequence:

-   A user can have different roles in different spaces: be a modeler in space Sales Germany and Sales France and a viewer in space Europe Sales.

-   A DW Administrator can give a role to many users in many spaces, all in one place in a scoped role. See [Create a Scoped Role to Assign Privileges to Users in Spaces](create-a-scoped-role-to-assign-privileges-to-users-in-spaces-b5c4e0b.md).

    A DW Space Administrator can then manage users in their spaces and the changes are reflected in the scoped roles. See [Control User Access to Your Space](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/9d59fe511ae644d98384897443054c16.html "You can assign users to your space and manage them.") :arrow_upper_right:.




</td>
</tr>
</table>



<a name="loio6f7c6dfa3cb249debb749c729025bae0__section_wmx_hmn_fyb"/>

## Converted Roles

You can now use global roles for tenant-wide actions and scoped roles for space-related actions.

![](images/SDPGraph_ScopedRoles_MigrationRoles1ImageBeforeAfter_caa41cb.png)

The *Roles* page lists the same standard and custom roles as before the conversion, and in addition the scoped roles that have been automatically created.

-   DW Administrator, Catalog Administrator and Catalog User: these standard roles are considered as global roles. They now include only privileges that are global, which means privileges that apply to the tenant and are not space-related. For example, the DW Administrator role no more grants access to any of the modeling apps of SAP Datasphere \(such as Data Builder\).

    Users who previously had these roles are still assigned to them after conversion.

    Users who previously had the DW Administrator role and were members of certain spaces are assigned to the new DW Scoped Space Administrator role for those spaces they previously had access to.

    The user who previously had the System Owner role and was member of certain spaces is assigned to the new DW Scoped Space Administrator role for those spaces the user previously had access to.

-   A single scoped role is created for each standard role \(outside of DW Administrator, Catalog Administrator and Catalog User\) and each custom role and all the users who previously had that standard or custom role are assigned to the new scoped role but only for those spaces they previously had access to.

    > ### Note:  
    > All the spaces of the tenant are included in each scoped role created, but not all users are assigned to all spaces. See the example of scoped role below.

    For each standard or custom role, two roles are available after the conversion: the initial standard or custom role \(which acts as a template for the scoped role\) and the scoped role created.

    Each scoped role includes privileges which are now considered as scoped privileges.

-   Users who previously had the DW Space Administrator role are assigned to these 2 roles: the standard role DW Space Administrator and the new scoped role DW Scoped Space Administrator. Users who manage spaces primarily need scoped permissions to work with spaces, but they also need some global permissions \(such as Lifecycle when transporting content packages\). To provide such users with the full set of permissions they need, each space administrator is assigned to the scoped role DW Scoped Space Administrator to receive the necessary scoped privileges, and they are also assigned directly to the DW Space Administrator role in order to receive the additional global privileges.


> ### Note:  
> -   Specific case - no role assigned to a user: Before conversion, a DW Administrator assigned a user to certain spaces but did not assign a role to the user. As no role was assigned to the user, the user-to-spaces assignment is not kept after conversion.
> 
> -   Privileges and permissions are now either global or scoped. See [Privileges and Permissions](privileges-and-permissions-d7350c6.md).



<a name="loio6f7c6dfa3cb249debb749c729025bae0__section_fx4_1mn_fyb"/>

## Example of a Converted Scoped Role

In this example, users assigned to a custom role called « Senior Modeler » were members of certain spaces before the conversion, as shown below.

![](images/SDPGraph_ScopedRoles_MigrationExample1ImageBeforeAfter_a8222ed.png)

The custom role « Senior Modeler » has been converted to the scoped role « Custom Scoped Senior Modeler » and the users who previously had that custom role « Senior Modeler » are assigned to the scoped role but only for the spaces they previously had access to.



<a name="loio6f7c6dfa3cb249debb749c729025bae0__section_zxd_cnw_dzb"/>

## Adapting Converted Scoped Roles

The scoped roles that are automatically created during the conversion ensure that users can continue to perform the same actions as before the conversion. However, we recommend that you do not use the automatically created scoped roles and that you create your own scoped roles by logical groups as soon as possible.

In this example, the following scoped roles have been automatically created during conversion:

-   DW Scoped Space Administrator

-   DW Scoped Modeler

-   DW Scoped Viewer

-   DW Scoped Consumer


There are 4 spaces: Sales US, Sales Europe, Finance US and Finance Europe, which can be logically organized in one Sales group and one Finance group.

You should create a set of scoped roles for each logical group of spaces, add the relevant spaces and the relevant users and assign the users to the spaces in the scoped roles. The users will have access to the spaces with the appropriate privileges.


<table>
<tr>
<th valign="top">

 

</th>
<th valign="top">

Sales Spaces

</th>
<th valign="top">

Finance Spaces

</th>
</tr>
<tr>
<td valign="top">

Scoped Roles

</td>
<td valign="top">

-   DW Sales Space Administrator

-   DW Sales Modeler

-   DW Sales Viewer

-   DW Sales Consumer




</td>
<td valign="top">

-   DW Finance Space Administrator

-   DW Finance Modeler

-   DW Finance Viewer

-   DW Finance Consumer




</td>
</tr>
<tr>
<td valign="top">

Spaces

</td>
<td valign="top">

-   Sales US

-   Sales Europe




</td>
<td valign="top">

-   Finance US

-   Finance Europe




</td>
</tr>
</table>

For more information about creating a scoped role, see [Create a Scoped Role to Assign Privileges to Users in Spaces](create-a-scoped-role-to-assign-privileges-to-users-in-spaces-b5c4e0b.md).

> ### Note:  
> In addition to the standard workflows, you can also create scoped roles and assign scopes and users to them via the command line \(see [Manage Scoped Roles via the Command Line](https://help.sap.com/viewer/9b8363ae47c347de9a027c0e5567a37a/DEV_CURRENT/en-US/85085a35a58a4589bc121fb94efc4876.html "Users with a DW Administrator role (or with equivalent privileges) can create, read, update, and delete scoped roles via the command line.") :arrow_upper_right:\).

