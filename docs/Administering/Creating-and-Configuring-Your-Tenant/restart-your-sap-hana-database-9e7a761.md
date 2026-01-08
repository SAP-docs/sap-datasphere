<!-- loio9e7a761d91a046d2abb6bd3b5c6137e9 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Restart Your SAP HANA Database

You can manually restart your SAP HANA database if it is down.



## Context

To restart your SAP HANA database, you must have a global role that grants you the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *System Information* \(`-RU-----`\) - To access the areas *Administration*, *Configuration*, and *About* \(including the *More* area\) in the *System* tool.

The *DW Administrator* global role, for example, grants these privileges. For more information, see [Privileges and Permissions](../Managing-Users-and-Roles/privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](../Managing-Users-and-Roles/standard-roles-delivered-with-sap-datasphere-a50a51d.md). 

> ### Note:  
> You cannot restart your SAP HANA database if it is up and running correctly.



## Procedure

1.  In the side navigation area, click <span class="FPA-icons-V3"></span> System ** \> **<span class="FPA-icons-V3"></span> About.

2.  Click *More* and scroll down to the bottom of the dialog.

3.  Click *Restart SAP HANA Cloud*.

    > ### Note:  
    > The restart will cause a short downtime during which SAP Datasphere and SAP HANA will no longer be connected.

4.  Click *Restart* to launch the restart process. When the restart is complete, you'll receive a notification.


