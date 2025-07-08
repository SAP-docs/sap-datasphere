<!-- loio39c116da4e5a41629040f38a907091ce -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Understanding the Replication Flows Metrics

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

*Operation*

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

*State*

</td>
<td valign="top">

Displays the status of the object replication.

</td>
</tr>
</table>

