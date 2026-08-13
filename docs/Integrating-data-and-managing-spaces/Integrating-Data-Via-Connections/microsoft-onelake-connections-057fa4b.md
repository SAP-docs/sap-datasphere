<!-- loio057fa4b51c734e679dd70eec9514839d -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Microsoft OneLake Connections

Use the connection to connect to and access objects in Microsoft OneLake.

This topic contains the following sections:

-   [Supported Features](microsoft-onelake-connections-057fa4b.md#loio057fa4b51c734e679dd70eec9514839d__OneLake_usage)
-   [Prerequisites](microsoft-onelake-connections-057fa4b.md#loio057fa4b51c734e679dd70eec9514839d__OneLake_prerequisites)
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

You can use the connection to add source objects to a replication flow \(see [Select Source and Target Connections for Replication Flows](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/10891192186c4920b08939a7b46adc79.html "Select the source connection you want to read data from and the target connection you want to replicate data to.") :arrow_upper_right:\).

For more information, see [Cloud Storage Provider Sources for Replication Flows](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/4d481a2c620f4b52ba65b360299d7719.html "If you use a cloud storage provider as the source for your replication flow, you need to consider additional specifics and conditions.") :arrow_upper_right:.

</td>
</tr>
</table>



<a name="loio057fa4b51c734e679dd70eec9514839d__OneLake_prerequisites"/>

## Prerequisites

If you want to prevent your data from being routed publicly through the internet, you can use Cloud Connector as a TLS tunnel between the customer virtual private network and SAP Datasphere to privately route the data.

Two service endpoints and their corresponding Cloud Connector system mappings are required:

-   global data endpoint \(via TCP protocol\) - used for accessing Microsoft OneLake
-   Microsoft OAuth endpoint \(via TCP protocol\) - used for authentication

When configuring Cloud Connector for the data endpoint, ensure you create the system mapping with the following settings:

-   *Back-end Type*: Non-SAP System

-   *Protocol*: TCP

-   *Internal Host*: global URL used to access Microsoft OneLake \(`onelake.dfs.fabric.microsoft.com`\)
-   *Port or Port Range*: port for the endpoint
-   *Virtual Host*: must be the same as the internal host
-   *Virtual Port*: must be the same as the internal port
-   *Check Internal Host*: deselected

When configuring Cloud Connector for the Microsoft OAuth endpoint, ensure you create the system mapping with the following settings:

-   *Back-end Type*: Non-SAP System

-   *Protocol*: TCP

-   *Internal Host*: authentication endpoint used to request the access token for OAuth 2.0 authorization \(`login.microsoftonline.com`\)
-   *Port or Port Range*: port for the endpoint
-   *Virtual Host*: must be the same as the internal host
-   *Virtual Port*: must be the same as the internal port
-   *Check Internal Host*: deselected

For more information, see [Configure Cloud Connector](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/f289920243a34127b0c8b13012a1a4b5.html "Configure Cloud Connector before connecting to on-premise sources and using them in various use cases. In the Cloud Connector administration, connect the SAP Datasphere subaccount to your Cloud Connector, add a mapping to each relevant source system in your network, and specify accessible resources for each source system.") :arrow_upper_right:.



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

For more information, see [Data Residency](https://learn.microsoft.com/en-us/fabric/onelake/onelake-access-api#data-residency) in the *Microsoft OneLake* documentation.

</td>
</tr>
<tr>
<td valign="top">

*Root Path*

</td>
<td valign="top">

Enter the root path to specify the objects on your Microsoft OneLake account which you want to access with the connection. For example `myworkspace/myitem.itemtype/myfiles`.

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

Set the property to *true* if you want to use replication flows and your Microsoft OneLake workspace does not have a public endpoint. The default is *false*.

</td>
</tr>
<tr>
<td valign="top">

\[if *Use Cloud Connector* = *true*\] *Location* 

</td>
<td valign="top">

Select the location ID for the Cloud Connector instance that is set up for connecting to Microsoft OneLake.

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

