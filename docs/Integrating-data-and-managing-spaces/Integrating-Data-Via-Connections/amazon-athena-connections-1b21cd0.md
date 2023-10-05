<!-- loio1b21cd00fa9842f5ba747047b80fe3ab -->

# Amazon Athena Connections

Use an *Amazon Athena* connection to access data from Amazon Athena, an interactive query service which can be used to analyze data in Amazon S3 using standard SQL.



<a name="loio1b21cd00fa9842f5ba747047b80fe3ab__section_j1b_byq_spb"/>

## Prerequisites

See: [Prepare Connectivity to Amazon Athena](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/8d80f60960294e1f9c3cea4778024663.html "To be able to successfully validate and use a connection to Amazon Athena for remote tables certain preparations have to be made.") :arrow_upper_right:



<a name="loio1b21cd00fa9842f5ba747047b80fe3ab__Athena_usage"/>

## Using the Connection

The connection type supports the remote table feature.

Supported data access methods for remote tables:

-   Remote
-   Replication \(snapshot\)

For more information, see [Replicating Data and Monitoring Remote Tables](../Data-Integration-Monitor/replicating-data-and-monitoring-remote-tables-4dd95d7.md). 



<a name="loio1b21cd00fa9842f5ba747047b80fe3ab__section_nrb_hcc_x4b"/>

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

*Region* 



</td>
<td valign="top">

Enter the AWS region in your Amazon Athena regional endpoint that you use to make your requests. For example, `us-west-2`. 



</td>
</tr>
<tr>
<td valign="top">

*Workgroup* 



</td>
<td valign="top">

Enter the name of the workgroup. Amazon Athena uses workgroups to control query access and costs. The default workgroup is `primary`. 



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

*Access Key* 



</td>
<td valign="top">

Enter the access key ID of the user that the application must use to authenticate. 



</td>
</tr>
<tr>
<td valign="top">

*Secret Key* 



</td>
<td valign="top">

Enter the secret access key of the user that the application must use to authenticate. 



</td>
</tr>
</table>



### Features

*Remote Tables* are enabled without the need to set any additional connection properties.

