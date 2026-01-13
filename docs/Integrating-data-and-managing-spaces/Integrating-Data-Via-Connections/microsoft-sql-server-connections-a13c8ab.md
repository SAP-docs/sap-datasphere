<!-- loioa13c8abb328f45be891599c9cc76fb91 -->

# Microsoft SQL Server Connections

Use a *Microsoft SQL Server* connection to access data from a Microsoft SQL Server database \(on-premise\).



This topic contains the following sections:

-   [Supported Features](microsoft-sql-server-connections-a13c8ab.md#loioa13c8abb328f45be891599c9cc76fb91__MSSQL_usage)
-   [Prerequisites](microsoft-sql-server-connections-a13c8ab.md#loioa13c8abb328f45be891599c9cc76fb91__MSSQL_prerequisites)
-   [Configuring Connection Properties](microsoft-sql-server-connections-a13c8ab.md#loioa13c8abb328f45be891599c9cc76fb91__MSSQL_connection_properties)



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

> ### Note:  
> The connection type supports replication with both remote tables via Data Provisioning Agent \(SAP HANA Smart Data Integration\) and replication flows. Generally, for replication scenarios, we recommend to use replication flows.



<a name="loioa13c8abb328f45be891599c9cc76fb91__MSSQL_prerequisites"/>

## Prerequisites



### Remote Tables

Before you can use the connection for remote tables, the following is required:

-   An administrator has connected an SAP HANA smart data integration Data Provisioning Agent to SAP Datasphere and registered the MssqlLogReaderAdapter.

    For more information, see [Preparing Data Provisioning Agent Connectivity](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/f1a39d1a763e48c8872f45c110a5a4e2.html "Most connection types supporting remote tables use SAP HANA Smart Data Integration (SDI) and its Data Provisioning Agent. Before using the connection, the agent requires an appropriate setup.") :arrow_upper_right:.

-   An administrator has downloaded and installed the required JDBC library in the <code><i class="varname">&lt;DPAgent_root&gt;</i>/lib</code> folder before registering the adapter with SAP Datasphere.

-   [Required Permissions for SQL Server Trigger-Based Replication](https://help.sap.com/viewer/7952ef28a6914997abc01745fef1b607/latest/en-US/2815e1a621f84bada5fa3447d5029eb6.html) in the *SAP HANA Smart Data Integration and SAP HANA Smart Data Quality Installation and Configuration Guide*




### Data Flows and Replication Flows

Before you can use the connection for data flows and replication flows, the following is required:

-   An administrator has installed and configured Cloud Connector to connect to your on-premise source.

    For more information, see [Configure Cloud Connector](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/f289920243a34127b0c8b13012a1a4b5.html "Configure Cloud Connector before connecting to on-premise sources and using them in various use cases. In the Cloud Connector administration, connect the SAP Datasphere subaccount to your Cloud Connector, add a mapping to each relevant source system in your network, and specify accessible resources for each source system.") :arrow_upper_right:.

    > ### Note:  
    > Cloud Connector is not required if your Microsoft SQL Server database is available on the public internet.

-   The required driver is pre-bundled and doesn't need to be uploaded by an administrator.

-   To replicate from a Microsoft SQL Server \(MSSQL\) or Azure SQL source system, the database user must have the following privileges:


    <table>
    <tr>
    <th valign="top">

    Privilege
    
    </th>
    <th valign="top">

    Object
    
    </th>
    <th valign="top">

    Description
    
    </th>
    <th valign="top">

    Required for initial load
    
    </th>
    <th valign="top">

    Required for delta load
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    `public` role
    
    </td>
    <td valign="top">
    
    Database
    
    </td>
    <td valign="top">
    
    Metadata access
    
    </td>
    <td valign="top">
    
    Yes
    
    </td>
    <td valign="top">
    
    Yes
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `VIEW DATABASE PERFORMANCE STATE`
    
    </td>
    <td valign="top">
    
    Database
    
    </td>
    <td valign="top">
    
    Metadata access

    > ### Note:  
    > For versions earlier than Microsoft SQL Server 2022, the `VIEW DATABASE STATE` privilege is required instead.


    
    </td>
    <td valign="top">
    
    Yes
    
    </td>
    <td valign="top">
    
    Yes
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `SELECT`
    
    </td>
    <td valign="top">
    
    Source table
    
    </td>
    <td valign="top">
    
    Read data from source tables.
    
    </td>
    <td valign="top">
    
    Yes
    
    </td>
    <td valign="top">
    
    Yes
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `ALTER`
    
    </td>
    <td valign="top">
    
    Source table
    
    </td>
    <td valign="top">
    
    Create triggers. Drop triggers for clean up.

    > ### Note:  
    > Triggers can only be created under the source schema. Other replication objects are created under the user schema.


    
    </td>
    <td valign="top">
    
    No
    
    </td>
    <td valign="top">
    
    Yes
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `CREATE TABLE`
    
    </td>
    <td valign="top">
    
    Database
    
    </td>
    <td valign="top">
    
    Create shadow tables.
    
    </td>
    <td valign="top">
    
    No
    
    </td>
    <td valign="top">
    
    Yes
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `CREATE SEQUENCE`
    
    </td>
    <td valign="top">
    
    Database
    
    </td>
    <td valign="top">
    
    Create stored procedures.
    
    </td>
    <td valign="top">
    
    No
    
    </td>
    <td valign="top">
    
    Yes
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `CREATE SEQUENCE`
    
    </td>
    <td valign="top">
    
    Database
    
    </td>
    <td valign="top">
    
    Create sequences.
    
    </td>
    <td valign="top">
    
    No
    
    </td>
    <td valign="top">
    
    Yes
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `ALTER`
    
    </td>
    <td valign="top">
    
    User schema
    
    </td>
    <td valign="top">
    
    Create replication objects in user schema. Drop replication objects for clean up.
    
    </td>
    <td valign="top">
    
    No
    
    </td>
    <td valign="top">
    
    Yes
    
    </td>
    </tr>
    </table>
    
    > ### Note:  
    > This table lists the minimum per-table privileges required for initial and delta loads. Equivalent schema-level privileges \(for example, `SELECT`, `ALTER` on the source schema\) also work because they cover all tables in the schema. Database roles like `db_datareader`, which grant `SELECT` on all tables in the database can also work, depending on your security requirements.

    To enable delta loading, a database schema with the same name as the database user must exist, replication objects \(shadow tables, procedures, sequences\) are created under this user schema. If it does not exist, create it. The database user needs the required privileges on this schema to create and manage replication objects. You can create the necessary user and schema with the following commands:

    ```
    -- Create login / userCREATE USER <ds_rep_user> WITH PASSWORD =<Strong!Password>;-- Create dedicated schema owned by the replication userCREATE SCHEMA <ds_rep_user> AUTHORIZATION <ds_rep_user>;
    ```




<a name="loioa13c8abb328f45be891599c9cc76fb91__MSSQL_connection_properties"/>

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

When you've selected a Data Provisioning Agent, you can configure advanced connection properties to enable specific customer scenarios. In the connection creation wizard, you configure advanced properties in an additional wizard step. When editing the connection to configure the properties, scroll down and click the *Show Advanced Properties* button. Advanced properties have default values that you can override according to your customer scenario’s needs.

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

