<!-- loio903b75e638074c638ed88a4b14b935c5 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Managing Users and Roles

Users with an administrator role can create SAP Datasphere users and manage secure access to the tenant through roles and privileges.

This topic contains the following sections:

-   [Provision Users](managing-users-and-roles-903b75e.md#loio903b75e638074c638ed88a4b14b935c5__section_provision)
-   [Grant Privileges with Scoped and Global Roles](managing-users-and-roles-903b75e.md#loio903b75e638074c638ed88a4b14b935c5__section_global)



<a name="loio903b75e638074c638ed88a4b14b935c5__section_provision"/>

## Provision Users

Users must be provisioned to SAP Datasphere before they can be granted privileges to access it. You can provision users via:

-   Your identity provider \(see [Managing User Identity and Authentication](managing-user-identity-and-authentication-48b5c8b.md)\).
-   The SCIM API \(see [Create Users and Assign Them to Roles via the SCIM 2.0 API](create-users-and-assign-them-to-roles-via-the-scim-2-0-api-1ca8c4a.md)\).
-   The command line \(see [Manage Users via the Command Line](https://help.sap.com/viewer/d0ecd6f297ac40249072a44df0549c1a/cloud/en-US/72dc33a8f41944f78318138bc1a57307.html "Users with a DW Administrator role (or with equivalent privileges) can list, create, update, and delete users via the command line.") :arrow_upper_right:\).
-   The <span class="FPA-icons-V3"></span> \(*Security*\) ** \> ** <span class="FPA-icons-V3"></span> \(*Users*\) app \(see [Create a User](create-a-user-58d4b24.md)\).



<a name="loio903b75e638074c638ed88a4b14b935c5__section_global"/>

## Grant Privileges with Scoped and Global Roles

Users must be granted privileges before they can work in SAP Datasphere or access data exposed by it.

Privileges are granted via roles, which are either:

-   Scoped roles - Providing access to one or more spaces and privileges to perform certain tasks or access certain features in those spaces.
-   Global roles - Providing tenant-wide privileges to perform certain tasks or access certain features.

Users can be granted a combination of global and scoped roles as necessary to perform their tasks in the tenant.

For more information, see:

-   [Privileges by App, Tool, Object, and Task](privileges-by-app-tool-object-and-task-2d8b7d0.md)
-   [Create a Scoped Role to Assign Privileges to Users in Spaces](create-a-scoped-role-to-assign-privileges-to-users-in-spaces-b5c4e0b.md)
-   [Assign Users to a Role](assign-users-to-a-role-57a7880.md)

