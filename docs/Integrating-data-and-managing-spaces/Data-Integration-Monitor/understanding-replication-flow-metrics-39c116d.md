<!-- loio39c116da4e5a41629040f38a907091ce -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Understanding Replication Flow Metrics

Display and analyze the metrics computed while running the replication flow.

When you run a replication flow, you can display the metrics per replication object and analyze them in case of error.

To display the metrics for an object:

1.  Go to *Data Integration Monitor* \> *Flows* monitor.
2.  Select the relevant replication flow and click <span class="SAP-icons-V5"></span> to navigate to the run details of your replication flow.
3.  Select the object you want to display and navigate to the *Metrics* area.

The following metrics are displayed:


<table>
<tr>
<th valign="top">

Metrics

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Duration*

</td>
<td valign="top">

Displays the time spent running the task. For example, *Initial Load Duration*.

</td>
</tr>
<tr>
<td valign="top">

*Operations*

</td>
<td valign="top">

Displays the number of records replicated into SAP Datasphere. For example, *Initial Load Operation* will consider the records loaded at the initial load whereas *Delta Load Operation* will consider delta changes due to insert, update or delete operations.

</td>
</tr>
<tr>
<td valign="top">

*Partitions*

</td>
<td valign="top">

Displays information about the partition: number of partitions created and their statuses.

> ### Note:  
> Click *View Details* to access the details information about each partition. For example, the Correlation ID number of each partition is useful when you want to contact the SAP Support if an error occurred in one partition



</td>
</tr>
<tr>
<td valign="top">

*Start Time*

</td>
<td valign="top">

Displays the time and date when the object replication started.

</td>
</tr>
<tr>
<td valign="top">

*End Time*

</td>
<td valign="top">

Displays the time and date when the object replication ended. For example, *Initial Load End Time*.

</td>
</tr>
<tr>
<td valign="top">

Object Thread Count for Delta Loads

</td>
<td valign="top">

Displays the number of threads that were used for parallel processing during delta load. This option is available for SLT tables, CDS views, and CDS view entities that have load type Initial and Delta or Delta Only.

</td>
</tr>
<tr>
<td valign="top">

*State*

</td>
<td valign="top">

Displays the status of the object replication.

</td>
</tr>
</table>



## Understanding Replication Flow Partition Metrics

When you run a replication flow, you can define how data is partitioned for each replication object. The following tables list the available partition metrics and how each one affects data loading.

