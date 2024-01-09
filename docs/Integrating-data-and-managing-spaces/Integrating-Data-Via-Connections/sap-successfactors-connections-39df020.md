<!-- loio39df02030d4b411487bacecf9afea4e8 -->

# SAP SuccessFactors Connections

Use an *SAP SuccessFactors* connection to access employee-related data in SAP SuccessFactors.



This topic contains the following sections:

-   [Supported Features](sap-successfactors-connections-39df020.md#loio39df02030d4b411487bacecf9afea4e8__SF_usage)
-   [Configuring Connection Properties](sap-successfactors-connections-39df020.md#loio39df02030d4b411487bacecf9afea4e8__connection_properties)

For information about the required prerequisites, see [Prepare Connectivity to SAP SuccessFactors](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/c9b19156c417409b8d563cc4b56c5dc0.html "To be able to successfully validate and use a connection to SAP SuccessFactors for remote tables or data flows certain preparations have to be made.") :arrow_upper_right:.



<a name="loio39df02030d4b411487bacecf9afea4e8__SF_usage"/>

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

> ### Note:  
> -   We strongly recommend to use remote tables for replication only and not to use it for federated access because of the following reason:
> 
>     When using remote tables to replicate data from SAP SuccessFactors, the *SAP SuccessFactors* connection type uses snapshot-based pagination for SAP SuccessFactors entities that support this method and this way ensures data consistency \(see [Snapshot-Based Pagination](https://help.sap.com/docs/SAP_SUCCESSFACTORS_PLATFORM/d599f15995d348a1b45ba5603e2aba9b/7af42e7079c3481688de975b38867c41.html) in the *SAP SuccessFactors Platform* documentation\). For federated access, snapshot-based pagination is not supported because of its service limits \(see [Service Limits for Snapshot-Based Pagination](https://help.sap.com/docs/SAP_SUCCESSFACTORS_PLATFORM/d599f15995d348a1b45ba5603e2aba9b/7af42e7079c3481688de975b38867c41.html#service-limits-for-snapshot-based-pagination) in the *SAP SuccessFactors Platform* documentation\). Instead, federated access uses client-side pagination, which potentially can lead to data loss or data duplication \(see[Client-Side Pagination](https://help.sap.com/docs/SAP_SUCCESSFACTORS_PLATFORM/d599f15995d348a1b45ba5603e2aba9b/1ea216105cfb4333b8189e3e9a4fdbcc.html) in the *SAP SuccessFactors Platform* documentation\).
> 
>     Please note that since the *Generic OData* connection type doesn’t use snapshot-based pagination at all, we do not recommend to use it to federate or replicate SAP SuccessFactors data with remote tables.
> 
> -   When replicating employee-related data, independently of their validity not only current data is replicated but all data including historical data.



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



<a name="loio39df02030d4b411487bacecf9afea4e8__connection_properties"/>

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

Enter the OData service provider URL of the SAP SuccessFactors service that you want to access. 

The syntax for the URL is:

-   For V2: <code><i class="varname">&lt;SAP SuccessFactors API Server&gt;</i>/odata/v2</code> \(providing a supported SAP SuccessFactors service group <code>/<i class="varname">&lt;service group&gt;</i></code> is optional\)
-   For V4: <code><i class="varname">&lt;SAP SuccessFactors API Server&gt;</i>/odatav4/<i class="varname">&lt;supported SAP SuccessFactors service group&gt;</i></code>



</td>
</tr>
<tr>
<td valign="top">

*Version*  

</td>
<td valign="top">

\[read-only\] Displays the OData version used to implement the SAP SuccessFactors OData service. 

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

-   *User Name And Password* for basic authentication
-   *OAuth 2.0* 

The default is *OAuth 2.0*.

> ### Note:  
> HTTP basic authentication in SAP SuccessFactors will soon be retired. For more information, see [Deprecation of HTTP Basic Authentication](https://help.sap.com/doc/62fddbd651204629b46bbccbabf886ba/cloud/en-US/fcc05a902b4140e585d968c2fe4a96bc.html) in *SAP SuccessFactors What's New Viewer*.



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

\[read-only\] Displays *SAML Bearer* as the grant type used to retrieve an access token. 

</td>
</tr>
<tr>
<td valign="top">

*OAuth Token Endpoint*

</td>
<td valign="top">

Enter the API endpoint to use to request an access token: <code><i class="varname">&lt;SAP SuccessFactors API Server&gt;</i>/oauth/token</code>.

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

*OAuth Company ID*

</td>
<td valign="top">

Enter the SAP SuccessFactors company ID \(identifying the SAP SuccessFactors system on the SAP SuccessFactors API server\) to use to request an access token.

</td>
</tr>
</table>

> ### Note:  
> When editing a connection that has been created before entering the SAML assertion in the credentials was required, you can set the *Provide SAML Assertion* property in the *OAuth 2.0* section to *true* to switch to the new method and then enter a valid SAML assertion in the *Credentials* section.
> 
> Note that once you change the *Provide SAML Assertion* property to *true*, enter the SAML assertion and save the connection, you cannot turn back to use the /oauth/idp API to generate the SAML assertion.



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

Enter the API key received when registering SAP Datasphere as OAuth2 client application in SAP SuccessFactors. 

</td>
</tr>
<tr>
<td valign="top">

*SAML Assertion*

</td>
<td valign="top">

Enter a valid SAML assertion that has been generated for authentication.

> ### Note:  
> If the SAML assertion expires, the connection gets invalid until you update the connection with a new valid SAML assertion.



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

Enter the user name in *<username@companyID\>* format. 

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

*Data Flows* are enabled without the need to set any additional connection properties. 

</td>
</tr>
</table>

