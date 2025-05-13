<!-- loioc4e26c09325a45d3ab7011a600c8fc6c -->

# Restore Spaces from, or Empty the Recycle Bin

Restore spaces, or delete them from the *Recycle Bin* to recover the disk storage used by the data in spaces.

This topic contains the following sections:

-   [Restore a Space](restore-spaces-from-or-empty-the-recycle-bin-c4e26c0.md#loioc4e26c09325a45d3ab7011a600c8fc6c__section_qjv_qnz_dcc)
-   [Delete a Space Permanently](restore-spaces-from-or-empty-the-recycle-bin-c4e26c0.md#loioc4e26c09325a45d3ab7011a600c8fc6c__section_vqc_dkz_dcc)

Once a space has been deleted and moved to the *Recycle Bin* \(see [Delete Your Space](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/3eb19b96e6ba41dfbffd759c5c8370bb.html "Delete a space if you are sure that you no longer need any of its content or data. The space is moved to the recycle bin, from which it can either be restored or permanently deleted from the database.") :arrow_upper_right:\), you can either restore the space or permanently delete the space from the database to recover the disk storage used by the data in the space.



<a name="loioc4e26c09325a45d3ab7011a600c8fc6c__section_qjv_qnz_dcc"/>

## Restore a Space

1.  In the side navigation area, click ![](../images/Space_Management_a868247.png) \(*Space Management*\).

2.  In the *Recycle Bin* area, locate and select your space and click the *Restore* button.

    The space is moved to the *All Spaces* area and you can work with it.

    > ### Note:  
    > Once a space is restored, its status is "active", regardless of the status the space had before deletion \(active or locked\).


As the following actions are not automatically done with the space restore, you can perform them manually:

-   Resume the schedules that were paused.
-   Run the replication for remote tables connected via SAP HANA smart data access, with real-time replication, and for replication flows with the load type "Initial and Delta" \(see [Replicating Data and Monitoring Remote Tables](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/4dd95d7bff1f48b399c8b55dbdd34b9e.html "In the Remote Tables monitor, you can find a remote table monitor per space. Here, you can copy data from remote tables that have been deployed in your space into SAP Datasphere, and you can monitor the replication of the data. You can copy or schedule copying the full set of data from the source, or you can set up replication of data changes in real-time via change data capturing (CDC).") :arrow_upper_right:\).
-   Re-enable real-time replication for remote tables connected via SAP HANA smart data integration, with real-time replication \(see [Replicating Data and Monitoring Remote Tables](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/4dd95d7bff1f48b399c8b55dbdd34b9e.html "In the Remote Tables monitor, you can find a remote table monitor per space. Here, you can copy data from remote tables that have been deployed in your space into SAP Datasphere, and you can monitor the replication of the data. You can copy or schedule copying the full set of data from the source, or you can set up replication of data changes in real-time via change data capturing (CDC).") :arrow_upper_right:\).
-   If replication flows were stopped before the space was deleted, ensure that they get started again \(see [Working With Existing Replication Flow Runs](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/da62e1ee746448e8bc043e1be4377cbe.html "You can pause a replication flow run and resume it at a later point in time, or you can stop it completely.") :arrow_upper_right:\).
-   Synchronize the source system with the catalog \(see [Manually Synchronizing a System](https://help.sap.com/viewer/97d1d2f0e35d410c893e95a5ff3bee6f/DEV_CURRENT/en-US/48c11915d74b41fcb8c07dd4bf1c4c86.html "After you create a connection to a source system, you'll want to manually synchronize it with the catalog to ensure that existing objects from the new source system are added as assets to the catalog. You may also need to manually synchronize existing source systems for specific situations, such as troubleshooting synchronization issues or reauthenticating the system user.") :arrow_upper_right:\).



<a name="loioc4e26c09325a45d3ab7011a600c8fc6c__section_vqc_dkz_dcc"/>

## Delete a Space Permanently

> ### Caution:  
> This action cannot be undone.

Be aware that the following content will also be **permanently** deleted:

-   All objects and data contained in the space.
-   All connections defined in the space.
-   All objects and data contained in any Open SQL schema associated with the space.
-   All audit logs entries generated for the space, including audit log entries related to any Open SQL schema associated with the space.

    > ### Note:  
    > For spaces that have been deleted before version 2023.05, all related audit logs have been kept. A user with an administrator role can decide to delete them \(see [Delete Audit Logs](../Monitoring-SAP-Datasphere/delete-audit-logs-589fa42.md) \).


1.  In the side navigation area, click ![](../images/Space_Management_a868247.png) \(*Space Management*\).

2.  In the *Recycle Bin* area, locate and select one or more spaces and click the *Delete* button.

3.  In the confirmation message, enter DELETE if you are sure that you no longer need the spaces and any of their content or data, then click the *Delete* button.

    The spaces are permanently deleted from the database and cannot be recovered.

    > ### Note:  
    > When you delete a file space, it can take more than 5 minutes and a timeout message from your browser might be displayed even though the space is being properly deleted. To make sure that your space has been permanently deleted, you can check later that it is no more in the recycle bin.


