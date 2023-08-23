<!-- loiob607a12931d74c4a93506ea64c55ab4e -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Importing Content from Another Tenant

Users with the *DW Administrator* or *DW Space Administrator* role can import content that has been shared from another tenant.



<a name="loiob607a12931d74c4a93506ea64c55ab4e__steps_uhk_n45_fpb"/>

## Procedure

1.  Ensure that the space or spaces that you want to import into exist in your tenant, and that each one contains any connections required by remote tables that you are importing.

    Be aware that if your content contains objects that are shared from one space to another, then both spaces must exist.

    > ### Note:  
    > The <span class="FPA-icons"></span> \(*Transport*\) app cannot create spaces or connections and cannot import content into a space with a different technical name to the space from which the content was exported. Only an administrator can create spaces \(see [Create a Space](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/bbd41b82ad4d4d9ba91341545f0b37e7.html "Create a space, allocate storage, and assign one or more members to allow them to start acquiring and preparing data.") :arrow_upper_right:\), while an administrator, space administrator, or integrator can create connections \(see [Create a Connection](../Integrating-Data-Via-Connections/create-a-connection-c216584.md)\).

2.  In the side navigation area, click <span class="FPA-icons"></span> \(*Transport*\)** \> **<span class="FPA-icons"></span> \(*Import*\) to open the list of content available for import.

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
    
    Controls what happens when an object to be imported already exists in your space:

    -   *Don’t overwrite objects or data* - Protects existing objects in your space from being overwritten or having their data updated. You are notified if any of the objects selected for import already exist in your system.

        > ### Note:  
        > If objects or data on your system will be overwritten by the import, a warning appears in the import window and next to the relevant objects in the *Content* list.

    -   *Overwrite data only* - Not currently supported for SAP Datasphere.
    -   *Overwrite objects and data* - Objects on your system can be overwritten and their data can be updated.

        Select *Including permissions* to update the *Privacy* and *Data Access Control* settings for models and dimensions. The corresponding permissions assigned to each role are also updated.



    
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

    To view the log of updates and imports for a package, select the package in the content network and choose <span class="SAP-icons"></span> History.


