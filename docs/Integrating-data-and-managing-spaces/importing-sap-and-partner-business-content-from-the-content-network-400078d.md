<!-- loio400078d689bf4454b3fc977a4e201c2f -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Importing SAP and Partner Business Content from the Content Network

Users with the *DW Administrator* global role \(or users with both a scoped *DW Space Administrator* role and a global role providing the *Lifecycle* privilege\), can use the *Semantic Onboarding* app to import business content and sample content from SAP and partners published to the *Content Network*.



## Context

> ### Note:  
> Use of sample content and business content is optional and not part of the business functionality of the product. Content packages may be discontinued or replaced at any time.

Detailed documentation for all business content is available at [SAP Datasphere Content Documentation](https://help.sap.com/doc/4b618244ad5f4fbb8423d08996f8b891/cloud/en-US/SAP_Data_Warehouse_Cloud_Content.pdf).

> ### Note:  
> The *Content Network* is not available for trial users.

We also provide content for download at our [Community Content](https://github.com/SAP-samples/analytics-cloud-datasphere-community-content) site.



## Procedure

1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(*Semantic Onboarding*\), and then click one of the following tiles: 

    -   *Business Content*: End-to-end business scenarios created by SAP for various industries and lines of business.
    -   *3rd Party Content*: End-to-end business scenarios created by SAP partners. Some third-party content has to be purchased in the *SAP Store*.
    -   *Samples*: Not used in SAP Datasphere.

2.  Click a package to open it and see an overview of its content.

3.  Review the *How to install this package* section to understand the requirements for installing the content. You may be instructed to:

    -   Create a space with a specific business and technical name before importing the content.
    -   Create a connection in the new space.
    -   Visit the *SAP Store* and, in some cases, make a payment to a partner.
    -   Contact a partner to complete the installation or obtain data.

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
        > Connections are never overwritten by an import. The *Including permissions* option is not supported for SAP Datasphere.



    
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
    > This option does not support packages that contain objects from one or more spaces where objects are shared from one space to another \(see [Sharing Tables and Views To Other Spaces](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/64b318f8afd74bb78467cf56eb44294f.html "Share a Data Builder table or view to another space to allow that users assigned to the space use it as a source for their objects.") :arrow_upper_right:. In this case, you should manually deploy the objects from the source space and then deploy the objects from the target space.


    
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


