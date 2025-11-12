<!-- loiob79b865e64794c7abcd12a54f2f73c8c -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Generic HTTP Connections

Use a *Generic HTTP* connection to connect to an external system via HTTP and run external REST-based API tasks in task chains.

> ### Note:  
> The connection type is not supported in spaces with storage type *SAP HANA Data Lake Files* \(file spaces\).

This topic contains the following sections:

-   -   [Supported Features](generic-http-connections-b79b865.md#loiob79b865e64794c7abcd12a54f2f73c8c__GBQ_usage)
-   [Configuring Connection Properties](generic-http-connections-b79b865.md#loiob79b865e64794c7abcd12a54f2f73c8c__GBQ_connection_properties)



<a name="loiob79b865e64794c7abcd12a54f2f73c8c__GBQ_usage"/>

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

API Tasks

</td>
<td valign="top">

See [Run API Tasks in a Task Chain](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/9a8489ed7443436197fbd8b8ffba61ab.html "Run tasks in a task chain that use a REST-based API to access external systems.") :arrow_upper_right:.

</td>
</tr>
</table>



<a name="loiob79b865e64794c7abcd12a54f2f73c8c__GBQ_connection_properties"/>

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

*Host*

</td>
<td valign="top">

Enter the host name or IP address of the HTTP server.

> ### Note:  
> The Domain Name System \(DNS\) host name can only contain letters \(A-Z\), numbers \(0-9\), minus signs \(-\), and periods \(.\).
> 
> For more information about DNS host names, see [RFC 952 \(DOD Internet Host Table Specification\)](https://www.ietf.org/rfc/rfc952.txt) of the *Internet Engineering Task Force* \(IETF\).



</td>
</tr>
<tr>
<td valign="top">

*Port*

</td>
<td valign="top">

Enter the port number for the HTTP server.

</td>
</tr>
<tr>
<td valign="top">

*Protocol*

</td>
<td valign="top">

Select the protocol to use for connecting to the server: HTTP or HTTPS \(default value\).

</td>
</tr>
<tr>
<td valign="top">

*Path*

</td>
<td valign="top">

\[optional\] Enter a path prefix to the API endpoint. For example, `/api/xyz`.

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

\[optional\] Set to *true* if your source is an on-premise source. The default is *false*. 

</td>
</tr>
<tr>
<td valign="top">

\[if *Use Cloud Connector* = *true*\] *Location* 

</td>
<td valign="top">

\[optional\] Select a location ID. 

> ### Note:  
> To select another location ID than the default location, *Connection.Read* privilege is required. The privilege is neither included in the *DW Integrator* nor in the *DW Space Administrator* role. If you need to select a location ID, ask your tenant administrator to either assign your user to a global role that is based on the *DW Administrator* role or to assign your user to a custom global role \(with license type SAP Datasphere\) that includes the required *Connection.Read* privilege.



</td>
</tr>
<tr>
<td valign="top">

\[if *Use Cloud Connector* = *true*\] *Virtual Destination* 

</td>
<td valign="top">

\[optional\] Select how you want to specify the virtual destination. 

You can select:

-   *Derive Virtual Host and Port from Connection Details* \(default\)

    If host and port entered in the connection details match the virtual host and port from the Cloud Connector configuration, you don't need to enter the values manually.

-   *Enter Virtual Host and Port in Separate Fields*




</td>
</tr>
<tr>
<td valign="top">

\[if *Virtual Destination* = *Enter Virtual Host and Port in Separate Fields*\] *Virtual Host* 

</td>
<td valign="top">

Enter the virtual host that you defined during Cloud Connector configuration. 

</td>
</tr>
<tr>
<td valign="top">

\[if *Virtual Destination* = *Enter Virtual Host and Port in Separate Fields*\] *Virtual Port* 

</td>
<td valign="top">

Enter the virtual port that you defined during Cloud Connector configuration. 

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

Select the authentication type to use to connect to the HTTP server. 

You can select:

-   *OAuth 2.0* \(default value\)
-   *User Name And Password* for basic authentication
-   *No Authentication* for no authentication



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

*OAuth Token Endpoint*

</td>
<td valign="top">

Enter the token endpoint that the application must use.

</td>
</tr>
<tr>
<td valign="top">

*OAuth Scope*

</td>
<td valign="top">

Enter the OAuth scope value.

</td>
</tr>
<tr>
<td valign="top">

*OAuth Resource*

</td>
<td valign="top">

Enter the OAuth resource.

</td>
</tr>
<tr>
<td valign="top">

*OAuth Response Type*

</td>
<td valign="top">

Select the OAuth response type. The values are *Token* or *None*.

</td>
</tr>
<tr>
<td valign="top">

*OAuth Token Request Content Type*

</td>
<td valign="top">

Select the value for the content-type HTTP header that the application must use when requesting a token. The values are *URL Encoded* or *JSON*.

</td>
</tr>
</table>



### Credentials \(OAuth 2.0 with X.509 Client Certificate\)

If *Authentication Type* = *Client Credentials with X.509 Client Certificate* and *OAuth Grant Type* = *OAuth 2.0*:


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

To upload the certificate or certificate chain that is used to authenticate to the remote system, click <span class="SAP-icons-V5"></span> \(Browse\) and select the file.

> ### Note:  
> The file must be in Privacy-enhanced Mail \(PEM\) format. Supported filename extensions are .pem, .crt, or .txt\).



</td>
</tr>
<tr>
<td valign="top">

*X.509 Client Private Key*

</td>
<td valign="top">

To upload the private key, click <span class="SAP-icons-V5"></span> \(Browse\) and select the file.

> ### Note:  
> The file must be in Privacy-enhanced Mail \(PEM\) format. Supported filename extensions are .pem, .crt, .key, or .txt\).



</td>
</tr>
</table>



### Credentials \(OAuth 2.0\)

If *Authentication Type* = *Client Credentials with X.509 Client Certificate* and *OAuth Grant Type* = *Client Credentials*:


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

If *Authentication Type* = *Client Credentials with X.509 Client Certificate* and *OAuth Grant Type* = *User Name and Password*:


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



### Credentials \(User Name and Password\)

If *Authentication Type* = *User Name And Password*:


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

Enter the user name that the application must use for authentication. 

</td>
</tr>
<tr>
<td valign="top">

*Password*  

</td>
<td valign="top">

Enter the password for authentication. 

</td>
</tr>
</table>



### Features

*API Tasks* are enabled without the need to set any additional connection properties. If the external system is an on-premise system, make sure you have maintained the properties in the *Cloud Connector* section.

