<!-- loio110404abd2d044008102c871b39fdf65 -->

# Monitor Database Operations with Audit Logs

Monitor the read and change actions \(policies\) performed in the database with audit logs, and see who did what and when.



<a name="loio110404abd2d044008102c871b39fdf65__section_xwg_h5q_hfc"/>

## Prerequisites

To monitor database operations with audit logs, you must have a global role that grants you the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *System Information* \(`-RU-----`\) - To access the *Administration* and *Configuration* areas in the *System* tool.

The *DW Administrator* role template, for example, grants these privileges. For more information, see [Privileges and Permissions](../Managing-Users-and-Roles/privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](../Managing-Users-and-Roles/standard-roles-delivered-with-sap-datasphere-a50a51d.md). 



<a name="loio110404abd2d044008102c871b39fdf65__section_sf3_f5q_hfc"/>

## Context

If Space Administrators have enabled audit logs to be created for their space \(see [Logging Read and Change Actions for Audit](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/266553976e1c4db9aaa28a75e2308b77.html "You can enable audit logs for your space so that read and change actions (policies) are recorded. Administrators can then analyze who performed which action at which point in time.") :arrow_upper_right:\), you can get an overview of these audit logs. You can do analytics on audit logs by assigning the audit views to a dedicated space and then work with them in a view in the Data Builder.

> ### Note:  
> Audit logs can consume a large quantity of GB of disk in your database, especially when combined with long retention periods \(which are defined at the space level\). You can delete audit logs when needed, which will free up disk space. For more information, see [Delete Audit Logs](delete-audit-logs-589fa42.md).



<a name="loio110404abd2d044008102c871b39fdf65__section_txh_jk5_dsb"/>

## Procedure

1.  Choose a space that will contain the audit logs.

    Go to *System* \> *Configuration* \> *Audit*. Enable to save and later display the audit logs directly in a certain space by choosing a space from the drop-down list. We recommend to create a dedicated space for audit logs, as you might not want all users to view sensitive data.

2.  Open the *Data Builder*, create a view, and add one or more of the following views from the DWC\_AUDIT\_READER schema as sources:
    -   `DPP_AUDIT_LOG` - Contains audit log entries.
    -   `AUDIT_LOG_OVERVIEW` - Contains audit policies \(read or change operations\) and the number of audit log entries.
    -   `ANALYSIS_AUDIT_LOG` - Contains audit log entries for database analysis users. For more information, see [Create a Database Analysis User to Debug Database Issues](create-a-database-analysis-user-to-debug-database-issues-c28145b.md).


