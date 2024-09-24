<!-- loio58d4b24f766c4879b71c33f8e8dd5da8 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Create a User

You can create individual users in SAP Datasphere.



<a name="loio58d4b24f766c4879b71c33f8e8dd5da8__prereq_lkd_3n1_jhb"/>

## Prerequisites

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

A role that enables users assigned to it to perform actions that are not space-related, typically a role that enables to administrate the tenant. A standard or custom role is considered as global when it includes global privileges.

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



<a name="loio58d4b24f766c4879b71c33f8e8dd5da8__context_mgz_hjz_1fb"/>

## Context

The method described here assumes that SAP Datasphere is using its default authentication provider. If you are using a custom SAML Identity Provider, you must provide slightly different information, depending upon how your SAML authentication is configured.



## Procedure

1.  Go to <span class="FPA-icons-V3"></span> \(*Expand*\)** \> **<span class="FPA-icons-V3"></span> \(*Security*\)** \> **<span class="FPA-icons-V3"></span> \(*Users*\).

2.  Select <span class="FPA-icons-V3"></span> \(New\) to add a new user to the user management table.

3.  Enter a *User ID*.

    Each user needs a unique ID. Only alphanumeric and underscore characters are allowed. The maximum length is 127 characters.

4.  Enter the user name details.

    Only *Last Name* is mandatory, but it is recommended that you provide a *First Name*, *Last Name*, and *Display Name*. *Display Name* will appear in the screens.

5.  Enter an *Email* address.

    A welcome email with logon information will be sent to this address.

    > ### Note:  
    > The *Manager* column is not relevant for SAP Datasphere users.

6.  Select the icon <span class="FPA-icons-V3"></span> and choose one or more roles from the list.

7.  Select <span class="FPA-icons-V3"></span> \(Save\).




## Results

-   A welcome email including an account activation URL will be sent to the user, so that the user can set an initial password and access the system. Optionally, you can disable the welcome email notification \(see [Configure Notifications](../Monitoring-SAP-Datasphere/configure-notifications-4388411.md)\).

-   When you create a user, it is activated by default. You may want to deactivate a user in specific cases, for example when a user is on long-term leave. To deactivate a user, select the relevant check box in the leftmost column of the table, click the icon \(*Deactivate Users*\) and optionally select *Email users to notify them that their accounts have been deactivated*. Deactivated users cannot login to SAP Datasphere until they are activated again.


> ### Note:  
> In addition to the standard workflows, you can also create users via the command line \(see [Manage Users via the Command Line](https://help.sap.com/viewer/9b8363ae47c347de9a027c0e5567a37a/DEV_CURRENT/en-US/72dc33a8f41944f78318138bc1a57307.html "Users with a DW Administrator role (or with equivalent privileges) can list, create, update, and delete users via the command line.") :arrow_upper_right:\).

