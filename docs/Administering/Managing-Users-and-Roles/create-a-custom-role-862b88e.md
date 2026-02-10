<!-- loio862b88eed50244049d41361ba3290456 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Create a Custom Role

You can create a custom role, using either a blank template or a standard role template, choosing privileges and permissions as needed.

This topic contains the following sections:

-   [Context](create-a-custom-role-862b88e.md#loio862b88eed50244049d41361ba3290456__section_ct1_g1l_1gc)
-   [Create a Custom Role](create-a-custom-role-862b88e.md#loio862b88eed50244049d41361ba3290456__section_prc_t1l_1gd)
-   [Assign Users to a Custom Global Role](create-a-custom-role-862b88e.md#loio862b88eed50244049d41361ba3290456__section_gjy_4dl_1gc)
-   [Remove Users from a Role](create-a-custom-role-862b88e.md#loio862b88eed50244049d41361ba3290456__section_sv2_dgl_1gc)



<a name="loio862b88eed50244049d41361ba3290456__section_ct1_g1l_1gc"/>

## Context

You can create a custom role to enable users to do either global actions on the tenant or actions that are specific to spaces.

-   If you create a custom role for global purposes, you should include only global privileges and permissions. You can then assign the role to the relevant users.

-   If you create a custom role for space-related purposes, you should include only scoped privileges and permissions. As a second step, you need to create a scoped role based on this custom role to assign users and spaces to the set of privileges included. See [Create a Scoped Role to Assign Privileges to Users in Spaces](create-a-scoped-role-to-assign-privileges-to-users-in-spaces-b5c4e0b.md).


You should not mix global and scoped privileges in a custom role.

-   If you include a scoped privilege in a custom role that you create for global purposes, the privilege is ignored.

-   If you include a global privilege in a custom role that you want to use as a template for a scoped role, the privilege is ignored.


> ### Note:  
> Some users, such as space administrators, primarily need scoped permissions to work with spaces, but they also need some global permissions \(such as Lifecycle when transporting content packages\). To provide such users with the full set of permissions they need, you can include both the relevant global privileges and scoped privileges in the custom role you will use as a template for the scoped role. Each space administrator is then assigned to the scoped role to receive the necessary scoped privileges, but they are also assigned directly to the custom role in order to receive the additional global privileges.

For more details about global and scoped privileges, see [Privileges and Permissions](privileges-and-permissions-d7350c6.md).



<a name="loio862b88eed50244049d41361ba3290456__section_prc_t1l_1gd"/>

## Create a Custom Role

You can create a custom role to enable users to do either global actions on the tenant or actions that are specific to spaces.

-   If you create a custom role for global purposes, you should include only global privileges and permissions. You can then assign the role to the relevant users.

-   If you create a custom role for space-related purposes, you should include only scoped privileges and permissions. As a second step, you need to create a scoped role based on this custom role to assign users and spaces to the set of privileges included. See [Create a Scoped Role to Assign Privileges to Users in Spaces](create-a-scoped-role-to-assign-privileges-to-users-in-spaces-b5c4e0b.md).


1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(*Security*\) ** \> ** <span class="FPA-icons-V3"></span> \(*Roles*\).
2.  Click <span class="FPA-icons-V3"></span> \(Add Role\) and select *Create a Custom Role*.
3.  In the *Create a New Role* wizard, complete the following properties and click *Next Step*:


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
    
4.  In the *Role Template* step of the wizard, select the template you want to base your role on and click *Next Step*. You can also start with a blank template.

    The role templates are the predefined standard roles associated with the SAP Datasphere license type. If you wish to create a role without extending a predefined standard role, choose the blank template.

    The role page that opens displays the privileges and permissions that are included in the role template you chose.

5.  If needed, select the permissions for every privilege you want to include in the role, then click *Next Step* and *Save*.

    The privileges represent an area, app, or tool in SAP Datasphere while the permissions \(create, read, update, delete, execute, maintain, share, and manage\) represent the actions a user can perform. For more details about global and scoped privileges, see [Privileges and Permissions](privileges-and-permissions-d7350c6.md).

6.  \[optional\] If you want to change the role template that your new custom role will be based on, select <span class="FPA-icons-V3"></span> \(*Select Template*\), and choose a role.
7.  \[optional\] To define the custom role as a default role, which will be assigned to all new users when no other role is assigned to them, select :gear:\(*Role Configuration*\) and select the option *Use as Default Role*.

    > ### Note:  
    > The option *Enable Self-Service* is not relevant for SAP Datasphere.

8.  Save the new custom role.
    -   If you've included global privileges in the role, you can now assign users to the role.
    -   If you've created the custom role to be used as a template for a scoped role, see [Create a Scoped Role to Assign Privileges to Users in Spaces](create-a-scoped-role-to-assign-privileges-to-users-in-spaces-b5c4e0b.md).




<a name="loio862b88eed50244049d41361ba3290456__section_gjy_4dl_1gc"/>

## Assign Users to a Custom Global Role

If a custom role includes global privileges, you can assign users to the role as follows.

> ### Note:  
> Alternatively, you can assign users to a role from the *Users* page \(see [Create a User](create-a-user-58d4b24.md)\).

1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(*Security*\) ** \> ** <span class="FPA-icons-V3"></span> \(*Roles*\).
2.  Open the role to which you want to assign users and click *\[number of\] Users*.

    Alternatively, from the list of users, identify the role and can click the number in the *Users* column.

    The dialog *Select Users* opens.

3.  Select the users and click *Save*.



<a name="loio862b88eed50244049d41361ba3290456__section_sv2_dgl_1gc"/>

## Remove Users from a Role

1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(*Security*\) ** \> ** <span class="FPA-icons-V3"></span> \(*Roles*\).
2.  Open the role to which you want to assign users and click *\[number of\] Users*.

    Alternatively, from the list of users, identify the role and can click the number in the *Users* column.

    The dialog *Select Users* opens.

3.  In the *Selected Users* area of the dialog, click the cross icon for each user that you want to remove from the role, then click *Save*.

