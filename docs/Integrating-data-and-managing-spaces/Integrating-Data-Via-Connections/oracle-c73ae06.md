<!-- loioc73ae0601d364f47830d339b6e86b7e8 -->

# Oracle

 Use the connection to access data from an Oracle database \(on-premise\). 



## Prerequisites

See: [Prepare Connectivity to Oracle](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/internal/en-US/9fca7c484e974429afc6570196303c35.html "To be able to successfully validate and use a connection to an Oracle database for remote tables or data flows, certain preparations have to be made.") :arrow_upper_right:



<a name="loioc73ae0601d364f47830d339b6e86b7e8__Oracle_usage"/>

## Using the Connection

The connection type supports the remote table as well as the data flow feature.

Supported data access methods for remote tables:

-   Remote
-   Replication \(snapshot\)
-   Replication \(real-time\)

    > ### Note:  
    > SAP Datasphere uses trigger-based replication. For more information, see [Oracle Trigger-Based Replication](https://help.sap.com/viewer/7952ef28a6914997abc01745fef1b607/latest/en-US/0167d05537d84b0ea32979be85266b54.html) in the *SAP HANA Smart Data Integration and SAP HANA Smart Data Quality Installation and Configuration Guide*.


For more information, see [Replicating Data and Monitoring Remote Tables](../Data-Integration-Monitor/replicating-data-and-monitoring-remote-tables-4dd95d7.md). 

> ### Note:  
> Note that only databases available on the public internet can be consumed in data flows directly. To avoid this restriction, you can use a remote table as a source for your data flow. To do so, you can deploy a remote table by importing the data set you're interested in from the connection into an E/R model in your space, for example. When creating a data flow in the space, the remote table then is available from the *Repository* tab in the *Source Browser*.



<a name="loioc73ae0601d364f47830d339b6e86b7e8__section_nrb_hcc_x4b"/>

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

*Data Flows* are enabled without the need to set any additional connection properties. Make sure you have maintained the properties in the *Cloud Connector* section.



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

