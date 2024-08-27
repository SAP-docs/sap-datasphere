<!-- loio46343fc1c4544fa9a075d97f84d39826 -->

# Microsoft Azure SQL Database Connections

Use a *Microsoft Azure SQL Database* connection to access table data from a Microsoft Azure SQL database.



This topic contains the following sections:

-   [Supported Features](microsoft-azure-sql-database-connections-46343fc.md#loio46343fc1c4544fa9a075d97f84d39826__Azure_SQL_usage)
-   [Configuring Connection Properties](microsoft-azure-sql-database-connections-46343fc.md#loio46343fc1c4544fa9a075d97f84d39826__connection_properties)

For information about the required prerequisites, see [Prepare Connectivity to Microsoft Azure SQL Database](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/782bd8c0d71943a9a6febee5f1557c80.html "To be able to successfully validate and use a connection to Microsoft Azure SQL database for remote tables or data flows certain preparations have to be made.") :arrow_upper_right:.



<a name="loio46343fc1c4544fa9a075d97f84d39826__Azure_SQL_usage"/>

## Supported Features


<table>
<tr>
<th valign="top">

Feature

</th>
<th valign="top">

Additional Information

</th>
</tr>
<tr>
<td valign="top">

Remote Tables

</td>
<td valign="top">

You can use remote tables imported from the connection either to access data directly live in the connected source \(federation\) or to copy the data into SAP Datasphere \(replication\).

For remote tables, real-time replication is supported. For information about any constraints, see [Replicate Data Changes in Real-Time](../Data-Integration-Monitor/replicate-data-changes-in-real-time-441d327.md).

</td>
</tr>
<tr>
<td valign="top">

Data Flows

</td>
<td valign="top">

You can use the connection to add source objects to a data flow.

</td>
</tr>
<tr>
<td valign="top">

Replication Flows

</td>
<td valign="top">

You can use the connection to add source objects to a replication flow.

</td>
</tr>
</table>

> ### Note:  
> The connection type supports replication with both remote tables via Data Provisioning Agent \(SAP HANA Smart Data Integration\) and replication flows \(for on-premise systems via Cloud Connector\).
> 
> Regardless of whether you use the same connection or two separate connections, for replicating data from a dedicated source object in the source we strongly recommend to only use remote tables or replication flows and not both.



<a name="loio46343fc1c4544fa9a075d97f84d39826__connection_properties"/>

## Configuring Connection Properties



### Connection Details


<table>
<tr>
<th valign="top">

Property

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Server Name* 

</td>
<td valign="top">

Enter the host name of the Azure server. 

</td>
</tr>
<tr>
<td valign="top">

*Port* 

</td>
<td valign="top">

Enter the port number of the Azure server. The default is `1433`. 

</td>
</tr>
<tr>
<td valign="top">

*Database Name* 

</td>
<td valign="top">

Enter the name of the database to which you want to connect. 

</td>
</tr>
<tr>
<td valign="top">

*Version* 

</td>
<td valign="top">

Select the version. 

</td>
</tr>
</table>



### Security


<table>
<tr>
<th valign="top">

Property

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Host Name in Server Certificate* 

</td>
<td valign="top">

Enter `*.database.windows.net` .

</td>
</tr>
</table>



### Credentials


<table>
<tr>
<th valign="top">

Property

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*User Name* 

</td>
<td valign="top">

Enter the name of the Azure user that has privileges to connect to the database. 

</td>
</tr>
<tr>
<td valign="top">

*Password* 

</td>
<td valign="top">

Enter the password of the Azure user. 

</td>
</tr>
</table>



### Features


<table>
<tr>
<th valign="top">

Feature

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Remote Tables*

</td>
<td valign="top">

To enable *Remote Tables*, select a Data Provisioning Agent. 

</td>
</tr>
<tr>
<td valign="top">

*Data Flows*

</td>
<td valign="top">

*Data Flows* are enabled without the need to set any additional connection properties. 

</td>
</tr>
<tr>
<td valign="top">

*Replication Flows*

</td>
<td valign="top">

*Replication Flows* are enabled without the need to set any additional connection properties. 

</td>
</tr>
</table>

