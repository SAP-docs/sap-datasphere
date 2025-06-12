<!-- loio58e4bb2717b1445bba9e1f3d214f5181 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Check Consent Expirations

View a list of users whose authorization consent will expire in less than four weeks.



<a name="loio58e4bb2717b1445bba9e1f3d214f5181__section_vzk_lvq_hfc"/>

## Prerequisites

To check consent expirations, you must have a global role that grants you the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *System Information* \(`-RU-----`\) - To access the *Administration* and *Configuration* areas in the *System* tool.

The *DW Administrator* role template, for example, grants these privileges. For more information, see [Privileges and Permissions](../Managing-Users-and-Roles/privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](../Managing-Users-and-Roles/standard-roles-delivered-with-sap-datasphere-a50a51d.md). 



<a name="loio58e4bb2717b1445bba9e1f3d214f5181__section_lh3_kvq_hfc"/>

## Procedure

1.  To view a list of users whose authorization consent will expire within the next four weeks, click :wrench: \(*Configuration*\) ** \> *Tasks*.
2.  in the *Consent Expiration* section of the *Tasks* page, click the *View Expiration List* link. SAP Datasphere now displays a dialog in which you can view a list of users whose authorization consent will expire within a given timeframe.

![](images/Consent_Expiration_List_Dialog_5d32864.png)

By default, the dialog displays a list of users whose consent will expire within four weeks. You can change the default expiration timeframe to anywhere between one and four weeks. In addition to displaying the list of users whose consent will soon expire, you can also select a user in the list and click the *Show Affected Tasks* link to view the collection of tasks that user has scheduled.

