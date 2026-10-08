<!-- loiof4d469b644af4c30b8cd071d07a2babc -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Resolving Schema Inconsistencies

You can check for schema changes between installed data products and their catalog versions and then resolve the discrepancies.



## Prerequisites

To run the schema inconsistency check and resolve inconsistencies, you must have:

-   A global role that grants you the following privileges:
    -   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
    -   *Catalog Asset* \(`–RU––--`\) - To run the schema inconsistencies check and update the data product installations.

-   A scoped role that grants you the following privilege:
    -   *Data Warehouse Connection* \(`-R------`\) - To access remote objects.


The *Catalog User* global role and the *DW Modeler* scoped role template, applied together for example, grant these privileges. For more information, see [Privileges and Permissions](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/d7350c6823a14733a7a5727bad8371aa.html "A privilege represents a task or an area in SAP Datasphere and can be assigned to a specific role. The actions that can be performed in the area are determined by the permissions assigned to a privilege.") :arrow_upper_right: and [Standard Roles Delivered with SAP Datasphere](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/a50a51d80d5746c9b805a2aacbb7e4ee.html "SAP Datasphere is delivered with several standard roles. A standard role includes a predefined set of privileges and permissions.") :arrow_upper_right:. 



## Context

To check for and resolve data product inconsistencies, use the *Check for Schema Changes* action.

If a data product is inactive, you can resolve the schema inconsistencies by activating it in SAP Business Data Cloud cockpit. Activating the data product automatically updates its installation. You can also uninstall the data product by ending all access agreements for it.



## Procedure

1.  In the side navigation area, choose <span class="SAP-icons-V5"></span>\(*Catalog & Marketplace*\) ** \> ** <span class="SAP-icons-V5"></span>*\(Data Product Access\)*.

2.  At the top of the *Data Product Access* page select *Check for Schema Changes*.

    A dialog informing you that the check has started appears. The check might take some time to complete. When it's finished, the *Resolve Inconsistencies* page appears, showing a list of the data products that have schema inconsistencies.

3.  Select the data products that you want to update and choose *Update Installations*.

    If you don't want to update any of the data products, choose *Cancel* to return to the *Data Product Access* page.

    > ### Note:  
    > As a best practice, check the data product consumption and notify users before updating the installation. Updating data products can take a significant amount of time \(for example, a couple of hours to a couple of days, or in extreme cases, even longer\). Data products that are being updated are not available for consumption until the installation update has finished.

4.  Review the confirmation dialog and select *Confirm*.




## Results

A message confirms that some data products are queued for update. Updates start in a staggered sequence: the first data product begins updating, and each subsequent update starts a few moments after the previous one. You receive an in-app notification when each update starts and another when it ends.

During the installation update, all objects are redeployed, the replication flow to load the data in the updated schema is restarted, and all spaces where the data product is installed are refreshed.

