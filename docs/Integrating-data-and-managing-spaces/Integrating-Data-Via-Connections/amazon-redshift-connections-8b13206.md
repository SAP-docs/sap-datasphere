<!-- loio8b132061d4e149d9a16b3576dda1f613 -->

# Amazon Redshift Connections

Use an *Amazon Redshift* connection to access data from Amazon Redshift 8.x databases. 

> ### Note:  
> The connection type is not supported in spaces with storage type *SAP HANA Data Lake Files* \(file spaces\).

This topic contains the following sections:

-   [Supported Features](amazon-redshift-connections-8b13206.md#loio8b132061d4e149d9a16b3576dda1f613__Redshift_usage)
-   [Prerequisites](amazon-redshift-connections-8b13206.md#loio8b132061d4e149d9a16b3576dda1f613__Redshift_prerequisites)
-   [Configuring Connection Properties](amazon-redshift-connections-8b13206.md#loio8b132061d4e149d9a16b3576dda1f613__Redshift_connection_properties)



<a name="loio8b132061d4e149d9a16b3576dda1f613__Redshift_usage"/>

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

For more information, see [Monitoring Remote Tables](../Data-Integration-Monitor/monitoring-remote-tables-4dd95d7.md). 

> ### Note:  
> -   In the view editor of the Data Builder, you can see technical artifacts from the source that you cannot use for modeling. Affected artifacts are tables containing "pkey" or tables from technical schemas pg\_catalog, pg\_internal, and information\_schema, for example. Please ignore these artifacts.



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



<a name="loio8b132061d4e149d9a16b3576dda1f613__Redshift_prerequisites"/>

## Prerequisites



### Remote Tables

Before you can use the connection for remote tables, the following is required:

-   An administrator has connected an SAP HANA smart data integration Data Provisioning Agent to SAP Datasphere and registered the CamelJdbcAdapter.

    For more information, see [Preparing Data Provisioning Agent Connectivity](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/f1a39d1a763e48c8872f45c110a5a4e2.html "Most connection types supporting remote tables use SAP HANA Smart Data Integration (SDI) and its Data Provisioning Agent. Before using the connection, the agent requires an appropriate setup.") :arrow_upper_right:.

-   An administrator has downloaded and installed the required JDBC library in the <code><i class="varname">&lt;DPAgent_root&gt;</i>/camel/lib</code> folder and restarted the Data Provisioning Agent before registering the adapter with SAP Datasphere.




### Data Flows

Before you can use the connection for data flows, the following is required:

-   The outbound IP has been added to the source allowlist.

    For information on where a DW administrator can find the IP address, see [Obtain SAP Datasphere IP addresses For Allowlisting in Remote Systems](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/0934f7ed9a534e638299f53ab60866ae.html "Remote systems may restrict access to their instances. The remote system often decides whether an external client, such as SAP Datasphere, can access it based on allowlisted IPs. You must add SAP Datasphere's IP address to the remote system's allowlist before SAP Datasphere attempts access, via connections, for example.") :arrow_upper_right:.

-   A DW administrator has uploaded the required ODBC driver file to SAP Datasphere.

    For more information, see [Upload Third-Party ODBC Drivers (Required for Data Flows)](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/b9b5579054df48c39381d5b17286bf21.html "To enable access to a non-SAP database via ODBC to use it as a source for data flows, you need to upload the required ODBC driver files to SAP Datasphere.") :arrow_upper_right:.




<a name="loio8b132061d4e149d9a16b3576dda1f613__Redshift_connection_properties"/>

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

Enter the host name of the Redshift server. 

</td>
</tr>
<tr>
<td valign="top">

*Port* 

</td>
<td valign="top">

Displays the default port 5439. You can overwrite the port, if required. 

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

Select the SSL certificate verification mode to use when connecting. The default is *false*. 

</td>
</tr>
<tr>
<td valign="top">

\[if *Use SSL* = *true*\] *Validate Server Certificate*

</td>
<td valign="top">

Select if the server certficate should be validated \(*true*\) or not \(*false*\). The default is *false*. 

If you select *true*, then the host name in the certificate must match the host name specified in the *Host* field.

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

Enter the name of the Redshift user that has privileges to connect to the database. 

</td>
</tr>
<tr>
<td valign="top">

*Password* 

</td>
<td valign="top">

Enter the password of the Redshift user. 

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

