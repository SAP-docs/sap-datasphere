<!-- loioa7b660a0a4ef4a4fbee57b44f5b2147d -->

# Amazon Simple Storage Service Connections

Use an *Amazon Simple Storage Service* connection to connect to and access data from objects in Amazon S3 buckets. 



This topic contains the following sections:

-   [Supported Features](amazon-simple-storage-service-connections-a7b660a.md#loioa7b660a0a4ef4a4fbee57b44f5b2147d__S3_usage)
-   [Prerequisites](amazon-simple-storage-service-connections-a7b660a.md#loioa7b660a0a4ef4a4fbee57b44f5b2147d__S3_prerequisites)
-   [Configuring Connection Properties](amazon-simple-storage-service-connections-a7b660a.md#loioa7b660a0a4ef4a4fbee57b44f5b2147d__connection_properties)



<a name="loioa7b660a0a4ef4a4fbee57b44f5b2147d__S3_usage"/>

## Supported Features

> ### Note:  
> In file spaces, data flows are not supported.


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

You can use the connection to add source and target objects to a replication flow \(see [Select Source and Target Connections for Replication Flows](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/10891192186c4920b08939a7b46adc79.html "Select the source connection you want to read data from and the target connection you want to replicate data to.") :arrow_upper_right:\).

For more information, see:

-   [Cloud Storage Provider Sources for Replication Flows](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/4d481a2c620f4b52ba65b360299d7719.html "If you use a cloud storage provider as the source for your replication flow, you need to consider additional specifics and conditions.") :arrow_upper_right:

-   [Cloud Storage Provider Targets for Replication Flows](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/43d93a27150a4a218e3df14e3abdf456.html "If you use a cloud storage provider as the target for your replication flow, you need to consider additional specifics and conditions.") :arrow_upper_right:


> ### Note:  
> You can only use a non-SAP target for a replication flow if your admin has assigned capacity units to Premium Outbound Integration. For more information, see [Premium Outbound Integration](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/4e9c6acb5d6a43fa9a6471837399e71c.html "To use a non-SAP target in a replication flow, you need premium outbound integration.") :arrow_upper_right: and [Configure the Size of Your SAP Datasphere Tenant](https://help.sap.com/docs/SAP_DATASPHERE/9f804b8efa8043539289f42f372c4862/33f8ef4ec359409fb75925a68c23ebc3.html).



</td>
</tr>
<tr>
<td valign="top">

Data Flows

</td>
<td valign="top">

You can use the connection to add source objects to a data flow \(see [Creating a Data Flow](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/e30fd1417e954577baae3246ea470c3f.html "Create a data flow to move and transform data in an intuitive graphical interface. You can drag and drop sources from the Source Browser, join them as appropriate, add other operators to remove or create columns, aggregate data, and do Python scripting, before writing the data to the target table.") :arrow_upper_right:\).

</td>
</tr>
</table>



<a name="loioa7b660a0a4ef4a4fbee57b44f5b2147d__S3_prerequisites"/>

## Prerequisites

If you want to prevent your data from being routed publicly through the internet, you can use Cloud Connector as a TLS tunnel between the customer virtual private network and SAP Datasphere to privately route the data.

When configuring Cloud Connector, create both of the following system mappings for the regional endpoint where your Amazon S3 bucket is located:

-   endpoint for path-style URL access:
    -   *Back-end Type*: Non-SAP System

    -   *Protocol*: TCP

    -   *Internal Host*: Amazon S3 regional endpoint \(for example, `s3.eu-central-1.amazonaws.com`\)
    -   *Port or Port Range*: port for the Amazon S3 regional endpoint
    -   *Virtual Host*: must be the same as the internal host
    -   *Virtual Port*: must be the same as the internal port
    -   *Check Internal Host*: deselected

-   endpoint for virtual-hosted–style URL access:
    -   *Back-end Type*: Non-SAP System

    -   *Protocol*: HTTPS

    -   *Internal Host*: Amazon S3 regional endpoint including the name of the bucket that you want to access \(for example, <code><i class="varname">&lt;bucket-name&gt;</i>.s3.eu-central-1.amazonaws.com</code>\)
    -   *Port or Port Range*: port for the Amazon S3 regional endpoint
    -   *Virtual Host*: must be the same as the internal host
    -   *Virtual Port*: 80
    -   *Allow Principal Propagation*: deselected
    -   *Host in Request Header*: Use Internal Host


When you want to provide a \(legacy\) global endpoint in the *Endpoint* field of the connection details in SAP Datasphere, you must create both of the system mappings for the regional endpoint as described above, and in addition create the Cloud Connector system mappings for the global endpoint with the following differences in the settings:

-   endpoint for path-style URL access:
    -   *Back-end Type*: Non-SAP System

    -   *Protocol*: TCP

    -   *Internal Host*: Amazon S3 global endpoint \(`s3.amazonaws.com`\)
    -   *Port or Port Range*: port for the Amazon S3 global endpoint
    -   *Virtual Host*: must be the same as the internal host
    -   *Virtual Port*: must be the same as the internal port
    -   *Check Internal Host*: deselected

-   endpoint for virtual-hosted–style URL access:
    -   *Back-end Type*: Non-SAP System

    -   *Protocol*: HTTPS

    -   *Internal Host*: Amazon S3 global endpoint including the name of the bucket that you want to access \(for example, <code><i class="varname">&lt;bucket-name&gt;</i>.s3.amazonaws.com</code>\)
    -   *Port or Port Range*: port for the Amazon S3 global endpoint
    -   *Virtual Host*: must be the same as the internal host
    -   *Virtual Port*: 80
    -   *Allow Principal Propagation*: deselected
    -   *Host in Request Header*: Use Internal Host


> ### Note:  
> If you're using a Virtual Private Cloud \(VPC\) endpoint, this needs to be reflected accordingly in the host and port fields fields of the system mappings.

For more information, see [Configure Cloud Connector](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/f289920243a34127b0c8b13012a1a4b5.html "Configure Cloud Connector before connecting to on-premise sources and using them in various use cases. In the Cloud Connector administration, connect the SAP Datasphere subaccount to your Cloud Connector, add a mapping to each relevant source system in your network, and specify accessible resources for each source system.") :arrow_upper_right:.



<a name="loioa7b660a0a4ef4a4fbee57b44f5b2147d__connection_properties"/>

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

*Endpoint* 

</td>
<td valign="top">

Enter the endpoint URL of the Amazon S3 server, for example `s3.amazonaws.com`. The protocol prefix is not required. 

> ### Note:  
> When using *Assume Role*, you must enter the regional endpoint, for example `s3.us-west-2.amazonaws.com`.



</td>
</tr>
<tr>
<td valign="top">

*Protocol* 

</td>
<td valign="top">

Select the protocol. The default value is *HTTPS*. The value that you provide overwrites the value from the endpoint, if already set. 

</td>
</tr>
<tr>
<td valign="top">

*Root Path* 

</td>
<td valign="top">

\[optional\] Enter the root path name for browsing objects. The value starts with the character slash. For example,`/My Folder/MySubfolder`. 

If you have specified the root path, then any path used with this connection is prefixed with the root path.

</td>
</tr>
</table>



### Cloud Connector


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

Set the property to *true* if you want to use replication flows and your Amazon S3 bucket does not have a public endpoint. The default is *false*.

</td>
</tr>
<tr>
<td valign="top">

\[if *Use Cloud Connector* = *true*\] *Location* 

</td>
<td valign="top">

Select the location ID for the Cloud Connector instance that is set up for connecting to the endpoint.

> ### Note:  
> To select another location ID than the default location, *Connection* privilege with *Read* permission is required.



</td>
</tr>
<tr>
<td valign="top">

\[if *Use Cloud Connector* = *true*\] *Virtual Destination* 

</td>
<td valign="top">

We recommend to select *Derive Virtual Host and Port from Connection Details*. If you select *Enter Virtual Host and Port in Separate Fields*, the values you enter in the *Virtual Host* and *Virtual Port* field, won't be considered for the connection.

</td>
</tr>
<tr>
<td valign="top">

\[if *Virtual Destination* = *Enter Virtual Host and Port in Separate Fields*\] *Virtual Host* 

</td>
<td valign="top">

Any value you enter here, won't be considered, instead the connection uses internal host and port.

</td>
</tr>
<tr>
<td valign="top">

\[if *Virtual Destination* = *Enter Virtual Host and Port in Separate Fields*\] *Virtual Port* 

</td>
<td valign="top">

Any value you enter here, won't be considered, instead the connection uses internal host and port.

</td>
</tr>
</table>



### Server Side Encryption


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

*Use Server Side Encryption* 

</td>
<td valign="top">

\[optional\] Select *true* \(default\) if you want to use S3 objects encrypted through server side encryption. 

</td>
</tr>
<tr>
<td valign="top">

*Encryption Option* 

</td>
<td valign="top">

\[optional\] You can select: 

-   *Encryption with Amazon S3 Managed Keys \(SSE-S3\)* \(default\) if your objects are encrypted using the default encryption configuration for objects in your Amazon S3 buckets.

-   *Encryption with AWS Key Management Service Keys \(SSE-KMS\)* if your Amazon S3 buckets are configured to use AWS KMS keys.




</td>
</tr>
<tr>
<td valign="top">

\[if *Encryption Option* = *Encryption with AWS Key Management Service Keys \(SSE-KMS\)*\] *KMS Key ARN* 

</td>
<td valign="top">

Enter the KMS key Amazon Resource Name \(ARN\) for the customer managed key which has been created to encrypt the objects in your Amazon S3 buckets. 

</td>
</tr>
</table>



### Assume Role


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

*Use Assume Role* 

</td>
<td valign="top">

\[optional\] Select *true* if you want to use temporary security credentials and restrict access to your Amazon S3 buckets based on an Identity and Access Management role \(IAM role\). The default value is *false*. 

</td>
</tr>
<tr>
<td valign="top">

\[if *Use Assume Role* = *true*\] *Role ARN* 

</td>
<td valign="top">

Enter the role Amazon Resource Name \(ARN\) of the assumed IAM role. 

</td>
</tr>
<tr>
<td valign="top">

\[if *Use Assume Role* = *true*\] *Role Session Name* 

</td>
<td valign="top">

\[optional\] Enter the name to uniquely identify the assumed role session. 

</td>
</tr>
<tr>
<td valign="top">

\[if *Use Assume Role* = *true*\] *Duration of Role Session \(in Seconds\)* 

</td>
<td valign="top">

\[optional\] Enter the duration. The default duration is *3600* seconds.

</td>
</tr>
<tr>
<td valign="top">

\[if *Use Assume Role* = *true*\] *External ID* 

</td>
<td valign="top">

\[optional\] If an external ID is used to make sure that SAP Datasphere as a specified third party can assume the role, enter the ID.

</td>
</tr>
<tr>
<td valign="top">

\[if *Use Assume Role* = *true*\] *Role Policy* 

</td>
<td valign="top">

\[optional\] If you want to use a session policy, enter the respective IAM policy in JSON format.

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

Enter the access key ID of the user that is used to authenticate to Amazon S3. 

</td>
</tr>
<tr>
<td valign="top">

*Secret Key* 

</td>
<td valign="top">

Enter the secret access key of the user that is used to authenticate to Amazon S3. 

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

*Data Flows*

</td>
<td valign="top">

*Data Flows* are enabled without the need to set any additional connection properties.

> ### Note:  
> In file spaces or when using Cloud Connector, data flows are not supported.



</td>
</tr>
</table>

