<!-- loioe6b63f176d3640609adcf06297fb37e9 -->

# SAP HANA Connections

Use an *SAP HANA* connection to access data from a remote SAP HANA database \(on-premise or cloud\).



This topic contains the following sections:

-   [Supported Features](sap-hana-connections-e6b63f1.md#loioe6b63f176d3640609adcf06297fb37e9__HANA_usage)
-   [Configuring Connection Properties \(SAP HANA Cloud\)](sap-hana-connections-e6b63f1.md#loio27aebc8432aa419da75c5fc650981f24)
-   [Configuring Connection Properties \(SAP HANA on-premise\)](sap-hana-connections-e6b63f1.md#loio77cec6a1e8d04371a791658e641dc0d5)

For information about the required prerequisites, see [Prepare Connectivity to SAP HANA](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/d7f22cffa3d443669fec3003971e7638.html "To be able to successfully validate and use a connection to SAP HANA Cloud or SAP HANA (on-premise) for remote tables or data flows certain preparations have to be made.") :arrow_upper_right:.



<a name="loioe6b63f176d3640609adcf06297fb37e9__HANA_usage"/>

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

You can use the connection to add source and target objects to a replication flow.



</td>
</tr>
</table>

> ### Note:  
> The connection type supports replication with both remote tables via Data Provisioning Agent \(SAP HANA Smart Data Integration\) and replication flows.
> 
> Regardless of whether you use the same connection or two separate connections, for replicating data from a dedicated source object in the source we strongly recommend to only use remote tables or replication flows and not both.

 <a name="loio27aebc8432aa419da75c5fc650981f24"/>

<!-- loio27aebc8432aa419da75c5fc650981f24 -->

## Configuring Connection Properties \(SAP HANA Cloud\)





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

 *Category* 



</td>
<td valign="top">

 Select *Cloud* to connect to an SAP HANA Cloud instance. 



</td>
</tr>
<tr>
<td valign="top">

 *Host* 



</td>
<td valign="top">

 Enter the fully qualified host name or IP address on which the remote SAP HANA server is running. 



</td>
</tr>
<tr>
<td valign="top">

 *Port* 



</td>
<td valign="top">

 Enter the SQL port number of the remote SAP HANA server. 

You can find the SQL port in the list of service details in the SAP HANA Cockpit. For more information, see [Service Details](https://help.sap.com/viewer/afa922439b204e9caf22c78b6b69e4f2/latest/en-US/1d4b4fe9ee8b448a9977bfcc1fc55248.html?q=SQL%20port) in the *SAP HANA Administration with SAP HANA Cockpit* documentation.



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

 Enter the database user name \(case sensitive\). 



</td>
</tr>
<tr>
<td valign="top">

 *Password* 



</td>
<td valign="top">

 Enter the password of the SAP HANA database user. 



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

*Remote Tables* are enabled without the need to set any additional connection properties.

Complete the following properties:


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

*Data Provisioning Option*



</td>
<td valign="top">

\[read-only\] Displays the midleware used to connect to the on-premise system.

The option for SAP HANA Cloud is always set to *Direct* because no middleware is required.



</td>
</tr>
<tr>
<td valign="top">

*Data Access*



</td>
<td valign="top">

Select how you want to access data from source objects: 

-   Select *Remote Only* if you want to federate data from the source objects of the connection and access them remotely in the source system.

-   Select *Remote and Replication* \(default\) if you want to allow copying the data from the source object into SAP Datasphere.


For more information about the use cases for the options, see [Remote Tables in Data Access Remote Only Vs Data Access Remote and Replication](../Data-Integration-Monitor/remote-tables-in-data-access-remote-only-vs-data-access-remote-and-replication-9b9db14.md).



</td>
</tr>
</table>



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

 <a name="loio77cec6a1e8d04371a791658e641dc0d5"/>

<!-- loio77cec6a1e8d04371a791658e641dc0d5 -->

## Configuring Connection Properties \(SAP HANA on-premise\)





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

 *Category* 



</td>
<td valign="top">

 Select *On-Premise* to connect to SAP HANA \(on-premise\). 



</td>
</tr>
<tr>
<td valign="top">

 *Host* 



</td>
<td valign="top">

 Enter the fully qualified host name or IP address on which the remote SAP HANA server is running. 



</td>
</tr>
<tr>
<td valign="top">

 *Port* 



</td>
<td valign="top">

 Enter the SQL port number of the remote SAP HANA server. 

You can find the SQL port in the list of service details in the SAP HANA Cockpit. For more information, see [Service Details](https://help.sap.com/viewer/afa922439b204e9caf22c78b6b69e4f2/latest/en-US/1d4b4fe9ee8b448a9977bfcc1fc55248.html?q=SQL%20port) in the *SAP HANA Administration with SAP HANA Cockpit* documentation.



</td>
</tr>
</table>



### Cloud Connector


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

Set to *true* if your source is an on-premise source and you want to use the connection for one of the following features:

-   remote tables with SAP HANA smart data access
-   data flows
-   replication flows

The default is *false*.



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

 *Enable SSL encryption* 



</td>
<td valign="top">

 Select whether to enable SSL encryption on the connection to the remote SAP HANA database. The default value is *true*. 

> ### Note:  
> To use SSL encryption with a remote SAP HANA database connected via SAP HANA smart data integration, the Data Provisioning Agent must already be correctly configured for SSL support.
> 
> For more information, see [Configure SSL for SAP HANA On-Premise \[Manual Steps\]](https://help.sap.com/docs/HANA_SMART_DATA_INTEGRATION/7952ef28a6914997abc01745fef1b607/caeef0265b14482eb355b101c9cb92df.html?version=latest) in the *SAP HANA Smart Data Integration and SAP HANA Smart Data Quality* documentation.



</td>
</tr>
<tr>
<td valign="top">

 \[if *Enable SSL encryption* = *true*\] *Validate Server Certificate* 



</td>
<td valign="top">

 Select whether to validate the certificate of the remote SAP HANA server. The default value is *true*. 

If set to *false*, the host name used for the connection is used for verification.

> ### Note:  
> -   SSL is name-based; connecting to an IP address, or to “localhost” is unlikely to work.
> 
> -   When using SAP HANA smart data access via Cloud Connector for remote tables: To validate the server certificate, the certificate must have been uploaded to SAP Datasphere.
> 
>     For more information, see [Upload Certificates (Required for Remote Tables)](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/46f5467adc5242deb1f6b68083e72994.html "To enable a secure SSL/TLS-based connection for a connection type that supports remote tables but doesn&apos;t use a Data Provisioning Agent, you need to upload a server certificate to SAP Datasphere.") :arrow_upper_right:.



</td>
</tr>
<tr>
<td valign="top">

 \[if *Validate Server Certificate* = *true*\] *Host Name in Server Certificate* 



</td>
<td valign="top">

 Verify the host name field of the server certificate: 

-   If the string is “\*”, any name matches.
-   If the string starts with “CN=”, it is treated as a common name, and the textual representation of the common name entry in the certificate must be exactly the same.



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

 Enter the database user name \(case sensitive\). 



</td>
</tr>
<tr>
<td valign="top">

 *Password* 



</td>
<td valign="top">

 Enter the password of the SAP HANA database user. 



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

To enable *Remote Tables*, complete the following properties:


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

*Data Provisioning Option*



</td>
<td valign="top">

Select the midleware to use when connecting to and accessing the on-premise system: 

-   *None* \(default\) if you don't want to use remote tables.

-   *Cloud Connector* if you want to access the data via SAP HANA smart data access.

-   *Data Provisioning Agent* if you want to access the data via SAP HANA smart data integration.


> ### Note:  
> When creating a connection to SAP HANA on-premise using SAP HANA smart data access via Cloud Connector, the system checks for a required internal service. In the connection overview, a warning icon indicates that the service might not be ready yet. This happens for the first connection you create or when you create a connection after the service has been disabled \(after an automated weekly check returning that there is no such connection anymore\). Getting the service ready might take up to 45 minutes. Validate the connection and check the message details for more information.
> 
> For troubleshooting the Cloud Connector, see [Troubleshooting SAP HANA Smart Data Access via Cloud Connector](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/42f683edbf6742b19cf15e7a18b8a607.html "These are some of the most common issues that can occur when you use the Cloud Connector to connect to on-premise remote sources via SAP HANA Smart Data Access.") :arrow_upper_right:.



</td>
</tr>
<tr>
<td valign="top">

\[if *Data Provisioning Option* = *Data Provisioning Agent*\] *Data Provisioning Agent*



</td>
<td valign="top">

 Select an agent from the list of agents configured for SAP Datasphere. 



</td>
</tr>
<tr>
<td valign="top">

\[if *Data Provisioning Option* = *Cloud Connector* or *Data Provisioning Agent*\] *Data Access*



</td>
<td valign="top">

 Select how you want to access data from source objects: 

-   Select *Remote Only* if you want to federate data from the source objects of the connection and access them remotely in the source system.

-   Select *Remote and Replication* \(default\) if you want to allow copying the data from the source object into SAP Datasphere.


For more information about the use cases for the options, see [Remote Tables in Data Access Remote Only Vs Data Access Remote and Replication](../Data-Integration-Monitor/remote-tables-in-data-access-remote-only-vs-data-access-remote-and-replication-9b9db14.md).



</td>
</tr>
</table>



</td>
</tr>
<tr>
<td valign="top">

*Data Flows*



</td>
<td valign="top">

 *Data Flows* are enabled without the need to set any additional connection properties. Make sure you have maintained the properties in the *Cloud Connector* section. 



</td>
</tr>
<tr>
<td valign="top">

*Replication Flows*



</td>
<td valign="top">

 *Replication Flows* are enabled without the need to set any additional connection properties. Make sure you have maintained the properties in the *Cloud Connector* section. 



</td>
</tr>
</table>



<a name="loio77cec6a1e8d04371a791658e641dc0d5__section_j21_tdg_knb"/>

## Advanced Connection Properties \(SAP HANA on-premise\)

When you've selected a Data Provisioning Agent, you can configure advanced connection properties to enable specific customer scenarios. In the connection creation wizard, you configure advanced properties in an additional wizard step. When editing the connection to configure the properties, scroll down and click the *Show Advanced Properties button*. Advanced properties have default values that you can override according to your customer scenario’s needs.

Available properties:

-   *Enable ABAP Manageable Trigger Namespace*

-   \[if *Enable ABAP Manageable Trigger Namespace* = *true*\] *ABAP Manageable Trigger Namespace*

-   *Connection Pool Size*

-   *Minimum Scan Interval in Seconds*

-   *Maximum Scan Interval in Seconds*

-   *Maximum Batch Size*

-   *DDL Scan Interval in Minutes*

-   *Batch Queue Size*

-   *Maximum Transaction Count in Scan*

-   *Maximum Scan Size*

-   *Enable Statement-level Triggers*

-   \[if *Enable Statement-level Triggers* = *true*\] *Create Statement-level Insert Triggers*

-   \[if *Enable Statement-level Triggers* = *true*\] *Create Statement-level Delete Triggers*

-   \[if *Enable Statement-level Triggers* = *true*\] *Create Statement-level Update Triggers*

-   *Triggers Record Primary Keys Only*

-   \[if *Enable Statement-level Triggers* = *false* and *Triggers Record Primary Keys Only* = *true*\] *Triggers Upsert Shadow Tables*

-   \[if *Triggers Record Primary Keys Only* = *true*\] *Triggers Capture Before and After Images*

-   \[if *Triggers Record Primary Keys Only* = *true*\] *Triggers Capture Full Before Images*

-   *Shadow Table Type*

-   *Trigger Queue Table Type*

-   *Source Data Pattern Analysis*

-   *Transmit Data in Compact Mode*

-   *Enable Transaction Merge*

-   *Allowlist Table in Remote Database*

-   *Schema*

-   *JDBC Connection Properties*

-   *Retrieve Last Modified Dates for Objects in Dictionary*

-   *Schema Alias*

-   *Schema Alias Replacement*


For more information, see [SAP HANA Remote Source Configuration](https://help.sap.com/viewer/7952ef28a6914997abc01745fef1b607/latest/en-US/5d667b85725e4960b80550a0f75442ac.html) in the*SAP HANA Smart Data Integration and SAP HANA Smart Data Quality Installation and Configuration Guide*.

