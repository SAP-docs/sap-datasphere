<!-- loio58d4b24f766c4879b71c33f8e8dd5da8 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Create a User

You can create individual users in SAP Datasphere and assign them to roles.



<a name="loio58d4b24f766c4879b71c33f8e8dd5da8__context_mgz_hjz_1fb"/>

## Context

You can select one or more roles while you're creating the user. Before getting started creating users, you might want to become familiar with the global roles and scoped roles. You can still assign roles after you've created the users.


<table>
<tr>
<th valign="top">

Type of Role

</th>
<th valign="top">

Description

</th>
<th valign="top">

More Information

</th>
</tr>
<tr>
<td valign="top">

Global Roles

</td>
<td valign="top">

A role that enables users assigned to it to perform actions that are not space-related, typically a role that enables them to administer the tenant. A standard or custom role is considered as global when it includes global privileges.

</td>
<td valign="top">

[Managing Roles and Privileges](managing-roles-and-privileges-3740dac.md) 

</td>
</tr>
<tr>
<td valign="top">

Scoped Roles

</td>
<td valign="top">

A role that inherits a set of scoped privileges from a standard or custom role and grants these privileges to users for use in the assigned spaces.

</td>
<td valign="top">

[Create a Scoped Role to Assign Privileges to Users in Spaces](create-a-scoped-role-to-assign-privileges-to-users-in-spaces-b5c4e0b.md)

</td>
</tr>
</table>

The method described here assumes that SAP Datasphere is using its default authentication provider. If you are using a custom SAML Identity Provider, you must provide slightly different information, depending upon how your SAML authentication is configured.



## Procedure

1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(*Security*\) ** \> ** <span class="FPA-icons-V3"></span> \(*Users*\).

2.  Click :heavy_plus_sign:.

    The *Create User* wizard opens.

3.  In the *User Information* step, enter the following information and then click *Next Step*:


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
    
    User ID
    
    </td>
    <td valign="top">
    
    Each user needs a unique ID. Once the user account is created their ID can’t be modified. Only upper-case letters \(A-Z\), numbers \(0-9\), and underscores are allowed. The maximum length is 20 characters.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Email
    
    </td>
    <td valign="top">
    
    User’s email. A welcome email with logon information is sent to the email address.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    First Name
    
    </td>
    <td valign="top">
    
    \[Optional\] First name of the user.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Last Name
    
    </td>
    <td valign="top">
    
    Last name of the user.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Display Name
    
    </td>
    <td valign="top">
    
    \[Optional\] The display name appears on the screens.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Manager
    
    </td>
    <td valign="top">
    
    Not used in SAP Datasphere.
    
    </td>
    </tr>
    </table>
    
4.  In the *Role Assignment* step, select one or more roles that you want to assign to the user, and click *Next Step*, then *Save*.

    If one or more default roles have already been created, you can leave *Roles* empty. Default roles will be assigned to the user when you click *Save*.




## Results

-   A welcome email including an account activation URL will be sent to the user, so that the user can set an initial password and access the system. Optionally, you can disable the welcome email notification \(see [Configure Notifications](../configure-notifications-4388411.md)\).

-   When you create a user, it is activated by default. You may want to deactivate a user in specific cases, for example when a user is on long-term leave. To deactivate a user, select the relevant check box in the leftmost column of the table, click the icon \(*Deactivate Users*\) and optionally select *Email users to notify them that their accounts have been deactivated*. Deactivated users cannot login to SAP Datasphere until they are activated again.


> ### Note:  
> In addition to the standard workflows, you can also create users via the command line \(see [Manage Users via the Command Line](https://help.sap.com/viewer/d0ecd6f297ac40249072a44df0549c1a/cloud/en-US/72dc33a8f41944f78318138bc1a57307.html "Users with a DW Administrator role (or with equivalent privileges) can list, create, update, and delete users via the command line.") :arrow_upper_right:\).

