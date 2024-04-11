<!-- loioda62e1ee746448e8bc043e1be4377cbe -->

# Working With Existing Replication Flow Runs

You can pause a replication flow run and resume it at a later point in time, or you can stop it completely.

This topic contains the following sections:

-   [Statuses for Replication Flow Runs](working-with-existing-replication-flow-runs-da62e1e.md#loioda62e1ee746448e8bc043e1be4377cbe__section_ReplFlow_RunStatuses) 
-   [Scheduling a Replication Flow](working-with-existing-replication-flow-runs-da62e1e.md#loioda62e1ee746448e8bc043e1be4377cbe__section_ReplFlow_Scheduling) 
-   [Pausing and Resuming a Replication Flow Run](working-with-existing-replication-flow-runs-da62e1e.md#loioda62e1ee746448e8bc043e1be4377cbe__section_ReplFlow_Pausing) 
-   [Stopping a Replication Flow Run](working-with-existing-replication-flow-runs-da62e1e.md#loioda62e1ee746448e8bc043e1be4377cbe__section_ReplFlow_Stopping) 
-   [Removing Replication Objects from a Running Replication Flow](working-with-existing-replication-flow-runs-da62e1e.md#loioda62e1ee746448e8bc043e1be4377cbe__section_ReplFlow_RemovingObjects) 



<a name="loioda62e1ee746448e8bc043e1be4377cbe__section_ReplFlow_RunStatuses"/>

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

-   `Failed (Locked)`: A parallel flow is already running for this object. As you cannot have several flows running on the same objects, the first flow will continue running and the other ones will get the status *Failed \(Locked\)*.

-   `Completed`: This status is relevant for initial load and means that the run has been finished successfully for all objects.




<a name="loioda62e1ee746448e8bc043e1be4377cbe__section_ReplFlow_Scheduling"/>

## Scheduling a Replication Flow

You create a schedule for your replication flow and include your replication flow in a task chain if all objects in it have load type *Initial Only*. For more information, see [Schedule a Data Integration Task \(Simple Schedule\)](schedule-a-data-integration-task-simple-schedule-7c11059.md) and [Creating a Task Chain](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/d1afbc2b9ee84d44a00b0b777ac243e1.html "Group multiple tasks into a task chain and run them manually once, or periodically, through a schedule. You can create linear task chains in which one task is run after another. (You can also nest other task chains within a task chain.) Or, you can create task chains in which individual tasks are run in parallel and successful continuation of the entire task chain run depends on whether ANY or ALL parallel tasks are completed successfully. In addition, when creating or editing a task chain, you can also set up email notification for deployed task chains to notify selected users of task chain completion.") :arrow_upper_right:.



<a name="loioda62e1ee746448e8bc043e1be4377cbe__section_ReplFlow_Pausing"/>

## Pausing and Resuming a Replication Flow Run

You may want to pause a replication flow run, for example, while a system update is running. When you do so, the flow is stopped in SAP Datasphere, but not in the source. Consequently, the system still keeps track of changes in the source, but does copy them to the target.

> ### Note:  
> If you have many data changes in your source, and if you pause the replication flow for a longer time \(such as several hours\), the logging tables can become quite big.

To pause a replication flow that has a **schedule**, you need to pause the schedule. \(Pausing the replication flow run itself is not possible in this case.\)

When you resume the flow, the system replicates all source data changes that happened while the replication flow was paused, which means that the first replication flow run after a pause can take considerably longer than usual.



<a name="loioda62e1ee746448e8bc043e1be4377cbe__section_ReplFlow_Stopping"/>

## Stopping a Replication Flow Run

If you do so, the flow run is stopped permanently in SAP Datasphere as well as in the source. You can still run it again, but it will then start from scratch \(rather then from where it left off when you stopped it\). If you stop a replication flow run because you don't need it anymore, you should also delete it so that it does not clutter your system. For more information, see [Deleting a Replication Flow](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/bdd81ec3fb144bdab7d3a7dc25947efe.html "You can delete a replication flow if you do not need it anymore and thus free up capacity.") :arrow_upper_right:.



<a name="loioda62e1ee746448e8bc043e1be4377cbe__section_ReplFlow_RemovingObjects"/>

## Removing Replication Objects from a Running Replication Flow

You can remove individual replication objects from a running replication flow without stopping the replication flow run. To do so, choose the *Remove* button to the right of each object you want to remove, then deploy the flow once again. The relevant objects are then no longer replicated. Any data for the removed objects that already exists in the target \(from previous runs\) remains as-is.