1.  Partition Metric States:


    <table>
    <tr>
    <th valign="top">

    Metric State
    
    </th>
    <th valign="top">

    Object Status
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Created
    
    </td>
    <td valign="top">
    
    Created
    
    </td>
    <td valign="top">
    
    Task to replicate objects successfully created.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Target Setting Up
    
    </td>
    <td valign="top">
    
    Initial Running
    
    </td>
    <td valign="top">
    
    Target setup in progress.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Error \(target setup\)
    
    </td>
    <td valign="top">
    
    Error
    
    </td>
    <td valign="top">
    
    The target setup has failed due to an error that must be corrected before you restart the replication flow. Check the detailed log.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Target Setup completed
    
    </td>
    <td valign="top">
    
    Initial Running
    
    </td>
    <td valign="top">
    
    Target setup completed. Waiting in the queue to start source setup.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Source Setting up
    
    </td>
    <td valign="top">
    
    Initial Running
    
    </td>
    <td valign="top">
    
    Source setup in progress.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Error \(source setup\)
    
    </td>
    <td valign="top">
    
    Error
    
    </td>
    <td valign="top">
    
    The source setup has failed due to an error.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Setup Completed
    
    </td>
    <td valign="top">
    
    Initial Running
    
    </td>
    <td valign="top">
    
    Source setup completed. Waiting in the queue to start initial partitioning.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Partitioning Initial Load
    
    </td>
    <td valign="top">
    
    Initial Running
    
    </td>
    <td valign="top">
    
    Initial load partition is in progress.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Partitioning Initial Load
    
    </td>
    <td valign="top">
    
    Retrying
    
    </td>
    <td valign="top">
    
    Retrying to load initial partitions as the previous attempt could not be completed successfully, even though some partitions could have already been processed.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Error \(for initial load partition\)
    
    </td>
    <td valign="top">
    
    Error
    
    </td>
    <td valign="top">
    
    Initial load partition has failed due to an error.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Transferring Initial Load
    
    </td>
    <td valign="top">
    
    Initial Running
    
    </td>
    <td valign="top">
    
    Initial load partition is complete, and data is currently transferring in the target.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Error \(for Transferring initial load\)
    
    </td>
    <td valign="top">
    
    Initial Running
    
    </td>
    <td valign="top">
    
    Transferring initial data failed because one or more partitions have encountered an error. Please check the error messages of partitions.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    All initial Load Partitions Completed
    
    </td>
    <td valign="top">
    
    Initial Running
    
    </td>
    <td valign="top">
    
    All initial partitions are transferred to the target system. Waiting in queue to notify the target that the initial load task is complete.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Notifying source initial-load-done
    
    </td>
    <td valign="top">
    
    Initial Running
    
    </td>
    <td valign="top">
    
    Work order is notifying the source that the initial load task is complete.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Notifying source initial-load-done
    
    </td>
    <td valign="top">
    
    Retrying
    
    </td>
    <td valign="top">
    
    Retrying to notify the source that the initial load task is completed. The last attempt was not successful because of an error.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Error
    
    </td>
    <td valign="top">
    
    Error
    
    </td>
    <td valign="top">
    
    Notifying the source that the initial load task is complete has failed due to an error.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Source Notification Completed for Initial-load-done
    
    </td>
    <td valign="top">
    
    Initial Running
    
    </td>
    <td valign="top">
    
    The notification that the initial load task is complete has been sent to the source successfully.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Notifying Target Initial-load-done
    
    </td>
    <td valign="top">
    
    Initial Running
    
    </td>
    <td valign="top">
    
    Worker order is notifying the target that the initial load task is complete.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Notifying Target Initial-load-done
    
    </td>
    <td valign="top">
    
    Retrying
    
    </td>
    <td valign="top">
    
    Retrying to notify the target that the initial load task is complete. The last attempt was not successful because of an error.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Error
    
    </td>
    <td valign="top">
    
    Error
    
    </td>
    <td valign="top">
    
    The target cannot be notified that the initial load task is complete because of an error.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Completed Initial Load
    
    </td>
    <td valign="top">
    
    Delta\_Running
    
    </td>
    <td valign="top">
    
    Initial load completed. Waiting in queue to start delta load partitioning.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Completed \(for initial load\)
    
    </td>
    <td valign="top">
    
    Completed
    
    </td>
    <td valign="top">
    
    Initial load completed.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Partitioning Delta Load
    
    </td>
    <td valign="top">
    
    Delta\_Running
    
    </td>
    <td valign="top">
    
    Delta load partitioning is in progress.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Partitioning Delta Load
    
    </td>
    <td valign="top">
    
    Retrying
    
    </td>
    <td valign="top">
    
    Retrying for delta load partitioning. The last attempt was not successful because of an error.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Error \(for partitioning delta load\)
    
    </td>
    <td valign="top">
    
    Error
    
    </td>
    <td valign="top">
    
    Delta load partitioning has failed.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Transferring Delta Load
    
    </td>
    <td valign="top">
    
    Delta\_Running
    
    </td>
    <td valign="top">
    
    Delta load partitioning is in progress.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Transferring Delta Load
    
    </td>
    <td valign="top">
    
    Retrying
    
    </td>
    <td valign="top">
    
    Retrying for transferring delta data. The previous attempt was not successful.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Error \(for transferring delta load\)
    
    </td>
    <td valign="top">
    
     
    
    </td>
    <td valign="top">
    
    Transferring delta data failed because one or more partitions have encountered an error. Please check the error messages of partitions.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Removing
    
    </td>
    <td valign="top">
    
     
    
    </td>
    <td valign="top">
    
    Waiting in queue to start cleanup of source replication artifacts.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Source Tearing Down
    
    </td>
    <td valign="top">
    
     
    
    </td>
    <td valign="top">
    
    Cleanup of source replication artifacts is in progress.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Source Tearing Down
    
    </td>
    <td valign="top">
    
    Retrying
    
    </td>
    <td valign="top">
    
    Retrying to clean up the source replication artifacts. The previous attempt was not successful.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Error \(for source tearing down\)
    
    </td>
    <td valign="top">
    
     
    
    </td>
    <td valign="top">
    
    Cleanup of source replication artifacts failed due an error.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Compiling Objects
    
    </td>
    <td valign="top">
    
     
    
    </td>
    <td valign="top">
    
    Compiling objects is in progress.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Compiling Objects
    
    </td>
    <td valign="top">
    
    Retrying
    
    </td>
    <td valign="top">
    
    Retrying to compile objects. The previous attempt was not successful.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Error \(for compiling object\)
    
    </td>
    <td valign="top">
    
     
    
    </td>
    <td valign="top">
    
    Compiling objects failed due to an error.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Object Compilation Completed
    
    </td>
    <td valign="top">
    
     
    
    </td>
    <td valign="top">
    
    Compiling objects is completed.
    
    </td>
    </tr>
    </table>
    
