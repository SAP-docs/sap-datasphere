<!-- loio9b9db1490df6452a843f5081581aa5a3 -->

# Remote Tables in Data Access Remote Only Vs Data Access Remote and Replication

An administrator or a data integrator has configured the source connection as *Remote Only* to prevent remote tables from being replicated in SAP Datasphere.

> ### Note:  
> If your connections have been set up in a previous version, they have been updated with data access *Remote and Replication*.

The possibility to replicate the entire source object using remote table replication \(snapshot or real-time\) is useful for some use cases such as performance optimization.

However, remote table replication offers limited support for use cases that require more flexibility when dealing with larger amounts of data. Many of these use cases require ETL \(Extract, Transform, Load\) capabilities that can be easily achieved with *Replication Flow* or *Data Flow* capabilities.

There are also cases where you don't want the data to be persisted on the Cloud, for example for data protection or security concerns.

To support use cases where data does not need to be replicated using remote tables, the option data access: *Remote Only* can be set to a connection when supported \(currently, for SAP HANA Cloud and SAP HANA on-premise\). For more information, see [SAP HANA](../Integrating-Data-Via-Connections/sap-hana-e6b63f1.md#loioe6b63f176d3640609adcf06297fb37e9). You can use the data access: *Remote Only* for connections that both support remote tables and replication flows. This way, you will replicate data only via replication flows \(SAP recommendation\) and not via remote tables, and thus avoid replicating the same data twice.

The table below compares the actions you can do when your remote table is in data access *Remote Only* compared to a remote table in data access *Remote and Replication* or with no particular option selected:


<table>
<tr>
<th valign="top">

Actions



</th>
<th valign="top">

Data Access Remote Only



</th>
<th valign="top">

Data Access Remote and Replication \(or no option\)



</th>
</tr>
<tr>
<td valign="top">

Replication of Data



</td>
<td valign="top">

Not possible directly. However, selected data can be replicated via *Replication flow Monitor* 

For more information, see [Creating a Data Flow](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/internal/en-US/e30fd1417e954577baae3246ea470c3f.html "Create a data flow to move and transform data in an intuitive graphical interface. You can drag and drop sources from the Source Browser, join them as appropriate, add other operators to remove or create columns, aggregate data, and do Python scripting, before writing the data to the target table.") :arrow_upper_right: and [Creating a Replication Flow](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/internal/en-US/25e2bd7a70d44ac5b05e844f9e913471.html "Create a replication flow if you want to copy data from a source to a target in a fast and easy way and do not require complex projections.") :arrow_upper_right:

.



</td>
<td valign="top">

Possible. You can do it via snapshot replication or real-time replication when supported. Data can be replicated either from the table editor \(in the *Data Builder*\) or from the *Remote Table Monitor* \(in the *Data Integration Monitor*\)

For more information, see [Replicating Data and Monitoring Remote Tables](replicating-data-and-monitoring-remote-tables-4dd95d7.md)



</td>
</tr>
<tr>
<td valign="top">

Scheduling of data load



</td>
<td valign="top">

Not possible



</td>
<td valign="top">

Possible. For more information, see [Scheduling Data Integration Tasks](scheduling-data-integration-tasks-7fa0762.md)



</td>
</tr>
<tr>
<td valign="top">

Partition of data load



</td>
<td valign="top">

Not possible



</td>
<td valign="top">

Possible. See [Partitioning Remote Table Data Loads](partitioning-remote-table-data-loads-a218d27.md)



</td>
</tr>
<tr>
<td valign="top">

Import/Edit/Delete/Refresh/Display



</td>
<td valign="top">

Possible. For more information, see [Importing Tables and Views from Sources](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/internal/en-US/7c4acd33e39a451e99c87f0661772443.html "Import tables and views from a connection, Open SQL schema, HDI container or other source available in your space.") :arrow_upper_right:.



</td>
<td valign="top">

Possible. or more information, see [Importing Tables and Views from Sources](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/internal/en-US/7c4acd33e39a451e99c87f0661772443.html "Import tables and views from a connection, Open SQL schema, HDI container or other source available in your space.") :arrow_upper_right:.



</td>
</tr>
<tr>
<td valign="top">

Monitoring of remote tables



</td>
<td valign="top">

No specific monitor is available. However, you can monitor the exchange of data between SAP Datasphere and the remote source system in the *Remote Query Monitor*. For more information, see [Monitoring Remote Queries](monitoring-remote-queries-806d7f0.md)



</td>
<td valign="top">

Possible. You can monitor remote tables via the *Remote Table Monitor*. For more information, see [Monitoring Remote Queries](monitoring-remote-queries-806d7f0.md).



</td>
</tr>
<tr>
<td valign="top">

Create/Edit/Delete Statistics



</td>
<td valign="top">

Yes. For more information, see [Creating Statistics for Your Remote Tables](creating-statistics-for-your-remote-tables-e4120bb.md)



</td>
<td valign="top">

Not possible



</td>
</tr>
</table>

