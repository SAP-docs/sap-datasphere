<!-- loio3eb19b96e6ba41dfbffd759c5c8370bb -->

# Delete Your Space

Delete a space if you are sure that you no longer need any of its content or data.

This topic contains the following sections:

-   [Export Space Data Before Deletion](delete-your-space-3eb19b9.md#loio3eb19b96e6ba41dfbffd759c5c8370bb__section_lk4_xrc_rcc)
-   [Delete Your Space](delete-your-space-3eb19b9.md#loio3eb19b96e6ba41dfbffd759c5c8370bb__section_scx_lmz_dcc)
-   [Restore Your Space](delete-your-space-3eb19b9.md#loio3eb19b96e6ba41dfbffd759c5c8370bb__section_qjv_qnz_dcc)

When you delete a space, the space is moved to the *Recycle Bin* area and can be restored at any time. To recover the disk storage used by the data in a space, the space must be deleted from the *Recycle Bin* \(see [Empty the Recycle Bin](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/c4e26c09325a45d3ab7011a600c8fc6c.html "To recover the disk storage used by the data in spaces, you must delete them from the Recycle Bin area.") :arrow_upper_right:\).

> ### Note:  
> For spaces that have been deleted before version 2023.05, all related audit logs have been kept. An administrator can decide to delete them \(see [Delete Audit Logs](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/589fa4251db74fb7955eeee5d86fc25c.html "Delete audit logs and free up disk space.") :arrow_upper_right: \).

> ### Note:  
> Before deleting your space, you may want to:
> 
> -   Export the data contained in your space \(see [Export Space Data Before Deletion](delete-your-space-3eb19b9.md#loio3eb19b96e6ba41dfbffd759c5c8370bb__section_lk4_xrc_rcc)\).
> 
> -   Export the audit log entries generated for your space \(see [Export Audit Logs](export-audit-logs-0c5dc64.md)\).

Only administrators can create spaces. Both administrators and space administrators can delete spaces.



<a name="loio3eb19b96e6ba41dfbffd759c5c8370bb__section_lk4_xrc_rcc"/>

## Export Space Data Before Deletion

If you want to keep the data contained in your space, you can export the data before you delete the space.



To export data using the SAP HANA Database Explorer, follow these steps:

1.  Expose for consumption the views containing the data you want to export \(see [Exposing Data For Consumption](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/40ec77ec24f244279a81448969a7e769.html "When your view is ready, you can make its data available for consumption in SAP Analytics Cloud and other clients, tools, and apps.") :arrow_upper_right:\).
2.  Create a database user in your space \(see [Create a Database User](Integrating-Data-Via-Database-Users/Open-SQL-Schema/create-a-database-user-798e3fd.md)\).

3.  Connect to your Open SQL schema with SAP HANA database explorer \(see [Connect to Your Open SQL Schema](Integrating-Data-Via-Database-Users/Open-SQL-Schema/connect-to-your-open-sql-schema-b78ad20.md)\).

4.  Export the data \(see [Export Schemas, Tables, and Other Catalog Objects](https://help.sap.com/docs/SAP_HANA_COCKPIT/e8d0ddfb84094942a9f90288cd6c05d3/1f20a6c4364c4b0680596e74e4ba281d.html) in the *SAP HANA Database Explorer* guide\).




<a name="loio3eb19b96e6ba41dfbffd759c5c8370bb__section_scx_lmz_dcc"/>

## Delete Your Space

> ### Note:  
> If your space contains replication flows with objects of load type “Initial and Delta”, you should make sure that these replication flows are stopped before you delete the space. If you restore the space at a later point in time, the replication flows can then be started again. For more information about replication flows, see [Working With Existing Replication Flow Runs](Data-Integration-Monitor/working-with-existing-replication-flow-runs-da62e1e.md).

1.  In the side navigation area, click ![](Integrating-Data-Via-Database-Users/Open-SQL-Schema/images/Space_Management_a868247.png) \(*Space Management*\).

2.  In the *All Spaces* area, locate and select your space and click the *Delete* button.

3.  In the confirmation message, enter DELETE if you are sure that you no longer need any of its content or data, then click the *Delete* button.

    The space is moved to the *Recycle Bin* area until you permanently delete it from the database \(see [Empty the Recycle Bin](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/c4e26c09325a45d3ab7011a600c8fc6c.html "To recover the disk storage used by the data in spaces, you must delete them from the Recycle Bin area.") :arrow_upper_right:\).


Once the space is in the *Recycle Bin*:

-   You cannot edit the deleted space.
-   As data is not deleted, the space still consumes disk storage.
-   Data integration tasks and schedules \(including those for elastic compute nodes\) are paused.
-   The deleted space is removed from the elastic compute nodes it was included in. If an elastic compute node is in a running state, you can stop the run and restart it again so that replicated data is removed from the node.
-   The database users/Open SQL schemas and HDI containers of the deleted space are disabled.
-   For remote tables connected via SAP HANA smart data access, with real-time replication, data replication is stopped and data is removed.
-   For remote tables connected via SAP HANA smart data integration, real-time replication is stopped.
-   You cannot create a new space with the ID of a space that is in the recycle bin. If you want to delete a space and recreate it with the same ID, you must first delete the space from the recycle bin \(see [Empty the Recycle Bin](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/c4e26c09325a45d3ab7011a600c8fc6c.html "To recover the disk storage used by the data in spaces, you must delete them from the Recycle Bin area.") :arrow_upper_right:\).
-   A database analysis user can still access the deleted space. For more information on a database analysis user, see [Create a Database Analysis User to Debug Database Issues](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/c28145bcb76c4415a1ec6265dd2a4c11.html "A database analysis user is an SAP HANA Cloud database user with wide-ranging privileges. It can be used to support monitoring, analyzing, tracing, and debugging of your SAP Datasphere run-time database.") :arrow_upper_right:.



<a name="loio3eb19b96e6ba41dfbffd759c5c8370bb__section_qjv_qnz_dcc"/>

## Restore Your Space

1.  In the side navigation area, click ![](Integrating-Data-Via-Database-Users/Open-SQL-Schema/images/Space_Management_a868247.png) \(*Space Management*\).

2.  In the *Recycle Bin* area, locate and select your space and click the *Restore* button.

    The space is moved to the *All Spaces* area and you can work with it.

    > ### Note:  
    > Once a space is restored, its status is "active", regardless of the status the space had before deletion \(active or locked\).


As the following actions are not automatically done with the space restore, you can perform them manually:

-   Resume the schedules that were paused.
-   Run the replication for remote tables connected via SAP HANA smart data access, with real-time replication, and for replication flows with the load type "Initial and Delta" \(see [Replicating Data and Monitoring Remote Tables](Data-Integration-Monitor/replicating-data-and-monitoring-remote-tables-4dd95d7.md)\).
-   Re-enable real-time replication for remote tables connected via SAP HANA smart data integration, with real-time replication \(see [Replicating Data and Monitoring Remote Tables](Data-Integration-Monitor/replicating-data-and-monitoring-remote-tables-4dd95d7.md)\).
-   If replication flows were stopped before the space was deleted, ensure that they get started again \(see [Working With Existing Replication Flow Runs](Data-Integration-Monitor/working-with-existing-replication-flow-runs-da62e1e.md)\).
-   Synchronize the source system with the catalog \(see [Manually Synchronizing a System](https://help.sap.com/viewer/97d1d2f0e35d410c893e95a5ff3bee6f/DEV_CURRENT/en-US/48c11915d74b41fcb8c07dd4bf1c4c86.html "After you create a connection to a source system, you'll want to manually synchronize it with the catalog to ensure that existing data objects from the new source system will be added as assets to the catalog. You may also need to manually synchronize existing source systems for specific situations, such as troubleshooting synchronization issues or reauthenticating the system user.") :arrow_upper_right:\).

