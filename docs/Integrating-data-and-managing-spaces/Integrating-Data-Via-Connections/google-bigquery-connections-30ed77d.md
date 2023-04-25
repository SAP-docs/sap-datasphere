<!-- loio30ed77de13864368bdc596099b37ed70 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Google BigQuery Connections

Use the connection to access data from a Google BigQuery data source.. 



<a name="loio30ed77de13864368bdc596099b37ed70__section_j1b_byq_spb"/>

## Prerequisites

See: [Prepare Connectivity to Google BigQuery](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/529cef1eee6a45a69ae4e51951718900.html "To be able to successfully validate and use a connection to a Google BigQuery data source for remote tables, certain preparations have to be made.") :arrow_upper_right:



<a name="loio30ed77de13864368bdc596099b37ed70__GBQ_usage"/>

## Using the Connection

The connection type supports the remote table feature.

Supported data access methods for remote tables:

-   Remote
-   Replication \(snapshot\)

For more information, see [Replicating Data and Monitoring Remote Tables](../Data-Integration-Monitor/replicating-data-and-monitoring-remote-tables-4dd95d7.md). 



<a name="loio30ed77de13864368bdc596099b37ed70__section_nrb_hcc_x4b"/>

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

 Enter the content of the json key file that is used for authentication.

Choose <span class="SAP-icons"></span> \(Browse\) and select the file from your download location.



</td>
</tr>
</table>



### Features

*Remote Tables* are enabled without the need to set any additional connection properties.

