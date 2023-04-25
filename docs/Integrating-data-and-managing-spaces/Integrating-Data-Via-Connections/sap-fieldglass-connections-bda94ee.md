<!-- loiobda94ee6c9d5403f8556af174399d221 -->

# SAP Fieldglass Connections

Use an *SAP Fieldglass* connection to retrieve data from SAP Fieldglass.



<a name="loiobda94ee6c9d5403f8556af174399d221__section_yjk_zk5_rrb"/>

## Prerequisites

See: [Prepare Connectivity to SAP Fieldglass](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/03ca23660b5d4b69960f264f5c31990e.html "To be able to successfully validate and use a connection to SAP Fieldglass for remote tables or data flows, certain preparations have to be made.") :arrow_upper_right:



<a name="loiobda94ee6c9d5403f8556af174399d221__Oracle_usage"/>

## Using the Connection

The connection type supports the remote table as well as the data flow feature.

Supported data access methods for remote tables:

-   Remote
-   Replication \(snapshot\)
-   Replication \(real-time\)

For more information, see [Replicating Data and Monitoring Remote Tables](../Data-Integration-Monitor/replicating-data-and-monitoring-remote-tables-4dd95d7.md). 



<a name="loiobda94ee6c9d5403f8556af174399d221__section_nrb_hcc_x4b"/>

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

Enter the URL with the following syntax: <code><i class="varname">&lt;protocol&gt;</i>://<i class="varname">&lt;host&gt;</i><i class="varname">&lt;service path&gt;</i></code> 

Protocol: HTTP or HTTPS. The default value is HTTPS.

Host: Host for accessing the cloud OData service

Service path: Relative path \(without host and port\) to the Cloud Data Integration service endpoint \(where the CDI provider service is running at the cloud provider side\). The value must start with a forward slash \( / \).



</td>
</tr>
<tr>
<td valign="top">

*Root Path*



</td>
<td valign="top">

\[optional\] Enter the root path name to restrict browsing to a certain CDI namespace or provider.



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

 Set to *true* if your source is an on-premise source and you want to use the connection for data flows. The default is *false*. 



</td>
</tr>
<tr>
<td valign="top">

 \[if *Use Cloud Connector* = *true*\] *Location* 



</td>
<td valign="top">

 Select a location. 



</td>
</tr>
<tr>
<td valign="top">

 \[if *Use Cloud Connector* = *true*\] *Virtual Destination* 



</td>
<td valign="top">

 Select *Derive Virtual Host and Port from Connection Details* or *Enter Virtual Host and Port in Separate Fields*. 

If host and port entered in the connection details match the virtual host and port from the Cloud Connector configuration, you can select *Derive Virtual Host and Port from Connection Details* and don't need to enter the values manually.



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

Select the OAuth response tyoe. The values are *token* or *none*.



</td>
</tr>
<tr>
<td valign="top">

*OAuth Token Request Content Type*



</td>
<td valign="top">

Select the value for the content-type HTTP header that the application must use when requesting a token. The values are *URLEncoded* or *JSON*.



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

To enable *Remote Tables*, select a Data Provisioning Agent.

*Data Flows* are enabled without the need to set any additional connection properties.

