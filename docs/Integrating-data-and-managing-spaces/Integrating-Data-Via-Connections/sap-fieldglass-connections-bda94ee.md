<!-- loiobda94ee6c9d5403f8556af174399d221 -->

# SAP Fieldglass Connections

Use an *SAP Fieldglass* connection to retrieve data from SAP Fieldglass.

> ### Note:  
> The connection type is not supported in spaces with storage type *SAP HANA Data Lake Files* \(file spaces\).



<a name="loiobda94ee6c9d5403f8556af174399d221__section_yjk_zk5_rrb"/>

## Prerequisites

See: [Prepare Connectivity to SAP Fieldglass](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/03ca23660b5d4b69960f264f5c31990e.html "To be able to successfully validate and use a connection to SAP Fieldglass for remote tables or data flows, certain preparations have to be made.") :arrow_upper_right:



<a name="loiobda94ee6c9d5403f8556af174399d221__Oracle_usage"/>

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

For remote tables, real-time replication is supported. For information about any constraints, see [Replicate Data Changes in Real-Time](../Data-Integration-Monitor/replicate-data-changes-in-real-time-441d327.md).

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

Select the OAuth response type. The values are *token* or *none*.

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

Enter a valid SAP Fieldglass username. 

</td>
</tr>
<tr>
<td valign="top">

*Client Secret*

</td>
<td valign="top">

Enter the client secret.

> ### Note:  
> The client secret can be either the user's application password, or, to avoid issues with password rotation, a <license key\>, as generated within the SAP Fieldglass system.



</td>
</tr>
</table>

For more information, see the *SAP Fieldglass Integration* documentation:

-   [Obtaining OAuth 2.0 Client Credentials from SAP Fieldglass](https://help.sap.com/docs/SAP_FIELDGLASS_INTEGRATION/a0ce6f1caba4472793e6f7a345e5ba37/2eb112386ca348cb8a7da962d25ddaef.html)
-   [Client Credentials Authentication](https://help.sap.com/docs/SAP_FIELDGLASS_INTEGRATION/d8db40690cb14f08a705f3bc5c9ecbb3/2eb112386ca348cb8a7da962d25ddaef.html#client-credentials-authentication)

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

*Remote Tables*

</td>
<td valign="top">

To enable *Remote Tables*, select a Data Provisioning Agent. 

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

