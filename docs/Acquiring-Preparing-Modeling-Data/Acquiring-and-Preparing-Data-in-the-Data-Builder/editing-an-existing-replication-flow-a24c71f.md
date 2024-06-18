<!-- loioa24c71f3ba7548909534d4cb52cefbfc -->

# Editing an Existing Replication Flow

You can change all settings for a replication flow as long as you haven't deployed it.

Once you have deployed it, you can no longer use the mapping function to add columns to your target structure. However you can still add columns manually using the table editor.

For replication flows that contain objects of type *Initial and Delta* and have the status *Active*, you can add or remove individual replication objects without stopping the replication flow run first. To do so, add or remove objects as required in the data builder, then save and deploy the flow again.

To change the load type, truncate setting, projections, filters, or delta interval value for a replication flow in status *Active*, you need to stop the replication flow, make the required changes, deploy the replication flow, and then run it again. If you change the delta load interval, the replication flow run starts all over again with an initial load.

For more information, see [Working With Existing Replication Flow Runs](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/da62e1ee746448e8bc043e1be4377cbe.html "You can pause a replication flow run and resume it at a later point in time, or you can stop it completely.") :arrow_upper_right:.

