<!-- loio30ed77de13864368bdc596099b37ed70 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Google BigQuery Connections

Use the connection to connect to and access data from Google BigQuery. 



This topic contains the following sections:

-   [Supported Features](google-bigquery-connections-30ed77d.md#loio30ed77de13864368bdc596099b37ed70__GBQ_usage)
-   [Prerequisites](google-bigquery-connections-30ed77d.md#loio30ed77de13864368bdc596099b37ed70__GBQ_prerequisites)
-   [Configuring Connection Properties](google-bigquery-connections-30ed77d.md#loio30ed77de13864368bdc596099b37ed70__GBQ_connection_properties)



<a name="loio30ed77de13864368bdc596099b37ed70__GBQ_usage"/>

## Supported Features

> ### Note:  
> In file spaces or when using Cloud Connector, remote tables and data flows are not supported.


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

You can use the connection to add target objects to a replication flow.

For more information, see [Google BigQuery Targets for Replication Flows](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/56d4472a0e1f44d58e07ca26ab666328.html "If you use Google BigQuery as the target for your replication flow, you need to consider the following additional specifics and conditions.") :arrow_upper_right:.

</td>
</tr>
<tr>
<td valign="top">

Remote Tables

</td>
<td valign="top">

You can use remote tables imported from the connection either to access data directly live in the connected source \(federation\) or to copy the data into SAP Datasphere \(snapshot replication\).

For more information, see [Monitoring Remote Tables](../Data-Integration-Monitor/monitoring-remote-tables-4dd95d7.md). 

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



<a name="loio30ed77de13864368bdc596099b37ed70__GBQ_prerequisites"/>

## Prerequisites



### Replication Flows

Before you can use the connection for replication flows, the following is required:

-   A DW administrator has uploaded the required ODBC driver file to SAP Datasphere.

    For more information, see [Upload Third-Party ODBC Drivers (Required for Data Flows)](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/b9b5579054df48c39381d5b17286bf21.html "To enable access to a non-SAP database via ODBC to use it as a source for data flows, you need to upload the required ODBC driver files to SAP Datasphere.") :arrow_upper_right:.

-   If you want to prevent your data from being routed publicly through the internet, you can use Cloud Connector as a TLS tunnel between the customer virtual private network and SAP Datasphere to privately route the data. In this case, two service endpoints and their corresponding Cloud Connector system mappings are required:

    -   REST API endpoint \(via HTTPS protocol\) - used for retrieving metadata from Google BigQuery
    -   Storage API endpoint \(via TCP protocol\) - used for writing data into the Google BigQuery target table

    For more information, see [Configure Cloud Connector](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/f289920243a34127b0c8b13012a1a4b5.html "Configure Cloud Connector before connecting to on-premise sources and using them in various use cases. In the Cloud Connector administration, connect the SAP Datasphere subaccount to your Cloud Connector, add a mapping to each relevant source system in your network, and specify accessible resources for each source system.") :arrow_upper_right:.

    > ### Note:  
    > The virtual hosts configured in the Cloud Connector system mappings must match the Google BigQuery service endpoints \(internal hosts in the system mappings\) exactly for both the REST and Storage API.




### Remote Tables

Before you can use the connection for remote tables, the following is required:

-   A DW administrator has uploaded the server certificate to SAP Datasphere.

    > ### Note:  
    > The root certificates `GTS Root R1` and `GTS Root R4` \(valid until 2036\) are required. In your browser, open [https://pki.goog/repository/](https://pki.goog/repository/)\(*Google Trust Services Repository*\) to download the certificates \(supported filename extensions are .pem and .crt\).
    > 
    > For more information, see SAP Notes [3424000](https://me.sap.com/notes/3424000) and [3567141](https://me.sap.com/notes/3567141).

    For more information, see [Manage Certificates for Connections](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/46f5467adc5242deb1f6b68083e72994.html "For connections secured by leveraging HTTPS as the underlying transport protocol (using SSL/TLS transport encryption), the server certificate must be trusted. To import a certificate into the SAP Datasphere trust chain, obtain the certificate from the target endpoint and upload it to SAP Datasphere.") :arrow_upper_right:.




### Data Flows

Before you can use the connection for data flows, the following is required:

-   A DW administrator has uploaded the required ODBC driver file to SAP Datasphere.

    For more information, see [Upload Third-Party ODBC Drivers (Required for Data Flows)](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/b9b5579054df48c39381d5b17286bf21.html "To enable access to a non-SAP database via ODBC to use it as a source for data flows, you need to upload the required ODBC driver files to SAP Datasphere.") :arrow_upper_right:.




<a name="loio30ed77de13864368bdc596099b37ed70__GBQ_connection_properties"/>

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

*Project* 

</td>
<td valign="top">

Enter the ID of the Google Cloud project to which you want to connect. You can find the project ID in the json key file that you need for the credentials. 

</td>
</tr>
<tr>
<td valign="top">

*Location* 

</td>
<td valign="top">

\[optional\] Enter a comma-separated list of additional locations. A location can be a region, for example `us-west1`or `asia-east1`, or a multi-region, for example `EU`. 

By default, SAP Datasphere connects to BigQuery datasets only from Google's default location - `US`. Datasets from other locations will only be available in the*Data Builder* if you enter the additional locations here.

</td>
</tr>
<tr>
<td valign="top">

*Use Cloud Connector*

</td>
<td valign="top">

\[optional\] Set to *true* if you want to use replication flows to write data to a Google BigQuery project that does not have a public endpoint. The default is *false*.

</td>
</tr>
</table>



### Cloud Connector for REST API


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

*Location*

</td>
<td valign="top">

\[optional\] Select a location ID. 

> ### Note:  
> To select another location ID than the default location, *Connection* privilege with *Read* permission is required.



</td>
</tr>
<tr>
<td valign="top">

*Virtual Host*

</td>
<td valign="top">

Enter the virtual host that you defined during Cloud Connector configuration. 

</td>
</tr>
<tr>
<td valign="top">

*Virtual Port*

</td>
<td valign="top">

Enter the virtual port that you defined during Cloud Connector configuration. 

</td>
</tr>
</table>



### Cloud Connector for Storage API


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

*Location* 

</td>
<td valign="top">

\[optional\] Select a location ID. 

> ### Note:  
> To select another location ID than the default location, *Connection* privilege with *Read* permission is required.



</td>
</tr>
<tr>
<td valign="top">

*Virtual Host* 

</td>
<td valign="top">

Enter the virtual host that you defined during Cloud Connector configuration. 

</td>
</tr>
<tr>
<td valign="top">

*Virtual Port*

</td>
<td valign="top">

Enter the virtual port that you defined during Cloud Connector configuration. 

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

*Key* 

</td>
<td valign="top">

Upload the json key file that is used for authentication.

Choose <span class="SAP-icons-V5"></span> \(Browse\) and select the file from your download location.

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

*Replication Flows* are enabled without the need to set any additional connection properties. 

</td>
</tr>
<tr>
<td valign="top">

*Remote Tables*

</td>
<td valign="top">

*Remote Tables* are enabled without the need to set any additional connection properties.

> ### Note:  
> In file spaces or when using Cloud Connector, remote tables are not supported.



</td>
</tr>
<tr>
<td valign="top">

*Data Flows*

</td>
<td valign="top">

*Data Flows* are enabled without the need to set any additional connection properties.

> ### Note:  
> In file spaces or when using Cloud Connector, data flows are not supported.



</td>
</tr>
</table>

