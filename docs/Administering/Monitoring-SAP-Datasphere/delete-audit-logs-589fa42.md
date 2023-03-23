<!-- loio589fa4251db74fb7955eeee5d86fc25c -->

# Delete Audit Logs

Delete audit logs and free up disk space.

All spaces for which auditing is enabled, are listed in the *Audit Log Deletion* area.

For each space, you can delete separately all the audit log entries recorded for read operations and all the audit log entries recorded for change operations. All the entries recorded before the date and time you specify are deleted.

1.  Go to *System* \> *Configuration* \> *Audit*.

2.  Select the spaces and the audit policy names \(read or change\) for which you want to delete all audit log entries and click *Delete*.

3.  Select a date and time and click *Delete*.

    All entries that have been recorded before this date and time are deleted.

    Deleting audit logs frees up disk space, which you can see in the *Used Disk* bar of the *Space Management* page.


> ### Note:  
> Audit logs are automatically deleted when performing the following actions: deleting a space, deleting a database user \(open SQL schema\), disabling an audit policy for a space, disabling an audit policy for a database user \(open SQL schema\), unassigning an HDI container from a space. Before performing any of these actions, you may want to export the audit log entries, for example by using SAP HANA Database Explorer \(see [Export Audit Logs](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/internal/en-US/0c5dc64a1c684edcb8ab03290d683bc9.html "You can export audit log entries before they are deleted.") :arrow_upper_right:\).

