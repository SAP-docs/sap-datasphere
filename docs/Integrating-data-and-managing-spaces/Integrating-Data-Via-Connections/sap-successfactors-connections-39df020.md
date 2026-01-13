<!-- loio39df02030d4b411487bacecf9afea4e8 -->

# SAP SuccessFactors Connections

Use an *SAP SuccessFactors* connection to access employee-related data in SAP SuccessFactors.

> ### Note:  
> The connection type is not supported in spaces with storage type *SAP HANA Data Lake Files* \(file spaces\).



This topic contains the following sections:

-   [Supported Features](sap-successfactors-connections-39df020.md#loio39df02030d4b411487bacecf9afea4e8__SF_usage)
-   [Prerequisites](sap-successfactors-connections-39df020.md#loio39df02030d4b411487bacecf9afea4e8__SF_prerequisites)
-   [Configuring Connection Properties](sap-successfactors-connections-39df020.md#loio39df02030d4b411487bacecf9afea4e8__SF_connection_properties)



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
> 
> -   Picklists used in SAP SuccessFactors are not available in remote tables because they are exposed as navigation properties and not as exposed properties of the entity. For more information on picklists, see SAP Note [2088679](https://me.sap.com/notes/2088679).



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



<a name="loio39df02030d4b411487bacecf9afea4e8__SF_prerequisites"/>

## Prerequisites

Before you can use the connection, the following is required:

-   A DW administrator has uploaded the server certificate to SAP Datasphere.

    Example for Certificate Download Site: `https://performancemanager4.successfactors.com`

    For more information, see [Manage Certificates for Connections](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/46f5467adc5242deb1f6b68083e72994.html "For connections secured by leveraging HTTPS as the underlying transport protocol (using SSL/TLS transport encryption), the server certificate must be trusted. To import a certificate into the SAP Datasphere trust chain, obtain the certificate from the target endpoint and upload it to SAP Datasphere.") :arrow_upper_right:.

-   When using OAuth 2.0 for authentication:

    -   SAP Datasphere must be registered in SAP SuccessFactors.

        For more information, see [Registering Your OAuth2 Client Application](https://help.sap.com/viewer/d599f15995d348a1b45ba5603e2aba9b/latest/en-US/6b3c741483de47b290d075d798163bc1.html) in the *SAP SuccessFactors platform* documentation.

    -   A SAML assertion needs to be generated to be able to provide it when creating or editing the connection.

        For an overview of the available options to generate a SAML assertion, see [Generating a SAML Assertion](https://help.sap.com/docs/SAP_SUCCESSFACTORS_PLATFORM/d599f15995d348a1b45ba5603e2aba9b/4e27e8f6ae2748ab9f23228dd6a31b06.html) in the *SAP SuccessFactors platform* documentation.


-   In SAP SuccessFactors IP restriction management, you have added the externally facing SAP HANA IP addresses and the outbound IP address for SAP Datasphere to the list of IP restrictions. IP restrictions are a specified list of IP addresses from which users can access your SAP SuccessFactors system.

    For more information, see:

    -   [IP Restrictions](https://help.sap.com/docs/SAP_SUCCESSFACTORS_PLATFORM/bf014ed11dae45ecae6f8c6e42fa68bb/a356e2c66c7443ceb15f8592318b5dcf.html) in the *SAP SuccessFactors platform* documentation

    -   [Obtain SAP Datasphere IP addresses For Allowlisting in Remote Systems](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/0934f7ed9a534e638299f53ab60866ae.html "Remote systems may restrict access to their instances. The remote system often decides whether an external client, such as SAP Datasphere, can access it based on allowlisted IPs. You must add SAP Datasphere's IP address to the remote system's allowlist before SAP Datasphere attempts access, via connections, for example.") :arrow_upper_right:





<a name="loio39df02030d4b411487bacecf9afea4e8__SF_connection_properties"/>

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

