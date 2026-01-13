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

You can use the connection to add target objects to a replication flow.

For more information, see [Google BigQuery Targets for Replication Flows](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/56d4472a0e1f44d58e07ca26ab666328.html "If you use Google BigQuery as the target for your replication flow, you need to consider the following additional specifics and conditions.") :arrow_upper_right:.

> ### Note:  
> You can only use a non-SAP target for a replication flow if your admin has assigned capacity units to Premium Outbound Integration. For more information, see [Premium Outbound Integration](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/4e9c6acb5d6a43fa9a6471837399e71c.html "To use a non-SAP target in a replication flow, you need premium outbound integration.") :arrow_upper_right: and [Configure the Size of Your SAP Datasphere Tenant](https://help.sap.com/docs/SAP_DATASPHERE/9f804b8efa8043539289f42f372c4862/33f8ef4ec359409fb75925a68c23ebc3.html).



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



### Remote Tables

Before you can use the connection for remote tables, the following is required:

-   A DW administrator has uploaded the server certificate to SAP Datasphere.

    > ### Note:  
    > The root certificates `GTS Root R1` and `GTS Root R4` \(valid until 2036\) are required. In your browser, open [https://pki.goog/repository/](https://pki.goog/repository/)\(*Google Trust Services Repository*\) to download the certificates \(supported filename extensions are .pem and .crt\).
    > 
    > For more information, see SAP Notes [3424000](https://me.sap.com/notes/3424000) and [3567141](https://me.sap.com/notes/3567141).

    For more information, see [Manage Certificates for Connections](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/46f5467adc5242deb1f6b68083e72994.html "For connections secured by leveraging HTTPS as the underlying transport protocol (using SSL/TLS transport encryption), the server certificate must be trusted. To import a certificate into the SAP Datasphere trust chain, obtain the certificate from the target endpoint and upload it to SAP Datasphere.") :arrow_upper_right:.




### Data Flows and Replication Flows

Before you can use the connection for data flows and replication flows, the following is required:

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

\[optional\] Enter an additional location. By default, SAP Datasphere connects to BigQuery datasets only from Google's default location - `US`. Datasets from any other location will only be available in the*Data Builder* if you enter the additional location here. 

A location can be a region, for example `us-west1`or `asia-east1`, or a multi-region, for example `EU`.

> ### Note:  
> If you provide an invalid location, the connection validation still passes, but failures will happen when you're using the connection in the *Data Builder*.



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
> In file spaces, only replication flows are supported. Remote tables are not supported.



</td>
</tr>
<tr>
<td valign="top">

*Data Flows*

</td>
<td valign="top">

*Data Flows* are enabled without the need to set any additional connection properties.

> ### Note:  
> In file spaces, only replication flows are supported. Data flows are not supported.



</td>
</tr>
</table>

