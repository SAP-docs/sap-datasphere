<!-- loioeeae3aca6d0040149f7b1e658c434f15 -->

# Generic JDBC Connections

Use a *Generic JDBC* connection to access data from tables and views in any supported data source for which a JDBC driver is available. You can use this connection type to connect to most databases that have SQL-based data types and functions, and a JDBC driver. If a specific connection type is available for your database in SAP Datasphere, we recommend to use the specific connection type instead of *Generic JDBC*.

> ### Note:  
> The connection type is not supported in spaces with storage type *SAP HANA Data Lake Files* \(file spaces\).

This topic contains the following sections:

-   [Supported Features](generic-jdbc-connections-eeae3ac.md#loioeeae3aca6d0040149f7b1e658c434f15__JDBC_usage)
-   [Prerequisites](generic-jdbc-connections-eeae3ac.md#loioeeae3aca6d0040149f7b1e658c434f15__JDBC_prerequisites)
-   [Configuring Connection Properties](generic-jdbc-connections-eeae3ac.md#loioeeae3aca6d0040149f7b1e658c434f15__JDBC_connection_properties)



<a name="loioeeae3aca6d0040149f7b1e658c434f15__JDBC_usage"/>

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

You can use remote tables imported from the connection either to access data directly live in the connected source \(federation\) or to copy the data into SAP Datasphere \(replication\).For more information, see [Monitoring Remote Tables](../Data-Integration-Monitor/monitoring-remote-tables-4dd95d7.md).

</td>
</tr>
</table>



<a name="loioeeae3aca6d0040149f7b1e658c434f15__JDBC_prerequisites"/>

## Prerequisites

Before you can use the connection for remote tables, the following is required:

-   An administrator has connected an SAP HANA smart data integration Data Provisioning Agent to SAP Datasphere and registered the CamelJdbcAdapter.

    For more information, see [Preparing Data Provisioning Agent Connectivity](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/f1a39d1a763e48c8872f45c110a5a4e2.html "Most connection types supporting remote tables use SAP HANA Smart Data Integration (SDI) and its Data Provisioning Agent. Before using the connection, the agent requires an appropriate setup.") :arrow_upper_right:.

-   It has been checked that the data source is supported by the CamelJdbcAdapter.

    For latest information about supported data sources and versions, see the [SAP HANA Smart Data Integration Product Availability Matrix \(PAM\)](https://support.sap.com/content/dam/launchpad/en_us/pam/pam-essentials/TIP/PAM_HANA_SDI_2_0.pdf).

    > ### Note:  
    > For information about unsupported data sources, see SAP Note [3130999](https://me.sap.com/notes/3130999).

-   An administrator has downloaded and installed the required JDBC library in the <code><i class="varname">&lt;DPAgent_root&gt;</i>/camel/lib</code> folder and restarted the Data Provisioning Agent before registering the adapter with SAP Datasphere.

    For more information, see [Set up the Camel JDBC Adapter](https://help.sap.com/viewer/7952ef28a6914997abc01745fef1b607/latest/en-US/1247c9518f8d4b5b93fa2ad54cb2dcf6.html) in the *SAP HANA Smart Data Integration and SAP HANA Smart Data Quality Installation and Configuration Guide*.

    For information about the proper JDBC library for your source, see the *SAP HANA smart data integration Product Availability Matrix \(PAM\)*.




<a name="loioeeae3aca6d0040149f7b1e658c434f15__JDBC_connection_properties"/>

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

*JDBC Driver Class* 

</td>
<td valign="top">

Enter the JDBC driver class for the database you are using. 

</td>
</tr>
<tr>
<td valign="top">

*JDBC URL*

</td>
<td valign="top">

Enter the URL for the JDBC driver.

> ### Note:  
> The JDBC URL is stored as plain text and is not stored in encrypted form. It is visible when editing the connection or when accessing the remote source with a database analysis user. Therefore, do not provide any sensitive information like passwords in the URL.



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

Enter the database user name.

</td>
</tr>
<tr>
<td valign="top">

*Password*

</td>
<td valign="top">

Enter the password for the database user.

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
</table>

