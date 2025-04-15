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

-   If you create a custom role for space-related purposes, you should include only scoped privileges and permissions. As a second step, you need to create a scoped role based on this custom role to assign users and spaces to the set of privileges included. See [Create a Scoped Role to Assign Privileges to Users in Spaces](create-a-scoped-role-to-assign-privileges-to-users-in-spaces-b5c4e0b.md).


You should not mix global and scoped privileges in a custom role.

-   If you include a scoped privilege in a custom role that you create for global purposes, the privilege is ignored.

-   If you include a global privilege in a custom role that you want to use as a template for a scoped role, the privilege is ignored .


> ### Note:  
> Some users, such as space administrators, primarily need scoped permissions to work with spaces, but they also need some global permissions \(such as Lifecycle when transporting content packages\). To provide such users with the full set of permissions they need, you can include both the relevant global privileges and scoped privileges in the custom role you will use as a template for the scoped role. Each space administrator is then assigned to the scoped role to receive the necessary scoped privileges, but they are also assigned directly to the custom role in order to receive the additional global privileges.

For more details about global and scoped privileges, see [Privileges and Permissions](privileges-and-permissions-d7350c6.md).



## Procedure

1.  Go to <span class="FPA-icons-V3"></span> \(*Expand*\)** \> **<span class="FPA-icons-V3"></span> \(*Security*\)** \> **<span class="FPA-icons-V3"></span> \(*Roles*\).

2.  To create a custom role, click <span class="FPA-icons-V3"></span> \(Add Role\) and select *Create a Custom Role*.

3.  In the *Create a New Role* dialog, complete the following properties:


    <table>
    <tr>
    <th valign="top">

    Property
    
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
    
    Enter a unique name for the role. The name can only contain upper and lower case letters, numbers, and underscores and its maximum length is 20 characters.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Description
    
    </td>
    <td valign="top">
    
    \[optional\] Enter a description, which can be changed at any time. The description can only contain upper and lower case letters, numbers, spaces, and dashes and its maximum length is 155 characters.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    License Type
    
    </td>
    <td valign="top">
    
    Select SAP Datasphere.
    
    </td>
    </tr>
    </table>
    
4.  Click *Create*.

5.  Select a role template.

    The role templates are the predefined standard roles associated with the SAP Datasphere license type. If you wish to create a role without extending a predefined standard role, choose the blank template. After you select a template, a page opens showing you the individual permissions assigned to the privileges that have been defined for the role template you chose.

6.  Select the permissions for your new role for every privilege type. The permission privileges represent an area, app, or tool in SAP Datasphere while the permissions \(create, read, update, delete, execute, maintain, share, and manage\) represent the actions a user can perform.For more details about global and scoped privileges, see [Privileges and Permissions](privileges-and-permissions-d7350c6.md).

7.  \[optional\] If you want to change the role template that your new custom role will be based on, select <span class="FPA-icons-V3"></span> \(*Select Template*\), and choose a role.

8.  \[optional\] To define the custom role as a default role, which will be assigned to all new users when no other role is assigned to them, select :gear:\(*Role Configuration*\) and select the option *Use as Default Role*.

    > ### Note:  
    > The option *Enable Self-Service* is not relevant for SAP Datasphere.

9.  Save your new custom role.

    > ### Note:  
    > You can assign the role to a user from the *Users* page or - only if you've created a custom role for global purposes \(and not for space-related purposes\) - from the *Roles* page. Whether you create users first or roles first does not matter. See [Assign Users to a Role](assign-users-to-a-role-57a7880.md).


