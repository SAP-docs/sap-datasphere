<!-- loiob2698dab33ea4487849a06ae40d8669a -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Import or Modify Users from a File

You can create users or batch-update existing users by importing user data that you have saved in a CSV file.



## Prerequisites

The user data you want to import must be stored in a CSV file. At minimum, your CSV file needs columns for `UserID`, `LastName`, and `Email`, but it is recommended that you also include `FirstName` and `DisplayName`.

If you want to assign new users different roles, include a `Roles` column in the CSV file. The role IDs used for role assignment are outlined in [Standard Roles Delivered with SAP Datasphere](standard-roles-delivered-with-sap-datasphere-a50a51d.md).

For existing users that you want to modify, you can create the CSV file by first exporting a CSV file from SAP Datasphere. For more information, see [Export Users](export-users-e227d3c.md).

> ### Note:  
> The first name, last name, and display name are linked to the identity provider, and can't be changed in the User list page, or when importing a CSV file. \(In the User list page, those columns are grayed out.\)
> 
> To edit those values, you'll need to use the user login, and edit that user's profile.

Edit the downloaded CSV file to remove columns whose values you don't want to modify, and to remove rows for users whose values you don't want to modify. Do not modify the `USERID` column. This ensures that entries can be matched to existing users when you re-import the CSV.

These are the available mapping parameters when importing CSV user data:


<table>
<tr>
<th valign="top">

Parameter

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

 

</td>
</tr>
<tr>
<td valign="top">

First Name

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Last Name

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Display Name

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Email

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Manager

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Roles

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Mobile

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Phone

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Office Location

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Function Area

</td>
<td valign="top">

Can be used to refer to a user's team or area within their organization.

</td>
</tr>
<tr>
<td valign="top">

Job Title

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Clean up notifications older than

</td>
<td valign="top">

Set in user settings: when to automatically delete notifications.

</td>
</tr>
<tr>
<td valign="top">

Email Notification

</td>
<td valign="top">

Set in user settings.

</td>
</tr>
<tr>
<td valign="top">

Welcome message

</td>
<td valign="top">

Message that is shown to the user on the home screen.

</td>
</tr>
<tr>
<td valign="top">

Page tips

</td>
<td valign="top">

Enabled/disabled via the help center \(deprecated\).

</td>
</tr>
<tr>
<td valign="top">

Closed Page tips

</td>
<td valign="top">

Closed page tips are tracked so that they are not shown again.

</td>
</tr>
<tr>
<td valign="top">

Closed Item Picker Tips

</td>
<td valign="top">

Closed tooltips are tracked so that they won't be reopened again \(for first time users\).

</td>
</tr>
<tr>
<td valign="top">

Current Banner

</td>
<td valign="top">

Saves which banner is currently showing.

</td>
</tr>
<tr>
<td valign="top">

Last Banner

</td>
<td valign="top">

The UUID of the last closed banner.

</td>
</tr>
<tr>
<td valign="top">

Last Maintenance Banner Version

</td>
<td valign="top">

The version when the last maintenance banner was shown.

</td>
</tr>
<tr>
<td valign="top">

Marketing email opt in

</td>
<td valign="top">

Set in user settings.

</td>
</tr>
<tr>
<td valign="top">

Homescreen content is initialized

</td>
<td valign="top">

If default tiles have been set for the home screen.

</td>
</tr>
<tr>
<td valign="top">

Expand Story Toolbar

</td>
<td valign="top">

Set in user settings.

</td>
</tr>
<tr>
<td valign="top">

Is user concurrent

</td>
<td valign="top">

If the user has a concurrent license.

</td>
</tr>
<tr>
<td valign="top">

On the *Edit Home Screen* dialog, a user can override all the default preferences that have been set by the administrator for the system \(*System* \> *Administration* \> *Default Appearance*\). These are the preferences:

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Override Background Option

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Override Logo Option

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Override Welcome Message

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Override Home Search To Insight

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Override Get Started

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Override Recent Stories

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Override Recent Presentations

</td>
<td valign="top">

 

</td>
</tr>
<tr>
<td valign="top">

Override Calendar Highlights

</td>
<td valign="top">

 

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


