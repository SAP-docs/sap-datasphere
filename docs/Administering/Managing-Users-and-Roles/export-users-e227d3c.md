<!-- loioe227d3cc675e47eca7009ed15848ae01 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Export Users

If you want to synchronize SAP Datasphere user data with other systems, you can export the data to a CSV file.



## Procedure

1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(*Security*\) ** \> ** <span class="FPA-icons-V3"></span> \(*Users*\).

2.  Select <span class="FPA-icons-V3"></span> \(Export\).




## Results

The system exports all user data into a CSV file that is automatically downloaded to your browser's default download folder.

The CSV file contains these columns:


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

Email address of the user. A welcome email with logon information is sent to the email address.

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

> ### Note:  
> Other properties that appear in columns of the file but are not mentioned in the table above are not used in SAP Datasphere.

