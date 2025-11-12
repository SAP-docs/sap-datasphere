<!-- loio589fa4251db74fb7955eeee5d86fc25c -->

# Delete Audit Logs

Delete audit logs and free up disk storage.

You can delete audit logs for:

-   Spaces for which auditing is enabled. For each space, you can delete separately all the audit log entries recorded for read operations and all the audit log entries recorded for change operations. All the entries recorded before the date and time you specify are deleted.
-   All read audit logs recorded for all database analysis users. They are grouped together into the audit policy DWC\_ANALYSIS\_USERS\_AUDIT\_ALL.

1.  Go to *System* \> *Configuration* \> *Audit* \> *Audit Log Deletion*.

2.  Select the spaces \(and the audit policy names - read or change\) or the database analysis user audit policy \(DWC\_ANALYSIS\_USERS\_AUDIT\_ALL\) for which you want to delete all audit log entries and click *Delete*.

3.  Select a date and time and click *Delete*.

    All entries that have been recorded before this date and time are deleted.

    Deleting audit logs frees up disk storage, which you can see in the *Disk Storage Used* card in *System Monitor* \> *Dashboard*.


> ### Note:  
> Audit logs are automatically deleted when performing the following actions: deleting a space, deleting a database user \(open SQL schema\), disabling an audit policy for a space, disabling an audit policy for a database user \(open SQL schema\), unassigning an HDI container from a space. Before performing any of these actions, you may want to export the audit log entries, for example by using SAP HANA Database Explorer \(see [Logging Read and Change Actions for Audit](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/266553976e1c4db9aaa28a75e2308b77.html "You can enable audit logs for your space so that read and change actions (policies) are recorded. Administrators can then analyze who performed which action at which point in time.") :arrow_upper_right:\).

