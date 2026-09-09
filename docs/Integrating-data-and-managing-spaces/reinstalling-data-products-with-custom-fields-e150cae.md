<!-- loioe150cae6255d46849f1ec9e81346a681 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Reinstalling Data Products with Custom Fields

You can reinstall an SAP data product that has custom fields.



## Prerequisites

To reinstall a data product, you must have:

-   A global role that grants you the following privileges:
    -   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
    -   *Catalog Asset* \(`–R–––--`\) - To access the catalog, view objects in the *Assets* and *Data Products* collections, and create and manage data product access requests and agreements.

-   A scoped role that grants you access to the space or spaces where you can reinstall data products, with the following privileges:
    -   *Spaces* \(`–R–––--`\) - To access a space.
    -   *Space Files* \(`CRUD–--`\) - To install data products in or uninstall data products from a space.
    -   *Data Warehouse Data Builder* \(`CRUD----`\) - To create, edit, and delete *Data Builder* objects.
    -   *Data Warehouse Connection* \(`-R------`\) - To access remote objects.


The *Catalog User* global role and the *DW Modeler* scoped role template, applied together for example, grant these privileges. For more information, see [Privileges and Permissions](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/d7350c6823a14733a7a5727bad8371aa.html "A privilege represents a task or an area in SAP Datasphere and can be assigned to a specific role. The actions that can be performed in the area are determined by the permissions assigned to a privilege.") :arrow_upper_right: and [Standard Roles Delivered with SAP Datasphere](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/a50a51d80d5746c9b805a2aacbb7e4ee.html "SAP Datasphere is delivered with several standard roles. A standard role includes a predefined set of privileges and permissions.") :arrow_upper_right:. 



## Context

When you install intelligent content via SAP Business Data Cloud, any required data products are installed in an ingestion space, but these data products don't include any custom fields defined in the source system \(see [Reviewing Installed Intelligent Content](https://help.sap.com/docs/SAP_DATASPHERE/be5967d099974c69b77f4549425ca4c0/644648756d334daaaf35d4fc9a0feeda.html)\).

However, you can update these data products to include any required custom fields by reinstalling them as part of the extension process explained in [Extending Intelligent Content](extending-intelligent-content-3c15868.md).

From time to time, users might add or remove custom fields, or they might change existing custom fields. To ensure that an SAP data product you installed has the latest updates to the custom fields, you must reinstall it.

During its lifecycle, an SAP data product might have patch, minor version, and major version updates. Any custom fields defined in the source system are available as follows:

-   Patch or a minor version update: Any custom fields defined in the source system will continue to be available.
-   Major version update: Any custom fields defined in the source system will no longer be available and they must be added again.



## Procedure

1.  In the side navigation area, choose <span class="SAP-icons-V5"></span>\(*Catalog & Marketplace*\) ** \> ** <span class="SAP-icons-V5"></span>*\(Data Product Access\)*.

2.  On the *Data Product Access* page, choose the *Agreements* tab.

3.  Select a filter and enter search terms to show the items that you want.

    The list is updated to show only the items that match the criteria you entered. 

4.  Select the access agreement to view its details page.

5.  Choose *Reinstall Data Product* to update the data product.

    For data access method, select the same method that was previously used. To learn more about this setting, go to the section **Changing the Data Delivery Method for a Data Product** in [Installing Data Products](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/605b734f433f4c3895ec827fa71bea41.html "Access requests that have been approved become access agreements and appear under the Agreements tab. You can install a data product for an access agreement or end an access agreement that's no longer needed.") :arrow_upper_right:.

6.  Choose *Reinstall Data Product*.


