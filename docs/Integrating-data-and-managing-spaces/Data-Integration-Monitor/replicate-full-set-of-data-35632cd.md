<!-- loio35632cd706474d9796fa5da56ba15c6b -->

# Replicate Full Set of Data

Start a data replication to copy the full set of data from your source object \(usually a database table or view\) into SAP Datasphere.



## Context

Availability of data replication \(snapshot\) depends on the connection type. For more information on which connection types support snapshot replication, see [Integrating Data via Connections](../Integrating-Data-Via-Connections/integrating-data-via-connections-eb85e15.md).

> ### Note:  
> By default, the full set of data is copied and imported in a single background task. For remote tables with larger data volumes, this can lead to out-of-memory errors or high memory peaks. To avoid such situations, you can enable partitioned data transfer of large datasets for supported connection types \(which is all remote table-enabled connections that use a Data Provisioning Agent\). For more information, see [Partitioning Remote Table Data Loads](partitioning-remote-table-data-loads-a218d27.md).



## Procedure

1.  Go to *Data Integration Monitor* and select the space in which the relevant remote table resides.

2.  Go to the *Remote Tables*.

3.  Select the remote table that you want to replicate data for.

4.  When real-time replication has been used before, select *Data Replication* \> *Remove Replicated Data*.

5.  You have two options:


    <table>
    <tr>
    <th valign="top">

    Option
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    **Directly start the replication**
    
    </td>
    <td valign="top">
    
    Select *Data Replication* \> *Start Data Replication*.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Schedule the replication**
    
    </td>
    <td valign="top">
    
    Select *Schedule* \> *Create Schedule*. For more information, see [Schedule a Data Integration Task \(Simple Schedule\)](schedule-a-data-integration-task-simple-schedule-7c11059.md).
    
    </td>
    </tr>
    </table>
    



<a name="loio35632cd706474d9796fa5da56ba15c6b__result_err_prm_h4b"/>

## Results

When you directly start the replication, it starts in the background and you can see the progress of the replication in the replication status. Once the replication has finished, you can see it in the *Status* column. For a successful load, you will see the status *Available* and the date and time of the latest update. The *Frequency* for a replication you started directly is *None*. The changed size of the remote table will also be shown in the monitor.

When you scheduled the replication, the columns *Frequency* and *Next Run* are updated with the scheduling information. You can display the scheduling settings by clicking *Scheduled* in the *Frequency* column.

You can access the detailed logs for the remote table: Select the relevant remote table and click ![](images/Remote_Table_Logs_Button_a6170ee.png)*\(Remote Table Logs\)*.

Once, you start a new data replication \(either directly or via a schedule\) while replicated data already exists, the replicated data in SAP Datasphere is deleted and fully replaced by the new one. .

> ### Note:  
> You can still access the current data until the replication ends. Once replication has successfully run, the data is updated. Please note that this data refresh behavior requires temporarily additional in-memory and disk-storage to be reserved during the processing of a new data replication.

