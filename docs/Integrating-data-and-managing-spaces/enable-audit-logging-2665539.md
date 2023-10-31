<!-- loio266553976e1c4db9aaa28a75e2308b77 -->

# Enable Audit Logging

You can enable audit logs for your space so that read and change actions \(policies\) are recorded. Administrators can then analyze who did what and when in the database.



-   Enable audit logs of SAP Datasphere objects for read and change operations on the space level in *Space Management* \> *<Your Space\>* \> *Edit Space* \> *Auditing*. You can set the retention time in days for each audit log policy \(read or change\). The default and minimum retention time is 7 days and the maximum retention time is 10 000 days.

    If audit logs have been enabled, entries of all SAP Datasphere related objects are saved in an SAP HANA audit log. These logs don't include the objects of the database access schemas, like open SQL schemas, for example.

    > ### Note:  
    > If you choose to enable audit logs, be aware that they can consume a large quantity of GB of disk in your SAP Datasphere tenant database, especially when combined with long retention periods. Administrators can delete audit logs when needed, which will free up disk space. For more information, see [Delete Audit Logs](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/589fa4251db74fb7955eeee5d86fc25c.html "Delete audit logs and free up disk space.") :arrow_upper_right:.

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
> If you want to keep the audit log entries generated for your space, you can export them before the space is deleted. For more information, see [Export Audit Logs](export-audit-logs-0c5dc64.md).

**Related Information**  


[Monitor Database Operations with Audit Logs](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/110404abd2d044008102c871b39fdf65.html "Monitor the read and change actions (policies) performed in the database with audit logs, and see who did what and when.") :arrow_upper_right:

