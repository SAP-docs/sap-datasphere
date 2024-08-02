<!-- loiocd06b3c5ab5147c0905e3fa8abd13eb1 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Microsoft Azure Data Lake Store Gen2 Connections

Use the connection to connect to and access objects in Microsoft Azure Data Lake Gen2 \(ADL Gen2\). 



This topic contains the following sections:

-   [Supported Features](microsoft-azure-data-lake-store-gen2-connections-cd06b3c.md#loiocd06b3c5ab5147c0905e3fa8abd13eb1__ADL2_usage)
-   [Configuring Connection Properties](microsoft-azure-data-lake-store-gen2-connections-cd06b3c.md#loiocd06b3c5ab5147c0905e3fa8abd13eb1__connection_properties)

For information about the required prerequisites, see [Prepare Connectivity to Microsoft Azure Data Lake Store Gen2](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/6b3fd2c371284637bac465edb9cc9e50.html "To be able to successfully validate and use a connection to Microsoft Azure Data Lake Store Gen2 certain preparations have to be made.") :arrow_upper_right:.



<a name="loiocd06b3c5ab5147c0905e3fa8abd13eb1__ADL2_usage"/>

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

For more information, see [Using a Cloud Storage Provider As the Target](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/43d93a27150a4a218e3df14e3abdf456.html "If you use a cloud storage provider as the target for your replication flow, you need to consider additional specifics and conditions.") :arrow_upper_right:. 

> ### Note:  
> You can only use a non-SAP target for a replication flow if your admin has assigned capacity units to Premium Outbound Integration. For more information, see [Configure the Size of Your SAP Datasphere Tenant](https://help.sap.com/docs/SAP_DATASPHERE/9f804b8efa8043539289f42f372c4862/33f8ef4ec359409fb75925a68c23ebc3.html).



</td>
</tr>
</table>



<a name="loiocd06b3c5ab5147c0905e3fa8abd13eb1__connection_properties"/>

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

*Storage Account Name*  

</td>
<td valign="top">

Enter the name of the Azure Data Lake Storage Gen2 used for authentication. 

</td>
</tr>
<tr>
<td valign="top">

*Root Path*  

</td>
<td valign="top">

\[optional\] Enter the root path name for browsing. It starts with a slash and the file system name. For example `/MyFileSystem/MyFolder`. The file system must be provided. Any path used with this connection will be prefixed with this root path. 

</td>
</tr>
</table>



### Authentication


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

*Authentication Type*  

</td>
<td valign="top">

Select the authentication type to be used: 

You can select:

-   *Shared Key \(default\)*
-   *Shared Access Signature*
-   *OAuth 2.0*

Shared key provides full access to your storage account while with shared access signature you can provide secure delegate access to the storage account resources.

</td>
</tr>
</table>



### Credentials \(Shared Key\)

If *Authentication Type* = *Shared Key*:


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

*Account Key*  

</td>
<td valign="top">

Enter the account key used in the shared key authorization. 

</td>
</tr>
</table>



### Credentials \(Shared Access Signature\)

If *Authentication Type* = *Shared Access Signature*:


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

*SAS Token*  

</td>
<td valign="top">

Enter the shared access signature token \(SAS token\) used in shared access signature authentication. 

</td>
</tr>
</table>



### OAuth 2.0

If *Authentication Type* = *OAuth 2.0*:


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

*OAuth Grant Type*  

</td>
<td valign="top">

Select the grant type. 

You can select:

-   *Client Credentials with X.509 Client Certificate*
-   *Client Credentials*
-   *User Name and Password*



</td>
</tr>
<tr>
<td valign="top">

\[if *OAuth Grant Type* = *Client Credentials with X.509 Client Certificate* or *Client Credentials*\] *OAuth Token Endpoint*  

</td>
<td valign="top">

Enter the token endpoint that the application must use to get the access token. 

</td>
</tr>
<tr>
<td valign="top">

\[if *OAuth Grant Type* = *User Name and Password*\] *OAuth Client Endpoint*  

</td>
<td valign="top">

Enter the client endpoint to get the access token for authorization method *User Name and Password*. 

</td>
</tr>
</table>



### Credentials \(OAuth 2.0 with X.509 Client Certificate\)


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

*Client ID*

</td>
<td valign="top">

Enter the client ID. 

</td>
</tr>
<tr>
<td valign="top">

*X.509 Client Certificate*

</td>
<td valign="top">

To upload the certificate or certificate chain that is used to authenticate to the remote system, click <span class="SAP-icons-V5"></span> \(Browse\) and select the file from your download location. 

</td>
</tr>
<tr>
<td valign="top">

*X.509 Client Private Key*

</td>
<td valign="top">

To upload the private key, click <span class="SAP-icons-V5"></span> \(Browse\) and select the file from your download location. 

</td>
</tr>
</table>



### Credentials \(OAuth 2.0\)

If *OAuth Grant Type* = *Client Credentials*:


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

*Client ID*

</td>
<td valign="top">

Enter the client ID. 

</td>
</tr>
<tr>
<td valign="top">

*Client Secret*

</td>
<td valign="top">

Enter the client secret.

</td>
</tr>
</table>

If *OAuth Grant Type* = *User Name And Password*:


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

Enter the name of the OAuth user.

</td>
</tr>
<tr>
<td valign="top">

*Password \(OAuth 2.0\)*

</td>
<td valign="top">

Enter the OAuth password.

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

*Data Flows*

</td>
<td valign="top">

*Data Flows* are enabled without the need to set any additional connection properties. 

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

