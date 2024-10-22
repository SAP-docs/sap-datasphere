<!-- loioa24c71f3ba7548909534d4cb52cefbfc -->

# Editing an Existing Replication Flow

Whether and how you can change the settings for a replication flow depends on several factors.

For target objects in the local repository \(SAP Datasphere\), you can no longer use the mapping function to add columns to your target structure after you save the replication flow. However you can still add columns manually using the table editor. To make the corresponding changes in your replication flow, select the relevant target object and choose *Additional Options* \> *Map to Existing Target Object*. Then deploy and run the replication flow again.

For other target objects, you can use the mapping function to add columns to your target structure. Make sure to redeploy the replication flow when you're done and manually implement the same changes in actual table structure before running the replication flow.

For replication flows that contain objects of type *Initial and Delta* and have the status *Active*, you can add or remove individual replication objects without stopping the replication flow run first. To do so, add or remove objects as required in the data builder, then save and deploy the flow again.

To change the load type, truncate setting, projections, filters, or delta interval for a replication flow in status *Active*, you need to stop the replication flow, make the required changes, deploy the replication flow, and then run it again.

> ### Note:  
> If you change the delta load interval, the replication flow run starts again with an initial load.

For more information, see [Working With Existing Replication Flow Runs](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/da62e1ee746448e8bc043e1be4377cbe.html "You can pause a replication flow run and resume it at a later point in time, or you can stop it completely.") :arrow_upper_right:.

