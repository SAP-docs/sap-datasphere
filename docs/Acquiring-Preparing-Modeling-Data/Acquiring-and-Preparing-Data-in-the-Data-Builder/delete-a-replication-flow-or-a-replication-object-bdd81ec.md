<!-- loiobdd81ec3fb144bdab7d3a7dc25947efe -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Delete a Replication Flow, or a Replication Object

You can delete a replication flow if you do not need it anymore and thus free up capacity.

As a general rule, do not delete objects while a replication flow is running. These operations are unsupported and may cause replication failures or data inconsistencies. Pause or stop any running replication flows before starting to delete objects.

To delete a replication object or a target table:

1.  Ensure that the replication object is not running and go to the replication flow editor.
2.  select the replication object, and click Remove.
3.  If the aim was to delete the target table, read the replication object.
4.  From the Flows monitor, restart \(not resume\) the replication object to ensure that previously ingested data will be replicated.



## Delete a Replication Flow

In the Data Builder, select the relevant replication flow and choose <span class="FPA-icons-V3"></span> \(Delete\).

If you delete a running replication flow, the system first stops the flow and then deletes it. However, the recommended approach is to first stop the replication flow by choosing *Stop* and then delete it.

