<!-- loio400078d689bf4454b3fc977a4e201c2f -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Importing SAP and Partner Business Content from the Content Network

Users with the *DW Administrator* or *DW Space Administrator* role can import business content and sample content from SAP and partners from the *Content Network*.



## Context

> ### Note:  
> Use of sample content and business content is optional and not part of the business functionality of the product. Content packages may be discontinued or replaced at any time.

Detailed documentation for all business content is available at [SAP Datasphere Content Documentation](https://help.sap.com/doc/4b618244ad5f4fbb8423d08996f8b891/cloud/en-US/SAP_Data_Warehouse_Cloud_Content.pdf).

> ### Note:  
> The *Content Network* is not available for trial users.



## Procedure

1.  In the side navigation area, click <span class="FPA-icons"></span> \(*Content Network*\), and then click one of the following tiles:

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


