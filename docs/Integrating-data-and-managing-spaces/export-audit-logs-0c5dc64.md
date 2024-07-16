<!-- loio0c5dc64a1c684edcb8ab03290d683bc9 -->

# Export Audit Logs

You can export audit log entries before they are deleted.

If you want to keep the audit log entries generated for your space, you can export them before they are automatically deleted by these actions: deleting a space, deleting a database user \(open SQL schema\), disabling an audit policy for a space, disabling an audit policy for a database user \(open SQL schema\) and unassigning an HDI container from a space.

To export audit log entries using the SAP HANA Database Explorer, follow these steps:

1.  Expose for consumption the view containing the audit log entries that you want to export. See [Exposing a View For Consumption](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/40ec77ec24f244279a81448969a7e769.html "When your view is ready, you can make its data available for consumption in SAP Analytics Cloud and other clients, tools, and apps.") :arrow_upper_right:.
2.  Create a database user in your space. See [Create a Database User](Integrating-Data-Via-Database-Users/Open-SQL-Schema/create-a-database-user-798e3fd.md)

3.  Connect to your Open SQL schema with SAP HANA database explorer. See [Connect to Your Open SQL Schema](Integrating-Data-Via-Database-Users/Open-SQL-Schema/connect-to-your-open-sql-schema-b78ad20.md)

4.  Export the data. See [Export Schemas, Tables, and Other Catalog Objects](https://help.sap.com/docs/SAP_HANA_COCKPIT/e8d0ddfb84094942a9f90288cd6c05d3/1f20a6c4364c4b0680596e74e4ba281d.html) in the *SAP HANA Database Explorer* guide.


**Related Information**  


[Enable Audit Logging](enable-audit-logging-2665539.md "You can enable audit logs for your space so that read and change actions (policies) are recorded. Administrators can then analyze who performed which action at which point in time.")

[Delete Your Space](delete-your-space-3eb19b9.md "Delete a space if you are sure that you no longer need any of its content or data.")

