<!-- loioa13c8abb328f45be891599c9cc76fb91 -->

# Microsoft SQL Server Connections

Use a *Microsoft SQL Server* connection to access data from a Microsoft SQL Server \(on-premise\).



<a name="loioa13c8abb328f45be891599c9cc76fb91__section_j1b_byq_spb"/>

## Prerequisites

See: [Prepare Connectivity to Microsoft SQL Server](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/ea69328fb328449ab7b04d2b142592f8.html "To be able to successfully validate and use a connection to a Microsoft SQL Server for remote tables or data flows, certain preparations have to be made.") :arrow_upper_right:



<a name="loioa13c8abb328f45be891599c9cc76fb91__MSSQL_usage"/>

## Using the Connection

The connection type supports the remote table as well as the data flow feature.

Supported data access methods for remote tables:

-   Remote
-   Replication \(snapshot\)
-   Replication \(real-time\)

    > ### Note:  
    > SAP Datasphere uses trigger-based replication. For more information, see [Microsoft SQL Server Trigger-Based Replication](https://help.sap.com/viewer/7952ef28a6914997abc01745fef1b607/latest/en-US/c27c15981a22450985e478d58d3c851d.html) in the *SAP HANA Smart Data Integration and SAP HANA Smart Data Quality Installation and Configuration Guide*.


For more information, see [Replicating Data and Monitoring Remote Tables](../Data-Integration-Monitor/replicating-data-and-monitoring-remote-tables-4dd95d7.md). 



<a name="loioa13c8abb328f45be891599c9cc76fb91__section_nrb_hcc_x4b"/>

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

Select the Microsoft SQL Server version.



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

\[optional\] Set to *true* if your source is an on-premise source and you want to use the connection for data flows. The default is *false*. 



</td>
</tr>
<tr>
<td valign="top">

\[if *Use Cloud Connector* = *true*\] *Location* 



</td>
<td valign="top">

\[optional\] Select a location ID. 

> ### Note:  
> To select another location ID than the default location, *Connection.Read* privilege is required. The privilege is not included in the *DW Integrator* or *DW Space Administrator* role. If you need to select a location ID, ask your tenant administrator to either assign the *DW Administrator* role to your user or to create a custom role containing the required privileges. 



</td>
</tr>
<tr>
<td valign="top">

\[if *Use Cloud Connector* = *true*\] *Virtual Destination* 



</td>
<td valign="top">

\[optional\] Select *Derive Virtual Host and Port from Connection Details* or *Enter Virtual Host and Port in Separate Fields*. 

If host and port entered in the connection details match the virtual host and port from the Cloud Connector configuration, you can select *Derive Virtual Host and Port from Connection Details* and don't need to enter the values manually.



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

To enable *Remote Tables*, select a Data Provisioning Agent.

*Data Flows* are enabled without the need to set any additional connection properties. Make sure you have maintained the properties in the *Cloud Connector* section.



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

