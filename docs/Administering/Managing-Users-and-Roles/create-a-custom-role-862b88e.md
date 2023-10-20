<!-- loio862b88eed50244049d41361ba3290456 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Create a Custom Role

You can create a custom role using either a blank template or a standard role template and choosing privileges and permissions as needed. 



<a name="loio862b88eed50244049d41361ba3290456__prereq_yst_nqr_vnb"/>

## Prerequisites

To create a custom role, you need the DW Administrator role.



## Context

You can create a custom role to enable users to do either global actions on the tenant or actions that are specific to spaces.

-   If you create a custom role for global purposes, you should include only global privileges and permissions. You can then assign the role to the relevant users.

-   If you create a custom role for space-related purposes, you should include only scoped privileges and permissions. As a second step, you will need to create a scoped role based on this custom role to assign users and spaces to the set of privileges included. See [Create a Scoped Role to Assign Privileges to Users in Spaces](create-a-scoped-role-to-assign-privileges-to-users-in-spaces-b5c4e0b.md).


You should not mix global and scoped privileges in a custom role.

-   If you include a scoped privilege in a custom role that you create for global purposes, the privilege will be ignored.

-   If you include a global privilege in a custom role that you want to use as a template for a scoped role, the privilege will be ignored.


> ### Note:  
> Some users, such as space administrators, primarily need scoped permissions to work with spaces, but they also need some global permissions \(such as Lifecycle when transporting content packages\). To provide such users with the full set of permissions they need, you can include both the relevant global privileges and scoped privileges in the custom role you will use as a template for the scoped role. Each space administrator is then assigned to the scoped role to receive the necessary scoped privileges, but they are also assigned directly to the custom role in order to receive the additional global privileges.

For more details about global and scoped privileges, see [Privileges and Permissions](privileges-and-permissions-d7350c6.md).

> ### Caution:  
> Scoped roles and all related features will be rolled out to all tenants over the course of a number of versions. For more details, see SAP Note [3380409](https://launchpad.support.sap.com/#/notes/3380409).



## Procedure

1.  Go to <span class="FPA-icons"></span> \(*Expand*\)** \> **<span class="FPA-icons"></span> \(*Security*\)** \> **<span class="FPA-icons"></span> \(*Roles*\).

2.  To create a custom role, click <span class="FPA-icons"></span> \(Add Role\) and select *Create a Custom Role*.

3.  Enter a unique name for the role and select the license type SAP Datasphere.

4.  Select *Create*.

5.  Select a role template.

    The role templates are the predefined standard roles associated with the SAP Datasphere license type. If you wish to create a role without extending a predefined standard role, choose the blank template. After you select a template, a page opens showing you the individual permissions assigned to the privileges that have been defined for the role template you chose.

    > ### Note:  
    > Currently, it is not possible to add *Catalog* access to a custom role as a template. Assign either the *Catalog Administrator* or *Catalog User* standard application roles instead.

6.  Select the permissions for your new role for every privilege type. The permission privileges represent an area, app or tool in SAP Datasphere while the permissions \(create, read, update, delete, execute, maintain, share and manage\) represent the actions a user can perform.For more details about global and scoped privileges, see [Privileges and Permissions](privileges-and-permissions-d7350c6.md).

7.  If you want to change the role template that your new custom role will be based on, select <span class="FPA-icons"></span> \(*Select Template*\), and choose a role.

8.  Save your new custom role.

    > ### Note:  
    > You can assign the role to a user from the *Users* page or - only if you've created a custom role for global purposes \(and not for space-related purposes\) - from the *Roles* page. Whether you create users first or roles first does not matter. See [Assign Users to a Role](assign-users-to-a-role-57a7880.md).