2.  Partition Information:


    <table>
    <tr>
    <th valign="top">

    Partition Information
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Partition ID
    
    </td>
    <td valign="top">
    
    Number that uniquely identifies the partition.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Transfer Mode
    
    </td>
    <td valign="top">
    
    How the data is loaded \(initial or delta\).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Correlation ID
    
    </td>
    <td valign="top">
    
    Number that uniquely identifies the partition \(to be provided to the support in case of any issues\).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Status
    
    </td>
    <td valign="top">
    
    Partition status.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Last Data Transferred At
    
    </td>
    <td valign="top">
    
    The last time data was loaded.
    
    </td>
    </tr>
    </table>
    
3.  Partition Statuses:


    <table>
    <tr>
    <th valign="top">

    Status
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Ready
    
    </td>
    <td valign="top">
    
    Waiting in queue to start.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Transferring
    
    </td>
    <td valign="top">
    
    Transferring data or retrying data transfer.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Completed
    
    </td>
    <td valign="top">
    
    Load is complete.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Error
    
    </td>
    <td valign="top">
    
    Error while loading the partition.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    PurgeReady
    
    </td>
    <td valign="top">
    
    Waiting in line to clean up log.
    
    </td>
    </tr>
    </table>
    
4.  Retry Information:


    <table>
    <tr>
    <th valign="top">

    Retry Information
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    First Retry Started
    
    </td>
    <td valign="top">
    
    Timestamp for first retry.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Latest Retry
    
    </td>
    <td valign="top">
    
    Status of last retry.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Total Retry Count
    
    </td>
    <td valign="top">
    
    Total number of retries.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Retry Count for Latest Retry Reason
    
    </td>
    <td valign="top">
    
    Total number of retries for the same reason.
    
    </td>
    </tr>
    </table>
    
5.  Retry Log:


    <table>
    <tr>
    <th valign="top">

    Retry Log
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Reason
    
    </td>
    <td valign="top">
    
    Reason for the retry.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Past Retries
    
    </td>
    <td valign="top">
    
    Number of previous retries.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Last Retry Started
    
    </td>
    <td valign="top">
    
    When the last retry action started.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Last Retry End
    
    </td>
    <td valign="top">
    
    When the last retry action ended.
    
    </td>
    </tr>
    </table>
    
6.  Retry Reasons:


    <table>
    <tr>
    <th valign="top">

    Reason
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    ACCEPTED
    
    </td>
    <td valign="top">
    
    The source connector has accepted the load request.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    PARTIAL\_RESULT
    
    </td>
    <td valign="top">
    
    Partial source partitions are available. The remaining partitioning is in progress.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    OTHER\_WORK\_ ORDER\_TIMEOUT
    
    </td>
    <td valign="top">
    
    The last attempt was unsuccessful because the worker process was shut down as one of the work orders timed out after 12 minutes. Another retry will happen.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    GRAPH\_TIMEOUT
    
    </td>
    <td valign="top">
    
    The last attempt was unsuccessful because the worker process was timed out in 1O minutes. Another retry will happen.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    GRAPH\_ABORTED
    
    </td>
    <td valign="top">
    
    The last attempt was not successful because the worker process terminated unexpectedly.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    TENANT\_UPGRADE
    
    </td>
    <td valign="top">
    
    The last attempt was not successful because the worker process terminated due to a service upgrade.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    ERROR
    
    </td>
    <td valign="top">
    
    The last attempt failed because of an error.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    DATA\_NOT\_READY
    
    </td>
    <td valign="top">
    
    The data is currently not available for loading, or no new delta data to load. A new check will be done later.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    DATA\_AVAILABLE\_NOT\_READY\_FOR\_TRANSFER
    
    </td>
    <td valign="top">
    
    The source data is available, but the connector is unable to retrieve or dispatch the data. There can be different reasons why the data is not ready: the buffer is empty as data is being written at the moment, the package creation has failed, “the package is too large," or there is an out-of-memory error. For more information, see the SAP Note [3703424](https://me.sap.com/notes/3703424) 
    
    </td>
    </tr>
    </table>
    

