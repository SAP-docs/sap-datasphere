<!-- loiob607a12931d74c4a93506ea64c55ab4e -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Importing Content from Another Tenant

Users with the *DW Administrator* global role \(or users with both a scoped *DW Space Administrator* role and a global role providing the *Lifecycle* privilege\), can use the *Transport* app to import content that has been shared from another tenant.



<a name="loiob607a12931d74c4a93506ea64c55ab4e__steps_uhk_n45_fpb"/>

## Procedure

1.  Ensure that your tenant is ready to import your content package:


    <table>
    <tr>
    <th valign="top">

    Prerequisite
    
    </th>
    <th valign="top">

    DW Administrator
    
    </th>
    <th valign="top">

    DW Space Administrator
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Does the space exist?

    You cannot import content into a space with a different technical name to the space from which the content was exported

    > ### Note:  
    > If the package contains objects from more than one space or objects that are shared from one space to another, then all referenced spaces must exist.


    
    </td>
    <td valign="top">
    
    No preparation is necessary. Users with the *DW Administrator* can create spaces through the *Import* app.
    
    </td>
    <td valign="top">
    
    If one or more required spaces does not exist, you must request a *DW Administrator* to create them for you.
    
    </td>
    </tr>
    </table>
    
2.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(*Transport*\)** \> **<span class="FPA-icons-V3"></span> \(*Import*\) to open the list of content available for import.

    If you don’t see expected packages to import, click the *Settings* button and review the import settings. You can:

    -   Enable the *Show content shared by all systems* option and optionally exclude content from specific tenants by adding them to the *Add systems to block content sharing* list.
    -   Disable the *Show content shared by all systems* option and choose specific tenants to import from by adding them to the *Add systems to allow content sharing* list.

    If, after checking these settings, an expected package is still not listed, contact an administrator for help.

3.  Click a package to open it and see an overview of its content.

4.  Review the *Import Overview* section. For more details, and to modify any of the options, click the *Import Options* tab:


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
    > Only object definitions can be transported. Data cannot be transported between SAP Datasphere tenants.

    You can choose between:

    -   *Don’t overwrite objects or data* - \[default\] Imports only objects that are not already present in your space. Objects that are already present are not updated, and are listed with warnings in the *Import* window.
    -   *Overwrite data only* - Not supported for SAP Datasphere.
    -   *Overwrite objects and data* - Imports all objects from the package, even if certain objects are already present in your space. These objects may be updated, and these updates may impact data \(for example, if a column is deleted\).

        > ### Note:  
        > -   The *Including permissions* option is not supported for SAP Datasphere.
        > -   Connections are never overwritten by an import.



    
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
    > This option does not support packages that contain objects from one or more spaces where objects are shared from one space to another \(see [Sharing Tables and Views To Other Spaces](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/64b318f8afd74bb78467cf56eb44294f.html "Share a Data Builder table or view to another space to allow users assigned to that space to use it as a source for their objects.") :arrow_upper_right:. In this case, you should manually deploy the objects from the source space and then deploy the objects from the target space.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Content
    
    </td>
    <td valign="top">
    
    Review the objects to be imported. All objects are imported by default.

    You can select and deselect individual objects, or types of objects. The *Impacted Object* column shows warnings for objects that will overwrite content on your system.
    
    </td>
    </tr>
    </table>
    
5.  Click *Import* to begin importing the content. 

    You will receive a notification when the process is complete, or if an error occurs.

    If you selected *Don’t overwrite objects or data*, a notification will let you know if any of the content wasn’t imported to avoid overwriting existing content.

    To view the log of updates and imports for a package, select the package in the content network and choose <span class="SAP-icons-V5"></span> History.

6.  If your content included one or more connections that didn't exist in your space before the import, then you should:

    1.  In the *Connections* app, open each connection, complete the configuration and enter appropriate credentials to connect to your system \(see [Edit a Connection](../Integrating-Data-Via-Connections/edit-a-connection-ba20892.md)\).

    2.  In the *Repository Explorer* or in the object editors, select the imported objects that depend on an imported connection \(and which could not, therefore, be automatically deployed\) and click <span class="SAP-icons-V5"></span> \(Deploy\) to deploy them.

        > ### Note:  
        > If you checked the *Deploy after import* checkbox in the *Import Options*, you can find a notification about the failed deployment of objects in the *Notifications* panel. Clicking the notification directly leads you to the list of imported objects in the *Repository Explorer*.


7.  If you are a *DW Administrator* and have created a space as part of the import, you are assigned to the space as a *DW Space Administrator*. You can assign other users to the space \(including as space administrators\) as appropriate.


