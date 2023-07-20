<!-- loio862b88eed50244049d41361ba3290456 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Create a Custom Role

You can create a new custom role either by customizing a predefined role or by creating a role from a blank template. 



<a name="loio862b88eed50244049d41361ba3290456__prereq_yst_nqr_vnb"/>

## Prerequisites

To create a custom role, you need the DW Administrator role.



## Procedure

1.  Go to <span class="FPA-icons"></span> \(*Expand*\)** \> **<span class="FPA-icons"></span> \(*Security*\)** \> **<span class="FPA-icons"></span> \(*Roles*\).

2.  To create a custom role, click <span class="FPA-icons"></span> \(Add Role\) and select *Create a Custom Role*.

3.  Enter a unique name for the role and select the license type SAP Datasphere.

4.  Select *Create*.

5.  Select a role template.

    The role templates are the predefined standard roles associated with the SAP Datasphere license type. If you wish to create a role without extending a predefined standard role, choose the blank template. After you select a template, the *Permissions* page appears, showing you the individual permissions assigned to privilege types that have been defined for the role template you chose.

    > ### Note:  
    > Currently, it is not possible to add *Catalog* access to a custom role as a template. Assign either the *Catalog Administrator* or *Catalog User* standard application roles instead.

6.  Define the permissions for your new role for every privilege type. The permission privileges represent an area, application or tool in SAP Datasphere while the permissions \(create, read, update, delete, manage and share\) represent the actions a user can perform.

    For example, to define a user who is allowed to read all data change logs, select the check box in the *Read* column of the *Data Change Log* row. The permission is automatically passed on to all existing logs.

    To define that the user should be allowed to read only specific data change logs, expand the *Data Change Log* node, and then select the check box in the *Read* column only for specific log rows.

7.  If you want to change the role template that your new custom role will be based on, select <span class="FPA-icons"></span> \(*Select Template*\), and choose a role.

8.  Save your new custom role.

    > ### Note:  
    > You can't delete or save changes to the predefined standard roles.

    > ### Note:  
    > In this procedure, we use the *Roles* page to assign roles to users, but you can also assign roles on the *Users* page. Whether you create users first or roles first does not matter.


