<!-- loioa7b660a0a4ef4a4fbee57b44f5b2147d -->

# Amazon Simple Storage Service Connections

Use an *Amazon Simple Storage Service* connection to connect to and access data from objects in Amazon S3 buckets. 

> ### Note:  
> The connection type is not supported in spaces with storage type *SAP HANA Data Lake Files* \(file spaces\).



This topic contains the following sections:

-   [Supported Features](amazon-simple-storage-service-connections-a7b660a.md#loioa7b660a0a4ef4a4fbee57b44f5b2147d__S3_usage)
-   [Configuring Connection Properties](amazon-simple-storage-service-connections-a7b660a.md#loioa7b660a0a4ef4a4fbee57b44f5b2147d__connection_properties)



<a name="loioa7b660a0a4ef4a4fbee57b44f5b2147d__S3_usage"/>

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

Replication Flows

</td>
<td valign="top">

You can use the connection to add source and target objects to a replication flow.

For more information, see:

-   [Cloud Storage Provider Sources for Replication Flows](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/4d481a2c620f4b52ba65b360299d7719.html "If you use a cloud storage provider as the source for your replication flow, you need to consider additional specifics and conditions.") :arrow_upper_right:

-   [Cloud Storage Provider Targets](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/43d93a27150a4a218e3df14e3abdf456.html "If you use a cloud storage provider as the target for your replication flow, you need to consider additional specifics and conditions.") :arrow_upper_right:


> ### Note:  
> You can only use a non-SAP target for a replication flow if your admin has assigned capacity units to Premium Outbound Integration. For more information, see [Premium Outbound Integration](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/4e9c6acb5d6a43fa9a6471837399e71c.html "To use a non-SAP target in a replication flow, you need premium outbound integration.") :arrow_upper_right: and [Configure the Size of Your SAP Datasphere Tenant](https://help.sap.com/docs/SAP_DATASPHERE/9f804b8efa8043539289f42f372c4862/33f8ef4ec359409fb75925a68c23ebc3.html).



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

</td>
</tr>
</table>

