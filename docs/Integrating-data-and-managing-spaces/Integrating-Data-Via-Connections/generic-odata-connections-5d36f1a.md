<!-- loio5d36f1aae68a4e59989c424a66d948c9 -->

# Generic OData Connections

Use a *Generic OData* connection to access data from an OData service. 

> ### Note:  
> The connection type is not supported in spaces with storage type *SAP HANA Data Lake Files* \(file spaces\).

This topic contains the following sections:

-   [Supported Features](generic-odata-connections-5d36f1a.md#loio5d36f1aae68a4e59989c424a66d948c9__Odata_usage)
-   [Prerequisites](generic-odata-connections-5d36f1a.md#loio5d36f1aae68a4e59989c424a66d948c9__Odata_prerequisites)
-   [Configuring Connection Properties](generic-odata-connections-5d36f1a.md#loio5d36f1aae68a4e59989c424a66d948c9__Odata_connection_properties)



<a name="loio5d36f1aae68a4e59989c424a66d948c9__Odata_usage"/>

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

You can use remote tables imported from the connection either to access data directly live in the connected source \(federation\) or to copy the data into SAP Datasphere \(replication\).

For more information, see [Monitoring Remote Tables](../Data-Integration-Monitor/monitoring-remote-tables-4dd95d7.md). 

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



<a name="loio5d36f1aae68a4e59989c424a66d948c9__Odata_prerequisites"/>

## Prerequisites



### Remote Tables

Before you can use the connection for remote tables, the following is required:

-   The OData service URL needs to be publicly available.

-   A DW administrator has uploaded the server certificate to SAP Datasphere.

    For more information, see [Manage Certificates for Connections](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/46f5467adc5242deb1f6b68083e72994.html "For connections secured by leveraging HTTPS as the underlying transport protocol (using SSL/TLS transport encryption), the server certificate must be trusted. To import a certificate into the SAP Datasphere trust chain, obtain the certificate from the target endpoint and upload it to SAP Datasphere.") :arrow_upper_right:.




### Data Flows

Before you can use the connection for data flows, the following is required:

-   If your OData service is an on-premise service in your local network, Cloud Connector is required for the connection between your service and SAP Datasphere.

    For more information, see [Configure Cloud Connector](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/f289920243a34127b0c8b13012a1a4b5.html "Configure Cloud Connector before connecting to on-premise sources and using them in various use cases. In the Cloud Connector administration, connect the SAP Datasphere subaccount to your Cloud Connector, add a mapping to each relevant source system in your network, and specify accessible resources for each source system.") :arrow_upper_right:.

    > ### Note:  
    > -   In Cloud Connector configuration, enter the port specified for your OData service. If the port is not explicitly included in the OData service URL, the system assumes that the service is using the default port 80 for HTTP or 443 for HTTPS.
    > -   Publicly available OData services are supported without Cloud Connector.




<a name="loio5d36f1aae68a4e59989c424a66d948c9__Odata_connection_properties"/>

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

*URL*  

</td>
<td valign="top">

Enter the OData service provider URL. 

</td>
</tr>
<tr>
<td valign="top">

*Version*  

</td>
<td valign="top">

Select the OData version used to implement the OData service \(*V2* or *V4*\). 

</td>
</tr>
<tr>
<td valign="top">

*Timeout \(sec\)*

</td>
<td valign="top">

\[optional\] Enter the HTTP connection timeout, in seconds. This property only affects remote tables.

The default is 900 \(15 minutes\).

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

\[optional\] Set to *true* if your source is an on-premise source and you want to use the connection for data flows. The default is *false*. 

</td>
</tr>
<tr>
<td valign="top">

\[if *Use Cloud Connector* = *true*\] *Location* 

</td>
<td valign="top">

\[optional\] Select a location ID. 

> ### Note:  
> To select another location ID than the default location, *Connection* privilege with *Read* permission is required. The privilege is neither included in the *DW Integrator* nor in the *DW Space Administrator* role. If you need to select a location ID, ask your tenant administrator to either assign your user to a global role that is based on the *DW Administrator* role or to assign your user to a custom global role \(with license type SAP Datasphere\) that includes the required *Connection* privilege with *Read* permission. 



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

Select the authentication type to use to connect to the OData endpoint. 

You can select:

-   *No Authentication*
-   *User Name And Password* for basic authentication
-   *OAuth 2.0* \(default value\)



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

Displays *Client Credentials* as grant type used to retrieve an access token. 

</td>
</tr>
<tr>
<td valign="top">

*OAuth Token Endpoint*

</td>
<td valign="top">

Enter the API endpoint to use to request an access token, for example <code><i class="varname">&lt;API server&gt;</i>/oauth/token</code>.

</td>
</tr>
<tr>
<td valign="top">

*OAuth Scope*

</td>
<td valign="top">

\[optional\] Enter the OAuth scope, if applicable.

</td>
</tr>
<tr>
<td valign="top">

*OAuth Token Request Content Type*

</td>
<td valign="top">

\[optional\] Enter the content type of the OAuth2 token request. 

You can select:

-   *URL Encoded* \(application/x-www-form-urlencoded\) \(default value\)

-   *JSON* \(application/json\)

-   *Form Data* \(multipart/form-data\)

    > ### Note:  
    > *Form Data* is not supported for data flows. Selecting the value disables data flows.




</td>
</tr>
</table>



### Credentials \(OAuth 2.0\)

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

*Client ID*

</td>
<td valign="top">

Enter the client ID to authenticate SAP Datasphere to the authorization server. 

</td>
</tr>
<tr>
<td valign="top">

*Client Secret*

</td>
<td valign="top">

Enter the client secret to authenticate SAP Datasphere to the authorziation server.

</td>
</tr>
</table>



### Credentials \(User Name And Password\)

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

Enter the user name. 

</td>
</tr>
<tr>
<td valign="top">

*Password*  

</td>
<td valign="top">

Enter the password. 

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
<tr>
<td valign="top">

*Data Flows*

</td>
<td valign="top">

*Data Flows* are enabled without the need to set any additional connection properties.If your source is an on-premise source, make sure you have maintained the properties in the *Cloud Connector* section.

> ### Note:  
> When you select *Form Data* as *OAuth Token Request Content Type*, data flows are disabled.



</td>
</tr>
</table>



## Advanced Connection Properties


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

*Enter Custom HTTP Headers*

</td>
<td valign="top">

Different OData services support different sets of custom headers to pass parameters to the service when using the connection. You can specify one or more custom HTTP headers to add them to the OData request.

Click *Add* to add name and value for a custom HTTP header field.

> ### Note:  
> -   Security-relevant headers such as "authorization" are not allowed.
> 
> -   Setting a Content-Type custom header is not considered in the OData request, instead the content type you selected in the *OAuth Token Request Content Type* property is used.



</td>
</tr>
<tr>
<td valign="top">

*Support Format Query*

</td>
<td valign="top">

If the option is enabled \(default\), you can use the <code>$format=<i class="varname">&lt;format&gt;</i></code> query option to specify the format in which data should be returned, for example you can use <code>$format=<i class="varname">&lt;json&gt;</i></code> to request JSON format. If you disable the property, the format query option is ignored, and the connection always returns the default response format of the OData service.

> ### Note:  
> This option applies to remote tables only.



</td>
</tr>
</table>

