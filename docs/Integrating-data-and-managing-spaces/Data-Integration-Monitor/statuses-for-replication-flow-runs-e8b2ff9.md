<!-- loioe8b2ff93d60b41caa3837ecf9c59689e -->

# Statuses for Replication Flow Runs

Learn more about the possible statuses of replication flow runs and what actions you can take for each of these statuses.

On the left of the monitoring screen, you find the aggregated status information for your replication flow. If the status for one or more objects in a run differs from the overall status, this is indicated by an additional status value in brackets. The following list shows the statuses that can occur and describes the actions you can take:

-   `Running`: For initial load, this status means that the replication flow run is in process for at least one object, while some objects may already be completed. No errors or issues have occurred, no user interaction is required.

    For delta runs, this status means that the run is active and either in the process of replicating or ready to replicate changes that are made in the source.

    > ### Note:  
    > You can stop a running replication flow, however you need to be aware of the consequences. For more information, see [Stopping a Replication Flow Run](stopping-a-replication-flow-run-9819e23.md).

    > ### Note:  
    > As long as the status is `Running`, you cannot start another run for the same replication flow.

-   `Running (Partial)`: The replication flow run is in process for at least one object and has encountered errors or has been paused for the other objects.

    Go through the information at object level and the messages on the right of the screen to find out more about errors and how to resolve them.

-   `Running (Paused)`: This status is relevant for delta runs and means that the run itself is still active \(running\) while all its objects are paused.

    You can resume a paused replication flow at any time. For more information, see [Pausing and Resuming a Replication Flow Run](pausing-and-resuming-a-replication-flow-run-a864530.md).

-   `Running (with Errors)`: This status is relevant for delta runs and means that the run itself is still active \(running\) while all its objects have errors.

    Go through the information at object level and the messages on the right of the screen to find out more about errors and how to resolve them.

-   `Failed (Stopped)`: You have stopped the replication flow. For more information about the consequences and about what you can do next, see [Stopping a Replication Flow Run](stopping-a-replication-flow-run-9819e23.md).

-   `Completed`: This status is relevant for initial load and means that the run has been finished successfully for all objects.


