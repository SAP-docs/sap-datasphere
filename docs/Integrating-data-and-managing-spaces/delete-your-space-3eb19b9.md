<!-- loio3eb19b96e6ba41dfbffd759c5c8370bb -->

# Delete Your Space

Delete a space if you are sure that you no longer need any of its content or data. The space is moved to the recycle bin, from which it can either be restored or permanently deleted from the database.



<a name="loio3eb19b96e6ba41dfbffd759c5c8370bb__section_bzq_m3j_42c"/>

## Prerequisites

To move your space to the *Recycle Bin* area, you must have a scoped role that grants you access to your space with the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Spaces* \(`-RUD----`\) - To open, update and delete your space in the *Space Management* tool.
-   *Space Files* \(`-R------`\) - To view objects in your space.
-   *Scoped Role User Assignment* \(`-------M`\) - To manage the users who can access your space.

The *DW Space Administrator* role template, for example, grants these privileges. For more information, see [Privileges and Permissions](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/d7350c6823a14733a7a5727bad8371aa.html "A privilege represents a task or an area in SAP Datasphere and can be assigned to a specific role. The actions that can be performed in the area are determined by the permissions assigned to a privilege.") :arrow_upper_right: and [Standard Roles Delivered with SAP Datasphere](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/a50a51d80d5746c9b805a2aacbb7e4ee.html "SAP Datasphere is delivered with several standard roles. A standard role includes a predefined set of privileges and permissions.") :arrow_upper_right:. 

> ### Note:  
> Before deleting your space, you may want to:
> 
> -   Export the data contained in your space \(see [Export Your Space Data](export-your-space-data-27c7761.md)\).
> 
> -   Export the audit log entries generated for your space \(see [Logging Read and Change Actions for Audit](logging-read-and-change-actions-for-audit-2665539.md)\).

> ### Note:  
> For spaces that have been deleted before version 2023.05, all related audit logs have been kept. A user with an administrator role can decide to delete them \(see [Delete Audit Logs](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/589fa4251db74fb7955eeee5d86fc25c.html "Delete audit logs and free up disk storage.") :arrow_upper_right: \).



<a name="loio3eb19b96e6ba41dfbffd759c5c8370bb__section_scx_lmz_dcc"/>

## Procedure

> ### Note:  
> If your space contains replication flows with objects of load type “Initial and Delta”, you should make sure that these replication flows are stopped before you delete the space. If you restore the space at a later point in time, the replication flows can then be started again. For more information about replication flows, see [Working With Existing Replication Flow Runs](Data-Integration-Monitor/working-with-existing-replication-flow-runs-da62e1e.md).

1.  In the side navigation area, click ![](Integrating-Data-Via-Database-Users/Open-SQL-Schema/images/Space_Management_a868247.png) \(*Space Management*\).

2.  Locate and select your space, and click the *Delete* button.

3.  In the confirmation message, enter DELETE if you are sure that you no longer need any of its content or data, then click the *Delete* button.

    The space is moved to the *Recycle Bin* area. From the *Recycle Bin*, a user with an administrator role can either restore the space or permanently delete the space from the database to recover the disk storage used by the data in the space \(see [Restore Spaces from, or Empty the Recycle Bin](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/c4e26c09325a45d3ab7011a600c8fc6c.html "Restore spaces, or delete them from the Recycle Bin to recover the disk storage used by the data in spaces.") :arrow_upper_right:\).

    > ### Note:  
    > The *Recycle Bin* is only visible and accessible to users with an administrator role.


Once the space is in the *Recycle Bin*:

-   You cannot edit the deleted space.
-   As data is not deleted, the space still consumes disk storage.
-   Data integration tasks and schedules \(including those for elastic compute nodes\) are paused.
-   The deleted space is removed from the elastic compute nodes it was included in. If an elastic compute node is in a running state, you can stop the run and restart it again so that replicated data is removed from the node.
-   The database users/Open SQL schemas and HDI containers of the deleted space are disabled.
-   For remote tables connected via SAP HANA smart data access, with real-time replication, data replication is stopped and data is removed.
-   For remote tables connected via SAP HANA smart data integration, real-time replication is stopped.
-   You cannot create a new space with the ID of a space that is in the recycle bin. If you want to delete a space and recreate it with the same ID, you must first delete the space from the recycle bin \(see [Restore Spaces from, or Empty the Recycle Bin](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/c4e26c09325a45d3ab7011a600c8fc6c.html "Restore spaces, or delete them from the Recycle Bin to recover the disk storage used by the data in spaces.") :arrow_upper_right:\).
-   A database analysis user can still access the deleted space. For more information on a database analysis user, see [Create a Database Analysis User to Debug Database Issues](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/c28145bcb76c4415a1ec6265dd2a4c11.html "Database analysis users are SAP HANA Cloud database users who have read-only access to all space schemas, and all their activities are recorded in audit logs. You create a database user to monitor, analyze, trace, or debug your SAP Datasphere database, and resolve a specific database issue.") :arrow_upper_right:.

