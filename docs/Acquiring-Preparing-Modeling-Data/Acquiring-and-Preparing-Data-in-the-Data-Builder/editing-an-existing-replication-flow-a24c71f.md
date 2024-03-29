<!-- loioa24c71f3ba7548909534d4cb52cefbfc -->

# Editing an Existing Replication Flow

You can change all settings for a replication flow as long as you haven't deployed it.

Once you have deployed it, you can no longer use the mapping function to add columns to your target structure. However you can still add columns manually using the table editor.

You can remove individual replication objects from a running replication flow and then deploy the flow again without stopping it first.

When a replication flow has run or is currently in status *Running*, you cannot change the load type anymore because data inconsistencies might occur if the source data gets changed while the load type is being changed. You need to stop and delete the existing replication flow and create a new one with the required load type.

However it is still possible to change the delta load interval for replication flows that already have load type *Initial and Delta*. To do so, stop the replication flow, change the interval as appropriate \(in the side panel\), deploy the flow, and run it. The replication flow run will then start all over again with an initial load.

For more information, see [Working With Existing Replication Flow Runs](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/da62e1ee746448e8bc043e1be4377cbe.html "You can pause a replication flow run and resume it at a later point in time, or you can stop it completely.") :arrow_upper_right:.

