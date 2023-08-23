<!-- loiocd06b3c5ab5147c0905e3fa8abd13eb1 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Microsoft Azure Data Lake Store Gen2 Connections

Use the connection to access objects in Microsoft Azure Data Lake Gen2 \(ADL Gen2\). 



<a name="loiocd06b3c5ab5147c0905e3fa8abd13eb1__ADL2_usage"/>

## Using the Connection

The connection type supports the data flow feature.



<a name="loiocd06b3c5ab5147c0905e3fa8abd13eb1__section_nrb_hcc_x4b"/>

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

Select the authentication type to be used: or *Shared Access Signature*. 

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

Upload the X.509 client certificate.

Choose <span class="SAP-icons"></span> \(Browse\) and select the file from your download location.



</td>
</tr>
<tr>
<td valign="top">

*X.509 Client Private Key*



</td>
<td valign="top">

Upload the X.509 client's private key.

Choose <span class="SAP-icons"></span> \(Browse\) and select the file from your download location.



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

*Data Flows* are enabled without the need to set any additional connection properties.

