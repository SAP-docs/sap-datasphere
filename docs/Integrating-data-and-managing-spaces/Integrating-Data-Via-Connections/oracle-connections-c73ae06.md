<!-- loioc73ae0601d364f47830d339b6e86b7e8 -->

# Oracle Connections

Use the connection to connect to and access data from an Oracle database \(on-premise\). 

> ### Note:  
> The connection type is not supported in spaces with storage type *SAP HANA Data Lake Files* \(file spaces\).



This topic contains the following sections:

-   [Supported Features](oracle-connections-c73ae06.md#loioc73ae0601d364f47830d339b6e86b7e8__Oracle_usage)
-   [Prerequisites](oracle-connections-c73ae06.md#loioc73ae0601d364f47830d339b6e86b7e8__Oracle_prerequisites)
-   [Configuring Connection Properties](oracle-connections-c73ae06.md#loioc73ae0601d364f47830d339b6e86b7e8__Oracle_connection_properties)



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



<a name="loioc73ae0601d364f47830d339b6e86b7e8__Oracle_prerequisites"/>

## Prerequisites



### Replication Flows

Before you can use the connection for replication flows, the following is required:

-   An administrator has installed and configured Cloud Connector to connect to your on-premise source.

    For more information, see [Configure Cloud Connector](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/f289920243a34127b0c8b13012a1a4b5.html "Configure Cloud Connector before connecting to on-premise sources and using them in various use cases. In the Cloud Connector administration, connect the SAP Datasphere subaccount to your Cloud Connector, add a mapping to each relevant source system in your network, and specify accessible resources for each source system.") :arrow_upper_right:.

    > ### Note:  
    > Cloud Connector is not required if your Oracle database is available on the public internet.




### Remote Tables

Before you can use the connection for remote tables, the following is required:

-   An administrator has connected an SAP HANA smart data integration Data Provisioning Agent to SAP Datasphere and registered the OracleLogReaderAdapter.

    For more information, see [Preparing Data Provisioning Agent Connectivity](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/f1a39d1a763e48c8872f45c110a5a4e2.html "Most connection types supporting remote tables use SAP HANA Smart Data Integration (SDI) and its Data Provisioning Agent. Before using the connection, the agent requires an appropriate setup.") :arrow_upper_right:.

-   An administrator has downloaded and installed the required JDBC library in the <code><i class="varname">&lt;DPAgent_root&gt;</i>/lib</code> folder before registering the adapter with SAP Datasphere.

    For more information about the supported JDBC libraries, see the [SAP HANA smart data integration and all its patches Product Availability Matrix \(PAM\) for SAP HANA SDI 2.0](https://support.sap.com/content/dam/launchpad/en_us/pam/pam-essentials/TIP/PAM_HANA_SDI_2_0.pdf). Search for the required library in the internet and download it from an appropriate web page.

-   [Required Permissions for Oracle Trigger-Based Replication](https://help.sap.com/viewer/7952ef28a6914997abc01745fef1b607/latest/en-US/bd79ed316a1447ffb1fbd3757aff9c71.html) in the *SAP HANA Smart Data Integration and SAP HANA Smart Data Quality Installation and Configuration Guide*

-   If encrypted communication is used \(connection is configured to use SSL\), the server certificate must be uploaded to the Data Provisioning Agent.

    To retrieve the certificate, you can use for example the following command: `openssl s_client -showcerts -servername <host name of the Oracle database server>:<port number of the Oracle database server> -connect <host name of the Oracle database server>:<port number of the Oracle database server>`

    For more information about uploading the certificate to the Data Provisioning Agent, see:

    -   [Configure the Adapter Truststore and Keystore](https://help.sap.com/docs/HANA_SMART_DATA_INTEGRATION/7952ef28a6914997abc01745fef1b607/1d0259de04e247d994258429b34b8546.html) in the *SAP HANA Smart Data Integration and SAP HANA Smart Data Quality* documentation
    -   [Configure SSL for the Oracle Log Reader Adapter](https://help.sap.com/docs/HANA_SMART_DATA_INTEGRATION/7952ef28a6914997abc01745fef1b607/03c4f2f0629d40f28d333723a820a0d4.html) in the *SAP HANA Smart Data Integration and SAP HANA Smart Data Quality* documentation




### Data Flows

Before you can use the connection for data flows, the following is required:

-   An administrator has installed and configured Cloud Connector to connect to your on-premise source.

    For more information, see [Configure Cloud Connector](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/f289920243a34127b0c8b13012a1a4b5.html "Configure Cloud Connector before connecting to on-premise sources and using them in various use cases. In the Cloud Connector administration, connect the SAP Datasphere subaccount to your Cloud Connector, add a mapping to each relevant source system in your network, and specify accessible resources for each source system.") :arrow_upper_right:.

    > ### Note:  
    > Cloud Connector is not required if your Oracle database is available on the public internet.

-   A DW administrator has uploaded the required ODBC driver file to SAP Datasphere.

    To use encrypted communication \(connection is configured to use SSL\), additional files are required to be uploaded.

    For more information, see [Upload Third-Party ODBC Drivers (Required for Data Flows)](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/b9b5579054df48c39381d5b17286bf21.html "To enable access to a non-SAP database via ODBC to use it as a source for data flows, you need to upload the required ODBC driver files to SAP Datasphere.") :arrow_upper_right:.

-   A DW administrator has uploaded the server certificate to SAP Datasphere.

    To retrieve the certificate, you can use for example the following command: `openssl s_client -showcerts -servername <host name of the Oracle database server>:<port number of the Oracle database server> -connect <host name of the Oracle database server>:<port number of the Oracle database server>`

    For more information, see [Manage Certificates for Connections](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/46f5467adc5242deb1f6b68083e72994.html "For connections secured by leveraging HTTPS as the underlying transport protocol (using SSL/TLS transport encryption), the server certificate must be trusted. To import a certificate into the SAP Datasphere trust chain, obtain the certificate from the target endpoint and upload it to SAP Datasphere.") :arrow_upper_right:.




<a name="loioc73ae0601d364f47830d339b6e86b7e8__Oracle_connection_properties"/>

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

> ### Note:  
> The port number can vary depending on whether SSL is used or not.



</td>
</tr>
<tr>
<td valign="top">

*Database Name/SID*  

</td>
<td valign="top">

Enter the Oracle database name. 

</td>
</tr>
<tr>
<td valign="top">

*Service Name*

</td>
<td valign="top">

Enter the service name of Oracle database. 

Only one of the following properties is required for the connection: *Database Name* and *Service Name*. If you enter values for both properties, the Data Provisioning Agent connects to Oracle by the service name as the first choice.

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
> To select another location ID than the default location, *Connection* privilege with *Read* permission is required.



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

> ### Note:  
> If you select SSL and you want to use the connection for data flows, in addition to the ODBC driver file, additional files must have been uploaded to SAP Datasphere \(see [Upload Third-Party ODBC Drivers (Required for Data Flows)](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/b9b5579054df48c39381d5b17286bf21.html "To enable access to a non-SAP database via ODBC to use it as a source for data flows, you need to upload the required ODBC driver files to SAP Datasphere.") :arrow_upper_right:\).



</td>
</tr>
<tr>
<td valign="top">

\[if *Use SSL* = *true*\] *Distinguished Name \(DN\) in Certificate*  

</td>
<td valign="top">

When using the connection for remote tables, enter the distinguished name \(DN\) of the primary data server certificate. 

> ### Note:  
> -   The DN field in the server certificate is verified to match what you've entered here. If it doesn’t match, the connection to the primary data server fails.
> -   The distinguished name must contain no quotes, and there must be a space between CN and C. For example, `CN=..., C=...` \(see [Configure SSL for the Oracle Log Reader Adapter](https://help.sap.com/docs/HANA_SMART_DATA_INTEGRATION/7952ef28a6914997abc01745fef1b607/03c4f2f0629d40f28d333723a820a0d4.html) in the *SAP HANA Smart Data Integration and SAP HANA Smart Data Quality* documentation.



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

Enter the Oracle user name \(case-sensitive\). 

</td>
</tr>
<tr>
<td valign="top">

*Password*  

</td>
<td valign="top">

Enter the Oracle user password. 

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
</table>



<a name="loioc73ae0601d364f47830d339b6e86b7e8__section_zrg_tsk_lpb"/>

## Advanced Connection Properties

When you've selected a Data Provisioning Agent, you can configure advanced connection properties to enable specific customer scenarios. In the connection creation wizard, you configure advanced properties in an additional wizard step. When editing the connection to configure the properties, scroll down and click the *Show Advanced Properties* button. Advanced properties have default values that you can override according to your customer scenario’s needs.

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

