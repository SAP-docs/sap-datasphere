<!-- loio3eb19b96e6ba41dfbffd759c5c8370bb -->

# Delete Your Space

Delete a space if you are sure that you no longer need any of its content or data.

When you delete a space, be aware that the following content will be **permanently** deleted:

-   All objects and data contained in the space.
-   All connections defined in the space.
-   All objects and data contained in any Open SQL schema associated with the space.
-   All audit logs entries generated for the space, including audit log entries related to any Open SQL schema or HDI container associated with the space.

> ### Caution:  
> This action cannot be undone.

> ### Note:  
> For spaces that have been deleted before version 2023.05, all related audit logs have been kept. An administrator can decide to delete them \(see [Delete Audit Logs](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/internal/en-US/589fa4251db74fb7955eeee5d86fc25c.html "Delete audit logs and free up disk space.") :arrow_upper_right: \).

> ### Note:  
> Before deleting your space, you may want to:
> 
> -   Export the data contained in your space. For more information, see the section below.
> 
> -   Export the audit log entries generated for your space. For more information, see [Export Audit Logs](export-audit-logs-0c5dc64.md).

Only administrators can create spaces. Both administrators and space administrators can delete spaces.

1.  In the *Space Management*, either locate and select your space or open your space by clicking *Edit*.
2.  Click *Delete*.
3.  In the confirmation message, enter DELETE if you are sure that you no longer need any of its content or data, then click the *Delete* button.



<a name="loio3eb19b96e6ba41dfbffd759c5c8370bb__section_y3p_3dv_kwb"/>

## Export Data Contained in Your Space

If you want to keep the data contained in your space, you can export the data before you delete the space.

 

To export data using the SAP HANA Database Explorer, follow these steps:

1.  Expose for consumption the views containing the data you want to export. See [Exposing a View For Consumption](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/internal/en-US/40ec77ec24f244279a81448969a7e769.html "To make a view available for consumption in SAP Analytics Cloud and other clients, tools, and apps (including via the public ODATA API), enable the Expose for Consumption switch.") :arrow_upper_right:.
2.  Create a database user in your space. See [Create a Database User](Integrating-Data-Via-Database-Users/Open-SQL-Schema/create-a-database-user-798e3fd.md)

3.  Connect to your Open SQL schema with SAP HANA database explorer. See [Connect to Your Open SQL Schema](Integrating-Data-Via-Database-Users/Open-SQL-Schema/connect-to-your-open-sql-schema-b78ad20.md)

4.  Export the data. See [Export Schemas, Tables, and Other Catalog Objects](https://help.sap.com/docs/SAP_HANA_COCKPIT/e8d0ddfb84094942a9f90288cd6c05d3/1f20a6c4364c4b0680596e74e4ba281d.html) in the *SAP HANA Database Explorer* guide.


