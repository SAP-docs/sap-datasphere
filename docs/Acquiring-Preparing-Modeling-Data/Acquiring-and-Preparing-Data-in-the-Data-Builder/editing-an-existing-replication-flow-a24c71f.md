<!-- loioa24c71f3ba7548909534d4cb52cefbfc -->

# Editing an Existing Replication Flow

You can change all settings for a replication flow as long as you haven't deployed it.

Once you have deployed it, you can no longer use the mapping function to add columns to your target structure. However you can still add columns manually using the table editor.

When a replication flow has run or is currently in status *Running*, you cannot change the load type anymore because data inconsistencies might occur if the source data gets changed while the load type is being changed. You need to stop and delete the existing replication flow and create a new one with the required load type. For background information about the different statuses, see also [Working With Existing Replication Flow Runs](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/da62e1ee746448e8bc043e1be4377cbe.html "You can pause a replication flow run and resume it at a later point in time, or you can stop it completely.") :arrow_upper_right:.

