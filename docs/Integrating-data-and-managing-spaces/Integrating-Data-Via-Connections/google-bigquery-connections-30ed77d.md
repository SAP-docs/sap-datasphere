<!-- loio30ed77de13864368bdc596099b37ed70 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Google BigQuery Connections

Use the connection to connect to and access data from Google BigQuery. 



This topic contains the following sections:

-   [Supported Features](google-bigquery-connections-30ed77d.md#loio30ed77de13864368bdc596099b37ed70__GBQ_usage)
-   [Configuring Connection Properties](google-bigquery-connections-30ed77d.md#loio30ed77de13864368bdc596099b37ed70__connection_properties)

For information about the required prerequisites, see [Prepare Connectivity to Google BigQuery](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/529cef1eee6a45a69ae4e51951718900.html "To be able to successfully validate and use a connection to a Google BigQuery data source for remote tables, certain preparations have to be made.") :arrow_upper_right:.



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

Remote Tables

</td>
<td valign="top">

You can use remote tables imported from the connection either to access data directly live in the connected source \(federation\) or to copy the data into SAP Datasphere \(snapshot replication\).

For more information, see [Replicating Data and Monitoring Remote Tables](../Data-Integration-Monitor/replicating-data-and-monitoring-remote-tables-4dd95d7.md). 

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

You can use the connection to add target objects to a replication flow.

For more information, see [Google BigQuery Targets](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/56d4472a0e1f44d58e07ca26ab666328.html "If you use Google BigQuery as the target for your replication flow, you need to consider the following additional specifics and conditions.") :arrow_upper_right:.

> ### Note:  
> You can only use a non-SAP target for a replication flow if your admin has assigned capacity units to Premium Outbound Integration. For more information, see [Premium Outbound Integration](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/4e9c6acb5d6a43fa9a6471837399e71c.html "To use a non-SAP target in a replication flow, you need premium outbound integration.") :arrow_upper_right: and [Configure the Size of Your SAP Datasphere Tenant](https://help.sap.com/docs/SAP_DATASPHERE/9f804b8efa8043539289f42f372c4862/33f8ef4ec359409fb75925a68c23ebc3.html).



</td>
</tr>
</table>



<a name="loio30ed77de13864368bdc596099b37ed70__connection_properties"/>

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
<tr>
<td valign="top">

*Replication Flows*

</td>
<td valign="top">

*Replication Flows* are enabled without the need to set any additional connection properties. 

</td>
</tr>
</table>

