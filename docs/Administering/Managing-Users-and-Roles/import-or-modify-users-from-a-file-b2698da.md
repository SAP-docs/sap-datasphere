<!-- loiob2698dab33ea4487849a06ae40d8669a -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Import or Modify Users from a File

You can create users or batch-update existing users by importing user data that you have saved in a CSV file.



## Prerequisites

The user data you want to import must be stored in a CSV file. At minimum, your CSV file needs columns for `UserID`, `LastName`, and `Email`, but it is recommended that you also include `FirstName` and `DisplayName`.

If you want to assign new users different roles, include a `Roles` column in the CSV file. The role IDs used for role assignment are outlined in [Standard Application RolesStandard Roles Delivered with SAP Datasphere](standard-application-rolesstandard-roles-delivered-with-sap-datasphere-a50a51d.md).

For existing users that you want to modify, you can create the CSV file by first exporting a CSV file from SAP Datasphere. For more information, see [Export Users](export-users-e227d3c.md).

> ### Note:  
> The first name, last name, and display name are linked to the identity provider, and can't be changed in the *Users* page, or when importing a CSV file.

Edit the downloaded CSV file to remove columns whose values you don't want to modify, and to remove rows for users whose values you don't want to modify. Do not modify the `USERID` column. This ensures that entries can be matched to existing users when you re-import the CSV.

These are the available mapping parameters when importing CSV user data:


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

USER\_NAME

</td>
<td valign="top">

ID of the user. Each user needs a unique ID. Once the user account is created their ID can’t be modified. Only upper-case letters \(A-Z\), numbers \(0-9\), and underscores are allowed. The maximum length is 20 characters.

</td>
</tr>
<tr>
<td valign="top">

FIRST\_NAME

</td>
<td valign="top">

First name of the user.

</td>
</tr>
<tr>
<td valign="top">

LAST\_NAME

</td>
<td valign="top">

Last name of the user.

</td>
</tr>
<tr>
<td valign="top">

DISPLAY\_NAME

</td>
<td valign="top">

Name of the user that appears on the screens.

</td>
</tr>
<tr>
<td valign="top">

EMAIL

</td>
<td valign="top">

Email address of the user. A welcome email with logon information is sent to the email address. .

</td>
</tr>
<tr>
<td valign="top">

ROLES

</td>
<td valign="top">

Roles assigned to the user via scoped roles.

</td>
</tr>
<tr>
<td valign="top">

SAML\_USER\_MAPPING

</td>
<td valign="top">

SAML property for the user \(if SAML enabled\).

</td>
</tr>
</table>



<a name="loiob2698dab33ea4487849a06ae40d8669a__steps_i5x_qnh_5q"/>

## Procedure

1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(*Security*\) ** \> ** <span class="FPA-icons-V3"></span> \(*Users*\).

2.  Select <span class="FPA-icons-V3"></span> \(Import Users\)** \> *Import Users from File*.

3.  In the *Import Users* dialog, choose *Select Source File* to upload your CSV file.

4.  Choose *Create Mapping* to assign the fields of your user data from the CSV file to the fields in user management.

5.  Select the appropriate entries for the *Header*, *Line Separator*, *Delimiter*, and *Text Qualifier*.

6.  Select *OK* when you've finished mapping.

7.  In the *Import Users* dialog, choose *Import* to upload your CSV file according to the defined mapping.


