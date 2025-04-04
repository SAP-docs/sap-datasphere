<!-- loio266553976e1c4db9aaa28a75e2308b77 -->

# Logging Read and Change Actions for Audit

You can enable audit logs for your space so that read and change actions \(policies\) are recorded. Administrators can then analyze who performed which action at which point in time.

This topic contains the following sections:

-   [Enable Audit Logs](logging-read-and-change-actions-for-audit-2665539.md#loio266553976e1c4db9aaa28a75e2308b77__section_pgz_ym4_2jb)
-   [Disable Audit Logs](logging-read-and-change-actions-for-audit-2665539.md#loio266553976e1c4db9aaa28a75e2308b77__section_gzv_3kx_rvb)
-   [Export Audit Logs](logging-read-and-change-actions-for-audit-2665539.md#loio266553976e1c4db9aaa28a75e2308b77__section_js3_ylk_k2c)



<a name="loio266553976e1c4db9aaa28a75e2308b77__section_lsx_5cj_42c"/>

## Prerequisites

To enable audit logs for your space, you must have a scoped role that grants you access to your space with the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Spaces* \(`-RU-----`\) - To open and update your space in the *Space Management* tool.
-   *Space Files* \(`-R------`\) - To view objects in your space.

The *DW Space Administrator* role template, for example, grants these privileges. For more information, see [Privileges and Permissions](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/d7350c6823a14733a7a5727bad8371aa.html "A privilege represents a task or an area in SAP Datasphere and can be assigned to a specific role. The actions that can be performed in the area are determined by the permissions assigned to a privilege.") :arrow_upper_right: and [Standard Roles Delivered with SAP Datasphere](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/a50a51d80d5746c9b805a2aacbb7e4ee.html "SAP Datasphere is delivered with several standard roles. A standard role includes a predefined set of privileges and permissions.") :arrow_upper_right:. 

> ### Note:  
> Relevant only for spaces with a storage type *SAP HANA Database \(Disk and In-Memory\)*, and not for *SAP HANA Data Lake Files* spaces.



<a name="loio266553976e1c4db9aaa28a75e2308b77__section_pgz_ym4_2jb"/>

## Enable Audit Logs

-   Enable audit logs of SAP Datasphere objects for read and change operations on the space level in *Space Management* \> *<Your Space\>* \> *Edit Space* \> *Auditing*. You can set the retention time in days for each audit log policy \(read or change\). The default and minimum retention time is 7 days and the maximum retention time is 10 000 days.

    If audit logs have been enabled, entries of all SAP Datasphere related objects are saved in an SAP HANA audit log. These logs don't include the objects of the database access schemas, like open SQL schemas, for example.

    > ### Note:  
    > If you choose to enable audit logs, be aware that they can consume a large quantity of GB of disk in your SAP Datasphere tenant database, especially when combined with long retention periods. Administrators can delete audit logs when needed, which will free up disk space. For more information, see [Delete Audit Logs](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/589fa4251db74fb7955eeee5d86fc25c.html "Delete audit logs and free up disk storage.") :arrow_upper_right:.

-   For individual database schemas \(open SQL schemas\), you can enable auditing for read and change operations in *Space Management* \> *<Your Space\>* \> *Database Access* \> *Database Users* \> *Edit Privileges*. The retention time can be defined per schema.

    > ### Note:  
    > **Data Lake**
    > 
    > Please note, that the statements issued via the execute-procedure for data lake are currently not audited in SAP Datasphere.


As a result, SAP HANA policies are created for the schemas of the space.

The policy names of the SAP Datasphere administered objects are:

-   DWC\_DPP\_<space name\>\_READ

-   DWC\_DPP\_<space name\>\_CHANGE




<a name="loio266553976e1c4db9aaa28a75e2308b77__section_gzv_3kx_rvb"/>

## Disable Audit Logs

When you disable an audit policy for a space or for a database user \(open SQL schema\), all related audit log entries are deleted.

> ### Note:  
> You can keep the audit log entries generated for your space by exporting them before the space is deleted.



<a name="loio266553976e1c4db9aaa28a75e2308b77__section_js3_ylk_k2c"/>

## Export Audit Logs

If you want to keep the audit log entries generated for your space, you can export them before they are automatically deleted by these actions: deleting a space, deleting a database user \(open SQL schema\), disabling an audit policy for a space, disabling an audit policy for a database user \(open SQL schema\) and unassigning an HDI container from a space.

To export audit log entries using the SAP HANA Database Explorer, follow these steps:

1.  Expose for consumption the view containing the audit log entries that you want to export. See [Exposing Data For Consumption](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/40ec77ec24f244279a81448969a7e769.html "Data can only be accessed outside of your SAP Datasphere space if it is exposed for consumption.") :arrow_upper_right:.
2.  Create a database user in your space. See [Create a Database User](Integrating-Data-Via-Database-Users/Open-SQL-Schema/create-a-database-user-798e3fd.md)

3.  Connect to your Open SQL schema with SAP HANA database explorer. See [Connect to Your Open SQL Schema](Integrating-Data-Via-Database-Users/Open-SQL-Schema/connect-to-your-open-sql-schema-b78ad20.md)

4.  Export the data. See [Export Schemas, Tables, and Other Catalog Objects](https://help.sap.com/docs/SAP_HANA_COCKPIT/e8d0ddfb84094942a9f90288cd6c05d3/1f20a6c4364c4b0680596e74e4ba281d.html) in the *SAP HANA Database Explorer* guide.


**Related Information**  


[Monitor Database Operations with Audit Logs](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/110404abd2d044008102c871b39fdf65.html "Monitor the read and change actions (policies) performed in the database with audit logs, and see who did what and when.") :arrow_upper_right:

[Delete Your Space](delete-your-space-3eb19b9.md "Delete a space if you are sure that you no longer need any of its content or data. The space is moved to the recycle bin, from which it can either be restored or permanently deleted from the database.")

