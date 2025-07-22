<!-- loiob607a12931d74c4a93506ea64c55ab4e -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Importing Content from Another Tenant

You can use the *Transport* app to import content that has been shared from another tenant.



<a name="loiob607a12931d74c4a93506ea64c55ab4e__context_x1k_gqh_vcc"/>

## Context

To import content into a space via the *Import* app, you must have either:


<table>
<tr>
<td valign="top">

A global role that allows you to update any space and to create new spaces if necessary, by granting you the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Lifecycle* \(`-----M--`\) - To use the *Transport* apps.
-   *Spaces* \(`-------M`\) - To update all spaces and space properties.
-   *Spaces* \(`C-------`\) - To create spaces.
-   *Space Files* \(`-------M`\) - To create, read, update, and delete all objects in all spaces.

The *DW Administrator* role, for example, grants these privileges.

</td>
<td valign="top">

A combination of a global role and a scoped role:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   A global role that grants you the following privilege:
    -   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
    -   *Lifecycle* \(`-----M--`\) - To use the *Transport* apps.

-   A scoped role that grants you access to the space or spaces to import into with the following privileges:
    -   *Spaces* \(`--U-----`\) - To update your spaces and their properties.
    -   *Space Files* \(`CRUD----`\) - To create, read, update, and delete objects in your spaces.
    -   *Data Warehouse Data Builder* \(`CRUD--S-`\) - To create, read, update, delete and share data builder objects \(and any other relevant object privileges to allow you to create and update other types of objects contained in the package\).


The *DW Space Administrator* global and scoped role templates, for example, grant this combination of privileges.

</td>
</tr>
</table>

For more information, see [Privileges and Permissions](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/d7350c6823a14733a7a5727bad8371aa.html "A privilege represents a task or an area in SAP Datasphere and can be assigned to a specific role. The actions that can be performed in the area are determined by the permissions assigned to a privilege.") :arrow_upper_right: and [Standard Roles Delivered with SAP Datasphere](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/a50a51d80d5746c9b805a2aacbb7e4ee.html "SAP Datasphere is delivered with several standard roles. A standard role includes a predefined set of privileges and permissions.") :arrow_upper_right:. 



<a name="loiob607a12931d74c4a93506ea64c55ab4e__steps_uhk_n45_fpb"/>

## Procedure

1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(*Transport*\)** \> **<span class="FPA-icons-V3"></span> \(*Import*\) to open the list of content available for import.

    If you don’t see expected packages to import, click the *Settings* button and review the import settings. You can:

    -   Enable the *Show content shared by all systems* option and optionally exclude content from specific tenants by adding them to the *Add systems to block content sharing* list.
    -   Disable the *Show content shared by all systems* option and choose specific tenants to import from by adding them to the *Add systems to allow content sharing* list.

    If, after checking these settings, an expected package is still not listed, contact an administrator for help.

2.  Click a package to open it and see an overview of its content.

