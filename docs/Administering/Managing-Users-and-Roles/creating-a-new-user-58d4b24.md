<!-- loio58d4b24f766c4879b71c33f8e8dd5da8 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Creating a New User

You can create individual users in SAP Datasphere.



<a name="loio58d4b24f766c4879b71c33f8e8dd5da8__prereq_lkd_3n1_jhb"/>

## Prerequisites

You can select one or more roles while you're creating the user. Before getting started creating users, you might want to become familiar with the standard application roles or custom roles. But don't worry-you can still assign roles after you've created the users.

> ### Note:  
> For more information about how to create a user and assign roles, check the in-app help in your system. Use F1 to open in-app help from SAP Datasphere User Interfaces. You can also use the question mark and click the *Help* tile to open the help.


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

Standard application roles



</td>
<td valign="top">

The roles available depend on the licenses included in your subscription



</td>
<td valign="top">

 [Standard Application Roles](standard-application-roles-a50a51d.md) 



</td>
</tr>
<tr>
<td valign="top">

Custom roles



</td>
<td valign="top">

Variations on the standard roles, created to meet your company's needs



</td>
<td valign="top">

 [Create a Custom Role](create-a-custom-role-862b88e.md) 



</td>
</tr>
</table>



<a name="loio58d4b24f766c4879b71c33f8e8dd5da8__context_mgz_hjz_1fb"/>

## Context

The method described here assumes that SAP Datasphere is using its default authentication provider. If you are using a custom SAML Identity Provider, you must provide slightly different information, depending upon how your SAML authentication is configured.



## Procedure

1.  Go to <span class="FPA-icons"></span> \(*Expand*\)** \> **<span class="FPA-icons"></span> \(*Security*\)** \> **<span class="FPA-icons"></span> \(*Users*\).

2.  Select <span class="FPA-icons"></span> \(New\) to add a new user to the user management table.

3.  Enter a *User ID*.

    Each user needs a unique ID. Only alphanumeric and underscore characters are allowed. The maximum length is 127 characters.

4.  Enter the user name details.

    Only *Last Name* is mandatory, but it is recommended that you provide a *First Name*, *Last Name*, and *Display Name*. *Display Name* will appear in user-facing screens.

5.  Enter an *Email* address.

    A welcome email with logon information will be sent to this address.

6.  Select the *Manager* who will approve requests this user makes for new role assignments.

    Users can request additional roles only if they have a custom role that allows for self-service.

7.  Select the icon <span class="FPA-icons"></span> and choose one or more roles from the list.

    If one or more default roles have already been created, you can leave *Roles* empty. Default roles will be assigned when you click save.

8.  Select <span class="FPA-icons"></span> \(Save\).




## Results

A welcome email including an account activation URL will be sent to the user, so that the user can set an initial password and access the system.

