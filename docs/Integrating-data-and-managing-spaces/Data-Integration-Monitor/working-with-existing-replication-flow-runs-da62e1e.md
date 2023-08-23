<!-- loioda62e1ee746448e8bc043e1be4377cbe -->

# Working With Existing Replication Flow Runs

You can pause a replication flow run and resume it at a later point in time, or you can stop it completely.



<a name="loioda62e1ee746448e8bc043e1be4377cbe__section_awz_hrj_3yb"/>

## Statuses for Replication Flow Runs

On the left of the monitoring screen, you find the aggregated status information for your replication flow. If the status for one or more objects in a run differs from the overall status, this is indicated by an additional status value in brackets. The following list shows the statuses that can occur and describes the actions you can take:

-   `Running`: For initial load, this status means that the replication flow run is in process for at least one object, while some objects may already be completed. No errors or issues have occurred, no user interaction is required.

    For delta runs, this status means that the run is active and either in the process of replicating or ready to replicate changes that are made in the source.

    > ### Note:  
    > You can stop a running replication flow, however you need to be aware of the consequences. For more information, see below under Stopping a Replication Flow Run.

    > ### Note:  
    > As long as the status is `Running`, you cannot start another run for the same replication flow.

-   `Running (Partial)`: The replication flow run is in process for at least one object and has encountered errors or has been paused for the other objects.

    Go through the information at object level and the messages on the right of the screen to find out more about errors and how to resolve them.

-   `Running (Paused)`: This status is relevant for delta runs and means that the run itself is still active \(running\) while all its objects are paused.

    You can resume a paused replication flow at any time. For more information, see below under Pausing and Resuming a Replication Flow.

-   `Running (with Errors)`: This status is relevant for delta runs and means that the run itself is still active \(running\) while all its objects have errors.

    Go through the information at object level and the messages on the right of the screen to find out more about errors and how to resolve them.

-   `Failed (Stopped)`: You have stopped the replication flow. For more information about the consequences and about what you can do next, see below under Stopping a Replication Flow Run.

-   `Completed`: This status is relevant for initial load and means that the run has been finished successfully for all objects.




<a name="loioda62e1ee746448e8bc043e1be4377cbe__section_opk_mrj_3yb"/>

## Pausing and Resuming a Replication Flow Run

You may want to pause a replication flow run, for example, while a system update is running. When you do so, the flow is stopped in SAP Datasphere, but not in the source. Consequently, the system still keeps track of changes in the source, but does copy them to the target.

> ### Note:  
> If you have many data changes in your source, and if you pause the replication flow for a longer time \(such as several hours\), the logging tables can become quite big.

When you resume the flow, the system replicates all source data changes that happened while the replication flow was paused, which means that the first replication flow run after a pause can take considerably longer than usual.



<a name="loioda62e1ee746448e8bc043e1be4377cbe__section_v3v_prj_3yb"/>

## Stopping a Replication Flow Run

If you do so, the flow run is stopped permanently in SAP Datasphere as well as in the source. You can still run it again, but it will then start from scratch \(rather then from where it left off when you stopped it\). If you stop a replication flow run because you don't need it anymore, you should also delete it so that it does not clutter your system. For more information, see [Deleting a Replication Flow](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/bdd81ec3fb144bdab7d3a7dc25947efe.html "You can delete a replication flow if you do not need it anymore and thus free up capacity.") :arrow_upper_right:.

