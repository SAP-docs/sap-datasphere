<!-- loioa13c8abb328f45be891599c9cc76fb91 -->

# Microsoft SQL Server Connections

Use a *Microsoft SQL Server* connection to access data from a Microsoft SQL Server database \(on-premise\).



This topic contains the following sections:

-   [Supported Features](microsoft-sql-server-connections-a13c8ab.md#loioa13c8abb328f45be891599c9cc76fb91__MSSQL_usage)
-   [Configuring Connection Properties](microsoft-sql-server-connections-a13c8ab.md#loioa13c8abb328f45be891599c9cc76fb91__connection_properties)

For more information about the required prerequisites, see [Prepare Connectivity to Microsoft SQL Server](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/ea69328fb328449ab7b04d2b142592f8.html "To be able to successfully validate and use a connection to a Microsoft SQL Server, certain preparations have to be made.") :arrow_upper_right:.



<a name="loioa13c8abb328f45be891599c9cc76fb91__MSSQL_usage"/>

## Supported Features

> ### Note:  
> In file spaces, only replication flows are supported. Remote tables and data flows are not supported.


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

Replication Flows

</td>
<td valign="top">

You can use the connection to add source objects to a replication flow.

</td>
</tr>
<tr>
<td valign="top">

Remote Tables

</td>
<td valign="top">

You can use remote tables imported from the connection either to access data directly live in the connected source \(federation\) or to copy the data into SAP Datasphere \(replication\).

For remote tables, real-time replication is supported. For information about any constraints, see [Replicate Data Changes in Real-Time](../Data-Integration-Monitor/replicate-data-changes-in-real-time-441d327.md).

> ### Note:  
> SAP Datasphere uses trigger-based replication. For more information, see [Microsoft SQL Server Trigger-Based Replication](https://help.sap.com/viewer/7952ef28a6914997abc01745fef1b607/latest/en-US/c27c15981a22450985e478d58d3c851d.html) in the *SAP HANA Smart Data Integration and SAP HANA Smart Data Quality Installation and Configuration Guide*.



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
</table>



<a name="loioa13c8abb328f45be891599c9cc76fb91__connection_properties"/>

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

Enter the Microsoft SQL Server name. 

> ### Note:  
> Connecting via instance name is not supported.



</td>
</tr>
<tr>
<td valign="top">

*Port* 

</td>
<td valign="top">

Enter the Microsoft SQL Server port number. The value range is 1–65535. 

> ### Note:  
> Dynamic ports are not supported.



</td>
</tr>
<tr>
<td valign="top">

*Database Name* 

</td>
<td valign="top">

Enter the Microsoft SQL Server database name. 

</td>
</tr>
<tr>
<td valign="top">

*Version*

</td>
<td valign="top">

Select the Microsoft SQL Server version. Supported versions are Microsoft SQL Server 2012, 2014, 2016, 2017, 2019, and 2022 \(default is 2022\). 

> ### Note:  
> Microsoft SQL Server 2012 is **not** supported for remote tables.



</td>
</tr>
</table>



### Cloud Connector

> ### Note:  
> Cloud Connector is not required if your Microsoft SQL Server database is available on the public internet.


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

*Use Cloud Connector* 

</td>
<td valign="top">

\[optional\] Set to *true* if your source is an on-premise source and you want to use the connection for data flows and replication flows. The default is *false*. 

</td>
</tr>
<tr>
<td valign="top">

\[if *Use Cloud Connector* = *true*\] *Location* 

</td>
<td valign="top">

\[optional\] Select a location ID. 

> ### Note:  
> To select another location ID than the default location, *Connection.Read* privilege is required. The privilege is neither included in the *DW Integrator* nor in the *DW Space Administrator* role. If you need to select a location ID, ask your tenant administrator to either assign your user to a global role that is based on the *DW Administrator* role or to assign your user to a custom global role \(with license type SAP Datasphere\) that includes the required *Connection.Read* privilege.



</td>
</tr>
<tr>
<td valign="top">

\[if *Use Cloud Connector* = *true*\] *Virtual Destination* 

</td>
<td valign="top">

\[optional\] Select how you want to specify the virtual destination. 

You can select:

-   *Derive Virtual Host and Port from Connection Details* \(default\)

    If host and port entered in the connection details match the virtual host and port from the Cloud Connector configuration, you don't need to enter the values manually.

-   *Enter Virtual Host and Port in Separate Fields*




</td>
</tr>
<tr>
<td valign="top">

\[if *Virtual Destination* = *Enter Virtual Host and Port in Separate Fields*\] *Virtual Host* 

</td>
<td valign="top">

Enter the virtual host that you defined during Cloud Connector configuration. 

</td>
</tr>
<tr>
<td valign="top">

\[if *Virtual Destination* = *Enter Virtual Host and Port in Separate Fields*\] *Virtual Port* 

</td>
<td valign="top">

Enter the virtual port that you defined during Cloud Connector configuration. 

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

*Use SSL*  

</td>
<td valign="top">

Select whether you’re using SSL. The default value is *true*. 

</td>
</tr>
<tr>
<td valign="top">

\[if *Use SSL* = *true*\] *Host Name in Certificate*  

</td>
<td valign="top">

Enter the host name that is in the SSL certificate. 

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

Enter the Microsoft SQL Server user name. 

</td>
</tr>
<tr>
<td valign="top">

*Password*  

</td>
<td valign="top">

Enter the Microsoft SQL Server user password. 

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

*Replication Flows*

</td>
<td valign="top">

*Replication Flows* are enabled without the need to set any additional connection properties.If your source is an on-premise source, make sure you have maintained the properties in the *Cloud Connector* section.

</td>
</tr>
<tr>
<td valign="top">

*Remote Tables*

</td>
<td valign="top">

To enable *Remote Tables*, select a Data Provisioning Agent.

> ### Note:  
> In file spaces, only replication flows are supported. Remote tables are not supported.



</td>
</tr>
<tr>
<td valign="top">

*Data Flows*

</td>
<td valign="top">

*Data Flows* are enabled without the need to set any additional connection properties.If your source is an on-premise source, make sure you have maintained the properties in the *Cloud Connector* section.

> ### Note:  
> In file spaces, only replication flows are supported. Data flows are not supported.



</td>
</tr>
</table>



<a name="loioa13c8abb328f45be891599c9cc76fb91__section_j21_tdg_knb"/>

## Advanced Connection Properties

When you've selected a Data Provisioning Agent, you can configure advanced connection properties to enable specific customer scenarios. In the connection creation wizard, you configure advanced properties in an additional wizard step. When editing the connection to configure the properties, scroll down and click the *Show Advanced Properties button*. Advanced properties have default values that you can override according to your customer scenario’s needs.

Available properties:

-   *Additional JDBC Connection Properties*

-   *Include Table and Columns Remarks*

-   *Allowlist Table in Remote Database*

-   *Schema Alias*

-   *Schema Alias Replacement*

-   *Use Windows Authentication*

-   *Schema to Create System Objects*

-   *Enable ABAP Manageable Trigger Namespace*

-   \[if *Enable ABAP Manageable Trigger Namespace* = *true*\] *ABAP Manageable Trigger Namespace*

-   *Connection Pool Size*

-   *Minimum Scan Interval in Seconds*

-   *Maximum Scan Interval in Seconds*

-   *Maximum Batch Size*

-   *Batch Queue Size*

-   *Maximum Transaction Count in Scan*

-   *Maximum Scan Size*

-   *Enable Compound Triggers*

-   *Triggers Record Primary Keys Only*

-   \[if *Triggers Record Primary Keys Only* = *true*\] *Triggers Capture Before and After Images*

-   \[if *Enable Compound Triggers* = *false* and *Triggers Record Primary Keys Only* = *false*\] *Transmit Data in Compact Mode*

-   *Enable Transaction Merge*


For more information, see [Microsoft SQL Server Log Reader Remote Source Configuration](https://help.sap.com/viewer/7952ef28a6914997abc01745fef1b607/latest/en-US/14a89905349146cf96dfe9ad651aba33.html) in the*SAP HANA Smart Data Integration and SAP HANA Smart Data Quality Installation and Configuration Guide*.

