<!-- loio057fa4b51c734e679dd70eec9514839d -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Microsoft OneLake Connections

Use the connection to connect to and access objects in Microsoft OneLake.

This topic contains the following sections: Supported Features 

-   [Supported Features](microsoft-onelake-connections-057fa4b.md#loio057fa4b51c734e679dd70eec9514839d__OneLake_usage)
-   [Configuring Connection Properties](microsoft-onelake-connections-057fa4b.md#loio057fa4b51c734e679dd70eec9514839d__connection_properties)



<a name="loio057fa4b51c734e679dd70eec9514839d__OneLake_usage"/>

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

You can use the connection to add source objects to a replication flow.

For more information, see [Cloud Storage Provider Sources](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/4d481a2c620f4b52ba65b360299d7719.html "If you use a cloud storage provider as the source for your replication flow, you need to consider additional specifics and conditions.") :arrow_upper_right:.

</td>
</tr>
</table>



<a name="loio057fa4b51c734e679dd70eec9514839d__connection_properties"/>

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

\[optional\] If you want to make sure that the data is not leaving the region where the data is stored, enter a region. For example `eastus2`. 

</td>
</tr>
<tr>
<td valign="top">

*Root Path*

</td>
<td valign="top">

Enter the root path to specify the object on your Microsoft OneLake account which you want to access with the connection. For example `myworkspace/myitem.itemtype/myfiles`.

</td>
</tr>
<tr>
<td valign="top">

*URL*

</td>
<td valign="top">

\[read only\] Displays the standard global Microsoft OneLake URL `https://onelake.dfs.fabric.microsoft.com/`.

When entering the root path in the *Root Path* field and a region in the *Region* field, these are automatically added to the URL. For example `https://eastus2-onelake.dfs.fabric.microsoft.com/myworkspace/myitem.itemtype/myfiles`

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

\[read only\] Displays authentication type *OAuth 2.0*. 

</td>
</tr>
</table>



### OAuth 2.0


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

If *OAuth Grant Type* = *Client Credentials with X.509 Client Certificate*:


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

*Certificate*

</td>
<td valign="top">

To upload the certificate or certificate chain that is used to authenticate to the remote system, click <span class="SAP-icons-V5"></span> \(Browse\) and select the file. 

</td>
</tr>
<tr>
<td valign="top">

*Private Key*

</td>
<td valign="top">

To upload the private key, click <span class="SAP-icons-V5"></span> \(Browse\) and select the file. 

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

*Replication Flows*

</td>
<td valign="top">

*Replication Flows* are enabled without the need to set any additional connection properties. 

</td>
</tr>
</table>

