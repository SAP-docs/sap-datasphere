<!-- loioffa92d9bd29e466f8014df0c36330b81 -->

# Monitoring Elastic Compute Nodes

Administrators can monitor key figures related to an elastic compute node in a dedicated dashboard.

When you create an elastic compute node in the *Space Management* app, a tab dedicated to the node is automatically created in the *System Monitor* app so that you can monitor the key figures related to elastic compute node. See [Create an Elastic Compute Node](../Creating-and-Configuring-Your-Tenant/create-an-elastic-compute-node-99ad61e.md).

The dashboard dedicated to an elastic compute node displays the following widgets:


<table>
<tr>
<th valign="top">

Widget

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Configuration*

</td>
<td valign="top">

Shows the following information about the current elastic compute node:

-   Technical name.

-   Status, such as *Ready* or *Running* \(see [Run an Elastic Compute Node](../Creating-and-Configuring-Your-Tenant/run-an-elastic-compute-node-34b3585.md)\).

-   The performance class and the resources allocated to the node: number of compute blocks, memory, disk storage and number of vCPUs.




</td>
</tr>
<tr>
<td valign="top">

*Run Details* 

</td>
<td valign="top">

Shows the following information about the latest or the previous run of the current elastic compute node:

-   The date and time at which the elastic compute node has started and stopped.

-   The total run duration \(uptime\) from the starting to the stopping phase.

-   The number of block-hours is the numbers of hours that have been consumed by the run. The number of block-hours is the result of the run duration in numbers of hours multiplied by the number of compute blocks. If a node that includes 4 compute blocks runs for 5 hours, 20 block-hours have been consumed. In such a case, the uptime equals the block-hours. If a node that includes 8 compute blocks runs for 5 hours, 40 block-hours have been consumed.




</td>
</tr>
<tr>
<td valign="top">

*Monthly Uptime*

</td>
<td valign="top">

Shows the following information about the elastic compute node runs for the current month or the last month:

-   The total duration \(uptime\) of all runs in the current or last month.

-   The total number of block-hours consumed by all the runs in the current or last month.




</td>
</tr>
<tr>
<td valign="top">

*Average CPU*

</td>
<td valign="top">

Shows the average percentage of the number of vCPUs consumed, during the latest or previous run of the elastic compute node.

The trend icon \(up or down arrow\) indicates if the percentage is higher or lower than the previous run.

To see the real-time average CPU utilization in percentage for the elastic compute note, click *Performance Monitor \(SAP HANA Cockpit\)*, which opens the Performance Monitor page in the SAP HANA Cockpit \(see [The Perfomance Monitor](https://help.sap.com/docs/hana-cloud/sap-hana-cloud-database-administration-with-sap-hana-cockpit/performance-monitor) in the *SAP HANA Cloud Database Administration with SAP HANA Cockpit*\).

</td>
</tr>
<tr>
<td valign="top">

*Average Memory*

</td>
<td valign="top">

Shows the average amount of memory consumed \(in GiB\), during the latest or previous run of the elastic compute node.

The trend icon \(up or down arrow\) indicates if the percentage is higher or lower than the previous run.

To see the real-time average memory utilization in GB for the elastic compute note, click *Performance Monitor \(SAP HANA Cockpit\)*, which opens the Performance Monitor page in the SAP HANA Cockpit \(see [The Perfomance Monitor](https://help.sap.com/docs/hana-cloud/sap-hana-cloud-database-administration-with-sap-hana-cockpit/performance-monitor) in the *SAP HANA Cloud Database Administration with SAP HANA Cockpit*\).

</td>
</tr>
<tr>
<td valign="top">

*Total Uptime*

</td>
<td valign="top">

Shows the total duration in hours of all runs of the elastic compute node.

</td>
</tr>
<tr>
<td valign="top">

*Top 5 Statements by Processing Memory Consumption*

</td>
<td valign="top">

Shows the 5 statements whose memory consumption was the highest during the last run of the elastic compute node.

To see detailed information about the statements, you can click *View Logs*, which takes you to the *Logs* \> *Statements* tab. See [Monitoring SAP Datasphere](monitoring-sap-datasphere-28910cd.md).

</td>
</tr>
<tr>
<td valign="top">

*Out-of-Memory Errors*

</td>
<td valign="top">

Shows the number of out-of-memory errors that have occurred in tasks and statements related to the elastic compute node, during the last run.

To see detailed information about the errors, you can click *View Logs*, which takes you to the *Logs* \> *Statements* tab. See [Monitoring SAP Datasphere](monitoring-sap-datasphere-28910cd.md).

</td>
</tr>
<tr>
<td valign="top">

*Memory Distribution*

</td>
<td valign="top">

Shows the amount of memory allocated to the elastic compute node, broken down between:

-   *Unused Memory* - Shows the amount of memory available for the elastic compute node.

-   *Memory Used for Data Replication* - Shows the amount of memory used to store replicated data for the elastic compute node.

-   *Memory Used for Processing* - Shows the amount of memory used by the processes that are currently running for the elastic compute node. For example: consumption of the queries running on the elastic compute node.




</td>
</tr>
</table>

You can also perform the following actions from a dashboard dedicated to an elastic compute node:

-   Refresh the dashboard by clicking *Refresh*.

-   See detailed information about the tasks and statements of the elastic compute node by clicking *View Logs*, which takes you to the *Logs* tab of the *System Monitor*.

-   Navigate to the elastic compute node in the *Space Management* app by clicking *Manage*.

-   Analyze the performance of the SAP HANA database by clicking *Database Overview \(SAP HANA Cockpit\)*, which opens the Performance Monitor page in the SAP HANA Cockpit \(see [The Database Overview Page](https://help.sap.com/docs/hana-cloud/sap-hana-cloud-database-administration-with-sap-hana-cockpit/database-overview-page) in the *SAP HANA Cloud Database Administration with SAP HANA Cockpit*\).