3.  Review the *Import Overview* section. For more details, and to modify any of the options, click the *Import Options* tab:


    <table>
    <tr>
    <th valign="top">

    Section
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Import Schedule
    
    </td>
    <td valign="top">
    
    Specifies what happens when the package is updated:

    -   *None* - No updates are made on your system. This option is automatically selected for packages that cannot be updated.
    -   *Notify for new content* - You receive a notification and can choose whether to import the new version of the package to your system.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Overwrite Preferences
    
    </td>
    <td valign="top">
    
    Controls whether objects that are already present in your space can be overwritten during an import.

    > ### Note:  
    > Only object definitions can be transported. Data cannot be transported between SAP Datasphere tenants via the <span class="FPA-icons-V3"></span> \(*Transport*\) app.

    You can choose between:

    -   *Don’t overwrite objects or data* - \[default\] Imports only objects that are not already present in your space. Objects that are already present are not updated, and are listed with warnings in the *Import* window.
    -   *Overwrite data only* - Not supported for SAP Datasphere.
    -   *Overwrite objects and data* - Imports all objects from the package, even if certain objects are already present in your space. These objects may be updated, and these updates may impact data \(for example, if a column is deleted\).

        > ### Note:  
        > -   The *Including permissions* option is not supported for SAP Datasphere.
        > -   Connections are never overwritten by an import.
        > -   When overwriting objects with a release state, the objects you are importing must have the same release state or another release state that is consistent with their lifecycle \(see [Releasing Stable Views for Consumption](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/5b99e9bcb5964ab69b094215d285feb1.html "To encourage confidence in the stability of your views and to guarantee backward compatibility when they are updated, you can set their Release State to Released. Once a view is released, it must continue to provide the same output columns until it is replaced by a successor, at which point it can be deprecated and, eventually, decommissioned.") :arrow_upper_right:\).



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Deployment Preference
    
    </td>
    <td valign="top">
    
    Check the *Deploy after import* checkbox to automatically deploy objects after import. If you have selected:

    -   **Don't overwrite objects or data** - Only newly imported objects will be deployed.
    -   **Overwrite objects and data** - All imported objects in the space will be deployed.

    > ### Note:  
    > This option does not support packages that contain objects from one or more spaces where objects are shared from one space to another \(see [Sharing Entities and Task Chains to Other Spaces](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/64b318f8afd74bb78467cf56eb44294f.html "Share a table or view to another space to allow users assigned to that space to use it as a source for their objects. Share a task chain to another space to allow it to be added to and controlled by another task chain in the space that you share it to.") :arrow_upper_right:. In this case, you should manually deploy the objects from the source space and then deploy the objects from the target space.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Content
    
    </td>
    <td valign="top">
    
    Select the space or spaces to import your content into in the *Space Mapping* field. You must choose one space for each space listed in the package:

    -   You can select any space for which you have the *Spaces.Update* permission to import the space's content into.

        If you have the *Spaces.Manage* permission, then you can choose to import into any space in your tenant.

    -   If the space does not exist in your tenant and you have the *Spaces.Create* permission, then you are invited to create it by default.
    -   You cannot "merge" content from two or more spaces included in your package. You must select a separate space for each space listed.
    -   You can only import content into a space with the appropriate storage type. Objects exported from a disk space cannot be imported into a file space and vice versa.

    > ### Note:  
    > Choosing space mappings is only possible if the source objects for any shared objects are included in the package. For example if your package contains shared objects in `Space A` that have been shared from `Space B`, then the source objects from `Space B` must be included in the package. If the sources of any shared objects cannot be resolved in the package, then the package must be imported into spaces with the same technical names as the spaces listed in the package.

    Review the objects to be imported. All objects are imported by default.

    You can select and deselect individual objects, or types of objects. The *Impacted Object* column shows warnings for objects that will overwrite content on your system.
    
    </td>
    </tr>
    </table>
    
4.  Click *Import* to begin importing the content. 

    You will receive a notification when the process is complete, or if an error occurs.

    If you selected *Don’t overwrite objects or data*, a notification will let you know if any of the content wasn’t imported to avoid overwriting existing content.

    To view the log of updates and imports for a package, select the package in the content network and choose <span class="SAP-icons-V5"></span> History.

5.  If your content included one or more connections that didn't exist in your space before the import, then you should:

    1.  In the *Connections* app, open each connection, complete the configuration and enter appropriate credentials to connect to your system \(see [Edit a Connection](../Integrating-Data-Via-Connections/edit-a-connection-ba20892.md)\).

    2.  In the *Repository Explorer* or in the object editors, select the imported objects that depend on an imported connection \(and which could not, therefore, be automatically deployed\) and click <span class="SAP-icons-V5"></span> \(Deploy\) to deploy them.

        > ### Note:  
        > If you checked the *Deploy after import* checkbox in the *Import Options*, you can find a notification about the failed deployment of objects in the *Notifications* panel. Clicking the notification directly leads you to the list of imported objects in the *Repository Explorer*.


6.  If you are a *DW Administrator* and have created a space as part of the import, you are assigned to the space as a *DW Space Administrator*. You can assign other users to the space \(including as space administrators\) as appropriate.


