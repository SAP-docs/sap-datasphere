<!-- loioc73ae0601d364f47830d339b6e86b7e8 -->

# Oracle Connections

Use the connection to connect to and access data from an Oracle database \(on-premise\). 



This topic contains the following sections:

-   [Supported Features](oracle-connections-c73ae06.md#loioc73ae0601d364f47830d339b6e86b7e8__Oracle_usage)
-   [Configuring Connection Properties](oracle-connections-c73ae06.md#loioc73ae0601d364f47830d339b6e86b7e8__connection_properties)

For information about the required prerequisites, see [Prepare Connectivity to Oracle](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/9fca7c484e974429afc6570196303c35.html "To be able to successfully validate and use a connection to an Oracle database for remote tables or data flows, certain preparations have to be made.") :arrow_upper_right:.



<a name="loioc73ae0601d364f47830d339b6e86b7e8__Oracle_usage"/>

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

> ### Note:  
> SAP Datasphere uses trigger-based replication. For more information, see [Oracle Trigger-Based Replication](https://help.sap.com/viewer/7952ef28a6914997abc01745fef1b607/latest/en-US/0167d05537d84b0ea32979be85266b54.html) in the *SAP HANA Smart Data Integration and SAP HANA Smart Data Quality Installation and Configuration Guide*.



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



<a name="loioc73ae0601d364f47830d339b6e86b7e8__connection_properties"/>

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

*Host*  

</td>
<td valign="top">

Enter the host name or IP address on which the remote Oracle database is running. 

</td>
</tr>
<tr>
<td valign="top">

*Port*  

</td>
<td valign="top">

Enter the Oracle database server port number. 

</td>
</tr>
<tr>
<td valign="top">

*Database Name/SID*  

</td>
<td valign="top">

Enter the Oracle database name 

</td>
</tr>
<tr>
<td valign="top">

*Service Name*

</td>
<td valign="top">

Enter the service name of Oracle database. When creating a remote source, you must set only one of the following parameters: *Database Name* and *Service Name*. 

If you set both, the Data Provisioning Agent connects to Oracle by the service name as the first choice.

</td>
</tr>
<tr>
<td valign="top">

*Version*

</td>
<td valign="top">

Select a version. Supported versions are Oracle 12c, Oracle 18c, and Oracle 19c. Default version is Oracle 19c.

</td>
</tr>
</table>



### Cloud Connector

> ### Note:  
> Cloud Connector is not required if your Oracle database is available on the public internet.


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
> To select another location ID than the default location, *Connection.Read* privilege is required. The privilege is neither included in the *DW Integrator* nor in the *DW Space Administrator* role. If you need to select a location ID, ask your tenant administrator to either assign your user to a global role that is based on the *DW Administrator* role or to assign your user to a custom global role that includes the required *Connection.Read* privilege.



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

> ### Note:  
> If you select SSL and you want to use the connection for data flows, in addition to the ODBC driver file, additional files must have been uploaded to SAP Datasphere \(see [Upload Third-Party ODBC Drivers (Required for Data Flows)](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/b9b5579054df48c39381d5b17286bf21.html "To enable access to a non-SAP database via ODBC to use it as a source for data flows, you need to upload the required ODBC driver files to SAP Datasphere.") :arrow_upper_right:\).



</td>
</tr>
<tr>
<td valign="top">

\[if *Use SSL* = *true*\] *Distinguished Name \(DN\) in Certificate*  

</td>
<td valign="top">

Enter the distinguished name \(DN\) of the primary data server certificate. 

> ### Note:  
> If this parameter is set, the DN field in the server certificate is verified to match this parameter. If it doesn’t match, the connection to the primary data server fails.



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

Enter the Oracle user name \(case-sensitive\) 

</td>
</tr>
<tr>
<td valign="top">

*Password*  

</td>
<td valign="top">

Enter the Oracle user password 

</td>
</tr>
</table>



### Features

To enable *Remote Tables*, select a Data Provisioning Agent.

*Data Flows* are enabled without the need to set any additional connection properties.



<a name="loioc73ae0601d364f47830d339b6e86b7e8__section_zrg_tsk_lpb"/>

## Advanced Connection Properties

When you've selected a Data Provisioning Agent, you can configure advanced connection properties to enable specific customer scenarios. In the connection creation wizard, you configure advanced properties in an additional wizard step. When editing the connection to configure the properties, scroll down and click the *Show Advanced Properties button*. Advanced properties have default values that you can override according to your customer scenario’s needs.

Available properties:

-   *Map INTEGER/NUMBER to DECIMAL\(38,0\)*

-   *Time Zone Format*

-   *Use Oracle TNSNAMES File*

-   *Allowlist Table in Remote Database*

-   *Use LDAP Authentication*

-   *Schema Alias*

-   *Schema Alias Replacement*

-   *Include Table and Columns Remarks*

-   *Enable ABAP Manageable Trigger Namespace*

-   *Sequence Cache Size*

-   *Connection Pool Size*

-   *Minimum Scan Interval in Seconds*

-   *Maximum Scan Interval in Seconds*

-   *Maximum Batch Size*

-   *Batch Queue Size*

-   *Maximum Transaction Count in Scan*

-   *Maximum Scan Size*

-   *Enable Compound Triggers*

-   \[if *Enable Compound Triggers* = *true*\] *Flush Threshold of Compound Triggers*

-   \[if *Enable Compound Triggers* = *false*\] *Triggers Record Primary Keys Only*

-   \[if *Enable Compound Triggers* = *false* and *Triggers Record Primary Keys Only* = *false*\] *Triggers Record ROWID Pseudo Column Only*

-   \[if *Enable Compound Triggers* = *false* and *Triggers Record Primary Keys Only* = *true*\] *Triggers Capture Before and After Images*

-   \[if *Enable Compound Triggers* = *false* and *Triggers Record Primary Keys Only* = *false*\] *Merge Before and After Images of Updates into One Row*

-   \[if *Triggers Record Primary Keys Only* = *false* and *Triggers Record ROWID Pseudo Column Only* = *false*\] *Triggers Record LOB Values*

-   *Enable Shadow Table Partition*

-   *Enable Trigger Queue Table Partition*

-   *Transmit Data in Compact Mode*

-   *Enable Transaction Merge*


For more information, see [Oracle Log Reader Remote Source Configuration](https://help.sap.com/viewer/7952ef28a6914997abc01745fef1b607/latest/en-US/01175421322d488cb508aaa2ca42fb47.html) in the*SAP HANA Smart Data Integration and SAP HANA Smart Data Quality Installation and Configuration Guide*.

