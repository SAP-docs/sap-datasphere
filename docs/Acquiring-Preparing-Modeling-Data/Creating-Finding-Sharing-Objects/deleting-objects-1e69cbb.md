<!-- loio1e69cbb9a99645cba9c8e241c72e8be3 -->

# Deleting Objects

You can delete objects from SAP Datasphere only if other objects do not depend on them.

For example, if `View 1` consumes `Table 1` and `Table 2` as sources, then you cannot delete either table unless or until you delete `View 1` or modify it so that it consumes other sources instead.

If the object is used by one or more other objects then a dialog listing these dependencies opens, and the deletion is canceled.

> ### Note:  
> If you want to delete a remote table with a data access of *Replicated \(Real-Time\)*, you must ensure that:
> 
> -   The data provisioning agent is connected.
> -   The real-time replication is not paused and is working normally.
> 
> If either of these requirements is not met, you must remove the replicated data before you can delete the remote table.

