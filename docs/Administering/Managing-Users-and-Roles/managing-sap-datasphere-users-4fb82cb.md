<!-- loio4fb82cb61ca84d8389e9cb18d94dab26 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Managing SAP Datasphere Users

You can create and modify users in SAP Datasphere in several different ways.



<a name="loio4fb82cb61ca84d8389e9cb18d94dab26__section_pjp_kr4_hfc"/>

## Prerequisites

To manage users, you must have a global role that grants you the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *User* \(`CRUD----`\) - To access the <span class="FPA-icons-V3"></span> \(*Users*\)area in the <span class="FPA-icons-V3"></span> \(*Security*\) tool and to create, update, and delete users.
-   *User* \(`-------M`\) - To assign users to roles.

The *DW Administrator* global role, for example, grants these privileges. For more information, see [Privileges and Permissions](privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](standard-roles-delivered-with-sap-datasphere-a50a51d.md). 



## Context

In addition to working with users in the *Security* tool, you can also:

-   List, create, update, and delete them using the `datasphere` command line interface \(see [Manage Users via the Command Line](https://help.sap.com/viewer/d0ecd6f297ac40249072a44df0549c1a/cloud/en-US/72dc33a8f41944f78318138bc1a57307.html "Users with a DW Administrator role (or with equivalent privileges) can list, create, update, and delete users via the command line.") :arrow_upper_right:\).
-   List, read, create, modify, or delete them and add them to roles via the SCIM 2.0 API \(see [Create Users and Assign Them to Roles via the SCIM 2.0 API](create-users-and-assign-them-to-roles-via-the-scim-2-0-api-1ca8c4a.md)\).



<a name="loio4fb82cb61ca84d8389e9cb18d94dab26__section_wfq_rrf_bfb"/>

## Creating Users

You can create users in the following ways:


<table>
<tr>
<th valign="top">

Method

</th>
<th valign="top">

More Information

</th>
</tr>
<tr>
<td valign="top">

Create individual users in the *Users* list

</td>
<td valign="top">

[Create a User](create-a-user-58d4b24.md) 

</td>
</tr>
<tr>
<td valign="top">

Import multiple users from a CSV file

</td>
<td valign="top">

[Import or Modify Users from a File](import-or-modify-users-from-a-file-b2698da.md) 

</td>
</tr>
</table>



## Modifying Users

You can modify existing users in the following ways:


<table>
<tr>
<th valign="top">

Modification

</th>
<th valign="top">

More Information

</th>
</tr>
<tr>
<td valign="top">

Export user data to a CSV file, to synchronize with other systems

</td>
<td valign="top">

[Export Users](export-users-e227d3c.md)

</td>
</tr>
<tr>
<td valign="top">

Update the email address a user logs on with

</td>
<td valign="top">

[Update a User Email Address](update-a-user-email-address-0889208.md)

</td>
</tr>
<tr>
<td valign="top">

Delete users

</td>
<td valign="top">

[Delete a User](delete-a-user-3ceb94c.md)

</td>
</tr>
</table>

