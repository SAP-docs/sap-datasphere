<!-- loio1b21cd00fa9842f5ba747047b80fe3ab -->

# Amazon Athena Connections

Use an *Amazon Athena* connection to access data from Amazon Athena, an interactive query service which can be used to analyze data in Amazon S3 using standard SQL.

> ### Note:  
> The connection type is not supported in spaces with storage type *SAP HANA Data Lake Files* \(file spaces\).

This topic contains the following sections:

-   [Supported Features](amazon-athena-connections-1b21cd0.md#loio1b21cd00fa9842f5ba747047b80fe3ab__Athena_usage)
-   [Prerequisites](amazon-athena-connections-1b21cd0.md#loio1b21cd00fa9842f5ba747047b80fe3ab__Athena_prerequisites)
-   [Configuring Connection Properties](amazon-athena-connections-1b21cd0.md#loio1b21cd00fa9842f5ba747047b80fe3ab__Athena_connection_properties)



<a name="loio1b21cd00fa9842f5ba747047b80fe3ab__Athena_usage"/>

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



<a name="loio1b21cd00fa9842f5ba747047b80fe3ab__Athena_prerequisites"/>

## Prerequisites

Before you can use the connection for remote tables, the following is required:

-   A DW administrator has uploaded the server certificates to SAP Datasphere. Two certificates are required, one for Amazon Athena and one for Amazon S3. Region-specific certificates might be required for Amazon Athena. Alternatively, if the common root CA certificate contains trust for both endpoints, Amazon Athena and Amazon Simple Storage Service \(API/Athena and Data/S3\), you can upload the root certificate.

    For more information, see [Manage Certificates for Connections](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/46f5467adc5242deb1f6b68083e72994.html "For connections secured by leveraging HTTPS as the underlying transport protocol (using SSL/TLS transport encryption), the server certificate must be trusted. To import a certificate into the SAP Datasphere trust chain, obtain the certificate from the target endpoint and upload it to SAP Datasphere.") :arrow_upper_right:.




<a name="loio1b21cd00fa9842f5ba747047b80fe3ab__Athena_connection_properties"/>

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

</td>
</tr>
</table>

