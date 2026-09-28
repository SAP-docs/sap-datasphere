<!-- loio9bf0d46d6e3c4bd98537e31ec34521a3 -->

# Delete Spaces

Delete a space if you are sure that you no longer need any of its content or data. The space is moved to the recycle bin, from which it can either be restored or permanently deleted from the database.



## Prerequisites

To delete spaces, which will be automatically moved to the *Recycle Bin*, you must have either:


<table>
<tr>
<td valign="top">

A global role that allows you to delete any space, by granting you the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Spaces* \(`-------M`\) - To manage and delete spaces in the *Space Management* tool.
-   *Space Files* \(`-------M`\) - To view objects and data in all spaces.
-   *User* \(`-------M`\) - To manage user access to spaces.

The *DW Administrator* role template, for example, grants these privileges.

</td>
<td valign="top">

A scoped role that grants you access to the space to delete with the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Spaces* \(`-RUD----`\) - To open, update and delete your space in the *Space Management* tool.
-   *Space Files* \(`-R------`\) - To view objects in your space.
-   *Scoped Role User Assignment* \(`-------M`\) - To manage the users who can access your space.

The *DW Space Administrator* role template, for example, grants these privileges.

</td>
</tr>
</table>

For more information, see [Privileges and Permissions](../Managing-Users-and-Roles/privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](../Managing-Users-and-Roles/standard-roles-delivered-with-sap-datasphere-a50a51d.md). 



<a name="loio9bf0d46d6e3c4bd98537e31ec34521a3__section_scx_lmz_dcc"/>

## Procedure

1.  Prepare your space for deletion.
    -   If a space contains replication flows with objects of load type “Initial and Delta”, you should make sure that these replication flows are stopped before you delete the space. If you restore the space at a later point in time, the replication flows can then be started again. For more information about replication flows, see [Working With Existing Replication Flow Runs](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/da62e1ee746448e8bc043e1be4377cbe.html "You can pause a replication flow run and resume it later, or stop it completely when it's no longer needed. You can also schedule, monitor premium outbound volume, and configure email notifications for replication flow failures. For more information on how to make changes to an existing replication flow in the Data Builder, see .") :arrow_upper_right:.
    -   Before deleting your space, you may want to:
        -   Export the data contained in your space \(see [Export Your Space Data](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/27c7761eaef44a6da4e3ae6bc9acbc90.html "You can export the data contained in your space at any time. For example, you may want to export data before deleting your space.") :arrow_upper_right:\).
        -   Export the audit log entries generated for your space \(see [Logging Read and Change Actions for Audit](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/266553976e1c4db9aaa28a75e2308b77.html "You can enable audit logs for your space so that read and change actions (policies) are recorded. Administrators can then analyze who performed which action at which point in time.") :arrow_upper_right:\).


2.  In the side navigation area, click ![](../images/Space_Management_a868247.png) \(*Space Management*\).

3.  Locate and select your space, and click the *Delete* button.

4.  In the confirmation message, enter DELETE if you are sure that you no longer need any of its content or data, then click the *Delete* button.

    The space is moved to the *Recycle Bin* area, from which you can either restore the space or permanently delete the space from the database to recover the disk storage used by the data in the space \(see [Manage Deleted Spaces in the Recycle Bin](manage-deleted-spaces-in-the-recycle-bin-c4e26c0.md)\).

    > ### Note:  
    > The *Recycle Bin* is only visible and accessible to users with an administrator role.


Once the space is in the *Recycle Bin*:

-   The deleted space cannot be edited.
-   As data is not deleted, the space still consumes disk storage.
-   Data integration tasks and schedules \(including those for elastic compute nodes\) are paused.
-   The deleted space is removed from the elastic compute nodes it was included in. If an elastic compute node is in a running state, you can stop the run and restart it again so that replicated data is removed from the node.
-   The database users/Open SQL schemas and HDI containers of the deleted space are disabled.
-   For remote tables connected via SAP HANA smart data access, with real-time replication, data replication is stopped and data is removed.
-   For remote tables connected via SAP HANA smart data integration, real-time replication is stopped.
-   You cannot create a new space with the ID of a space that is in the recycle bin. If you want to delete a space and recreate it with the same ID, you must first delete the space from the recycle bin \(see [Manage Deleted Spaces in the Recycle Bin](manage-deleted-spaces-in-the-recycle-bin-c4e26c0.md)\).
-   A database analysis user can still access the deleted space. For more information on a database analysis user, see [Create a Database Analysis User to Debug Database Issues](../create-a-database-analysis-user-to-debug-database-issues-c28145b.md).

