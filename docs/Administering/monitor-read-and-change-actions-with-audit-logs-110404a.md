<!-- loio110404abd2d044008102c871b39fdf65 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Monitor Read and Change Actions with Audit Logs

Monitor the read and change actions \(policies\) performed in the database with audit logs, and see who did what and when.

This topic contains the following sections:

-   [Prerequisites](monitor-read-and-change-actions-with-audit-logs-110404a.md#loio110404abd2d044008102c871b39fdf65__section_prereq)
-   [Prepare a Space for Monitoring Audit Logs](monitor-read-and-change-actions-with-audit-logs-110404a.md#loio110404abd2d044008102c871b39fdf65__section_prepare_space)
-   [Review Audit Log Records](monitor-read-and-change-actions-with-audit-logs-110404a.md#loio110404abd2d044008102c871b39fdf65__section_review_audit_log_records)



<a name="loio110404abd2d044008102c871b39fdf65__section_prereq"/>

## Prerequisites

To monitor database operations with audit logs, you must have a global role that grants you the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *System Information* \(`-RU-----`\) - To access the *Configuration* area in the *System* tool.

The *DW Administrator* role template, for example, grants these privileges. For more information, see [Privileges and Permissions](Managing-Users-and-Roles/privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](Managing-Users-and-Roles/standard-roles-delivered-with-sap-datasphere-a50a51d.md). 



<a name="loio110404abd2d044008102c871b39fdf65__section_sf3_f5q_hfc"/>

## Context

To monitor read and change actions with audit logs, you must first prepare a space for audit logs and designate it as the audit space. You can then review audit log records in *Data Builder* views.

> ### Note:  
> Audit logs can consume a large quantity of GB of disk in your database, especially when combined with long retention periods \(which are defined at the space level\). You can delete audit logs when needed, which will free up disk space. For more information, see [Delete Audit Logs](delete-audit-logs-589fa42.md).



<a name="loio110404abd2d044008102c871b39fdf65__section_prepare_space"/>

## Prepare a Space for Monitoring Audit Logs

We recommend using a dedicated space for audit logs to maintain greater control over who can access audit log data.

1.  Choose a space that will contain the audit logs or, alternatively, create a new space \(see [Create a Space](Creating-Spaces-and-Allocating-Storage/create-a-space-bbd41b8.md)\).
2.  Grant access to the space only to certain users and keep access restricted.
    -   Add one or more users to an existing scoped role \(see [Add Users to a Scoped Role](Managing-Users-and-Roles/create-a-scoped-role-to-assign-privileges-to-users-in-spaces-b5c4e0b.md#loiob5c4e0b6c462414783ebbfc053815521__section_u4g_xpj_zyb)\).
    -   Create a scoped role and add the space and users to the scoped role \(see [Create a Scoped Role](Managing-Users-and-Roles/create-a-scoped-role-to-assign-privileges-to-users-in-spaces-b5c4e0b.md#loiob5c4e0b6c462414783ebbfc053815521__section_z4m_mpj_zyb)\).

3.  In the side navigation area, select *System* \> *Configuration* \> *Audit*, select the space from the drop-down list to enable to save the audit logs in that space and select *Confirm Selected Space*.

    > ### Note:  
    > Once views are created from the DWC\_AUDIT\_READER schema, removing or changing the audit log space will invalidate any existing views that reference that schema.




<a name="loio110404abd2d044008102c871b39fdf65__section_review_audit_log_records"/>

## Review Audit Log Records

1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(*Data Builder*\) and create a view \(see [Creating a Graphical View](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/27efb479c4814252964d3fbc6ca2dfc3.html "Create a view to query sources in an intuitive graphical interface. You can drag and drop sources from the Source Browser, join them as appropriate, add other operators to remove or create columns and filter or aggregate data, and specify measures and other aspects of your output structure in the output node.") :arrow_upper_right:.\)
2.  Add one or more of the following views from the DWC\_AUDIT\_READER schema as sources:
    -   `ANALYSIS_AUDIT_LOG` - Contains audit log entries for all actions of the database analysis users \(see [Create a Database Analysis User to Debug Database Issues](create-a-database-analysis-user-to-debug-database-issues-c28145b.md)\).
    -   `AUDIT_LOG_OVERVIEW` - Contains an overview of all audit policies - including those for spaces, database analysis users, and sensitive personal data read access - and the number of audit log entries associated with each policy.

        When audit policies for read or change operations are enabled on a space, the corresponding policy names are:

        -   DWC\_DPP\_<space name\>\_READ
        -   DWC\_DPP\_<space name\>\_CHANGE

    -   `COLUMN_ACCESS_AUDIT_LOG` - Not in use
    -   `DPP_AUDIT_LOG` - Contains audit log entries for spaces where audit logging has been enabled by a space administrator \(see [Logging Read and Change Actions for Audit](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/266553976e1c4db9aaa28a75e2308b77.html "You can enable audit logs for your space so that read and change actions (policies) are recorded. Administrators can then analyze who performed which action at which point in time.") :arrow_upper_right:\).


