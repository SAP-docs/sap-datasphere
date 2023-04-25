<!-- loioa24c71f3ba7548909534d4cb52cefbfc -->

# Editing an Existing Replication Flow

You can change all settings for a replication flow as long as you haven't deployed it.

Once you have deployed it, you can no longer use the mapping function to add columns to your target structure. However you can still add columns manually using the table editor.

When a replication flow has run or is currently in status *Running*, you cannot change the load type anymore because data inconsistencies might occur if the source data gets changed while the load type is being changed. You need to stop and delete the existing replication flow and create a new one with the required load type. For background information about the different statuses, see also [Statuses for Replication Flow Runs](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/e8b2ff93d60b41caa3837ecf9c59689e.html "Learn more about the possible statuses of replication flow runs and what actions you can take for each of these statuses.") :arrow_upper_right:.

