<!-- loio5aafe32418b14f7e99528b49f48bd3ac -->

# Managing Connections via the REST API

You can manage connections via the *Connections* REST API. Creating and editing connections via the API is supported for SAP SuccessFactors connections only.

This topic contains the following sections:

-   [Prerequisites](managing-connections-via-the-rest-api-5aafe32.md#loio5aafe32418b14f7e99528b49f48bd3ac__section_REST_API_prerequisites)
-   [Introduction to the Connections REST APIs](managing-connections-via-the-rest-api-5aafe32.md#loio5aafe32418b14f7e99528b49f48bd3ac__section_REST_API_introduction)
-   [Obtain a CSRF Token](managing-connections-via-the-rest-api-5aafe32.md#loio5aafe32418b14f7e99528b49f48bd3ac__section_REST_API_CSRF_Token)
-   [List Connections in a Space](managing-connections-via-the-rest-api-5aafe32.md#loio5aafe32418b14f7e99528b49f48bd3ac__section_REST_API_list_connections)
-   [Read Connection Details](managing-connections-via-the-rest-api-5aafe32.md#loio5aafe32418b14f7e99528b49f48bd3ac__section_REST_API_read_connections)
-   [Create a Connection to SAP SuccessFactors](managing-connections-via-the-rest-api-5aafe32.md#loio5aafe32418b14f7e99528b49f48bd3ac__section_REST_API_create_connections)
-   [Validate Connections](managing-connections-via-the-rest-api-5aafe32.md#loio5aafe32418b14f7e99528b49f48bd3ac__section_REST_API_validate_connections)
-   [Edit a Connection to SAP SuccessFactors](managing-connections-via-the-rest-api-5aafe32.md#loio5aafe32418b14f7e99528b49f48bd3ac__section_REST_API_edit_connections)
-   [Delete Connections](managing-connections-via-the-rest-api-5aafe32.md#loio5aafe32418b14f7e99528b49f48bd3ac__section_REST_API_delete_connections)
-   [API Rate Limiting](managing-connections-via-the-rest-api-5aafe32.md#loio5aafe32418b14f7e99528b49f48bd3ac__section_rate_limiting)



<a name="loio5aafe32418b14f7e99528b49f48bd3ac__section_REST_API_prerequisites"/>

## Prerequisites

To create, edit, validate, and delete connections, you must have a scoped role that grants you access to a space with the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Data Warehouse Connection* \(`CRUD----`\) - To create, edit, validate, or delete connections.
-   *Space Files* \(`CRUD----`\) - To create, read, update, and delete objects in your spaces.

The *DW Space Administrator* and *DW Integrator* role templates, for example, grant these privileges. For more information, see [Privileges and Permissions](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/d7350c6823a14733a7a5727bad8371aa.html "A privilege represents a task or an area in SAP Datasphere and can be assigned to a specific role. The actions that can be performed in the area are determined by the permissions assigned to a privilege.") :arrow_upper_right: and [Standard Roles Delivered with SAP Datasphere](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/a50a51d80d5746c9b805a2aacbb7e4ee.html "SAP Datasphere is delivered with several standard roles. A standard role includes a predefined set of privileges and permissions.") :arrow_upper_right:. 

You must, in addition:

-   Obtain the following parameters for an OAuth client created in your SAP Datasphere tenant with *Purpose* set to *Interactive Usage* and the *Redirect URI* set to the URI provided by the client, tool, or app that you want to connect:


    <table>
    <tr>
    <th valign="top">

    Standard OAuth2 Authorization Flow
    
    </th>
    <th valign="top">

    OAuth2SAMLBearer Principal Propagation Flow
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    -   *Client ID*
    -   *Secret*
    -   *Authorization URL* \(not required for clients with a *Technical User* purpose\)
    -   *Token URL*

    Users of a client with a *Technical User* purpose \(which includes its own privileges and permissions\) can then access their resource directly. Users of clients with other purposes must manually authenticate against the IDP in order to generate the authorization code before continuing with the remaining OAuth2.0 steps.
    
    </td>
    <td valign="top">
    
    -   *Client ID*
    -   *Secret*
    -   *OAuth2SAML Token URL*
    -   *OAuth2SAML Audience*

    Users of a client with a *Technical User* purpose can then access their resource directly. Users of clients with other purposes must authenticate with their third-party app, which has a trusted relationship with the IDP, and do not need to re-authenticate \(see [Add a Trusted Identity Provider](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/ea0688aef2f94b35ae34d930b3cb0c10.html "If you use the OAuth 2.0 SAML Bearer Assertion workflow, you must add a trusted identity provider to SAP Datasphere.") :arrow_upper_right:\). See also the blog [Integrating with SAP Datasphere Consumption APIs using SAML Bearer Assertion](https://community.sap.com/t5/technology-blogs-by-sap/integrating-with-sap-datasphere-consumption-apis-using-saml-bearer/ba-p/13647905) \(published March 2024\). 
    
    </td>
    </tr>
    </table>
    
    For information about OAuth clients, see [Create OAuth2.0 Clients to Authenticate Against SAP Datasphere](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/3f92b46fe0314e8ba60720e409c219fc.html "Users with an administrator role can create OAuth2.0 clients and provide the client parameters to users who need to connect clients, tools, or apps to SAP Datasphere.") :arrow_upper_right:. 




<a name="loio5aafe32418b14f7e99528b49f48bd3ac__section_REST_API_introduction"/>

## Introduction to the Connections REST APIs

Using the **Connections API**, you can perform the following actions:

-   List connections in a space

-   Read connection details

-   Validate and delete connections

-   Create and edit connections to SAP SuccessFactors


> ### Note:  
> Connections based on custom connection types are not supported by the SAP Datasphere *Connections* API. You cannot list, read, create, edit, delete, or validate these connections via the API.

The API specification is available at the [SAP Business Accelerator Hub](https://api.sap.com/package/sapdatasphere/overview).



<a name="loio5aafe32418b14f7e99528b49f48bd3ac__section_REST_API_CSRF_Token"/>

## Obtain a CSRF Token

You must have a valid `x-csrf-token` before creating a POST, PUT, or DELETE request to the API endpoints.

You can get a token by sending a GET request to one of the API endpoints \(see below\) including the `x-csrf-token: fetch` header.

The CSRF token is returned in the `x-csrf-token` response header. You must pass the token in the <code>x-csrf-token:<i class="varname">&lt;token&gt;</i></code> header of all POST, PUT, or DELETE requests that you make to the API.

Example syntax of the GET request:

> ### Sample Code:  
> ```
> GET https://<tenant_url>/api/v1/datasphere/spaces/<space_id>/connections
> ```



<a name="loio5aafe32418b14f7e99528b49f48bd3ac__section_REST_API_list_connections"/>

## List Connections in a Space

To list all connections of a space, use the `connections` request and enter:

```
GET https://<tenant_url>/api/v1/datasphere/spaces/<space_id>/connections
```



<a name="loio5aafe32418b14f7e99528b49f48bd3ac__section_REST_API_read_connections"/>

## Read Connection Details

To read the JSON definition of a connection in a space \(without the connection's credentials\), use the `connections` request and enter:

```
GET https://<tenant_url>/api/v1/datasphere/spaces/<space_id>/connections/<connection_technical_name>
```



<a name="loio5aafe32418b14f7e99528b49f48bd3ac__section_REST_API_create_connections"/>

## Create a Connection to SAP SuccessFactors

To create an SAP SuccessFactors connection in a space, use the `connections` request and enter:

```
POST https://<tenant_url>/api/v1/datasphere/spaces/<space_id>/connections?typeId=SAPSF
```

To provide the connection definition, include it as JSON object in the request body.

The following example shows how to create a connection to SAP SuccessFactors for OData V4 and basic authentication:

> ### Sample Code:  
> ```
> {
> "name": "<technical name>", 
> "businessName" : "<business name>", 
> "description":"<description>",
> "authType": "Basic",
> "url": "https://<SAP SuccessFactors API Server>/odatav4/<supported SAP SuccessFactors service group>",
> "version" :"V4",
> "username": "<username>",
> "password":"<password>"
> }
> ```

The following example shows how to create a connection to SAP SuccessFactors for OData V2 and OAuth2 authentication:

> ### Sample Code:  
> ```
> {
>     "name":"<technical name>",
>     "businessName":"<business name>",
>     "description":"<description>", 
>     "authType": "OAuth2",
>     "url": "https://<SAP SuccessFactors API Server>/odata/v2/",
>     "version": "V2",
>     "oauth2GrantType":"saml_bearer",
>     "oauth2TokenEndpoint": "https://<oauth2TokenEndpoint.com>/oauth/token",
>     "oauth2CompanyId": "<SAP SuccessFactors company ID>",
>     "clientId": "<client id>",
>     "samlAssertion":"<SAML assertion>"
> }
> ```

Connection parameters are set as follows:


<table>
<tr>
<th valign="top">

Parameter

</th>
<th valign="top">

Connection Property

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

`name`

</td>
<td valign="top">

*Technical Name*

</td>
<td valign="top">

\[required\] Enter the technical name of the connection. The technical name can only contain alphanumeric characters and underscores \(\_\). It cannot start or end with underscore \(\_\). The name must be unique within the space. 

> ### Note:  
> Once the object is saved, the technical name can no longer be modified.



</td>
</tr>
<tr>
<td valign="top">

`businessName`

</td>
<td valign="top">

*Business Name*

</td>
<td valign="top">

\[optional\] Enter a descriptive name to help users identify the object. This name can be changed at any time.

</td>
</tr>
<tr>
<td valign="top">

`description`

</td>
<td valign="top">

*Description*

</td>
<td valign="top">

\[optional\] Provide more information to help users understand the object.

</td>
</tr>
<tr>
<td valign="top">

`package`

</td>
<td valign="top">

*Package*

</td>
<td valign="top">

\[optional\] Enter an existing package to facilitate transport between tenants \(see [Transporting Content Between Tenants](../Transporting-Content-Between-Tenants/transporting-content-between-tenants-df12666.md)\). 

Default value: `none`

</td>
</tr>
<tr>
<td valign="top">

`url`

</td>
<td valign="top">

*URL* 

</td>
<td valign="top">

\[required\] Enter the OData service provider URL of the SAP SuccessFactors service that you want to access.

The syntax for the URL is:

-   For V2: <code><i class="varname">&lt;SAP SuccessFactors API Server&gt;</i>/odata/v2</code> \(providing a supported SAP SuccessFactors service group <code>/<i class="varname">&lt;service group&gt;</i></code> is optional\)
-   For V4: <code><i class="varname">&lt;SAP SuccessFactors API Server&gt;</i>/odatav4/<i class="varname">&lt;supported SAP SuccessFactors service group&gt;</i></code>



</td>
</tr>
<tr>
<td valign="top">

`version`

</td>
<td valign="top">

*Version* 

</td>
<td valign="top">

\[required\] Enter the OData version used to implement the SAP SuccessFactors OData service \(`V2` or `V4`; see the URL\).

</td>
</tr>
<tr>
<td valign="top">

`authType`

</td>
<td valign="top">

*Authentication Type*

</td>
<td valign="top">

\[required\] Enter the authentication type to use to connect to the OData endpoint.

You can enter:

-   `Basic` for basic authentication with user name and password
-   `OAuth2`

> ### Note:  
> Access to APIs based on HTTP Basic Authentication will be deleted on November 12, 2027. We strongly recommend to adopt the *OAuth 2.0* authentication type for your connections.
> 
> For more information, see:
> 
> -   [Deprecation of Basic Authentication for APIs](https://help.sap.com/doc/62fddbd651204629b46bbccbabf886ba/cloud/en-US/fcc05a902b4140e585d968c2fe4a96bc.html) in *SAP SuccessFactors What's New Viewer*
> -   SAP Note [3774454](https://me.sap.com/notes/3774454)



</td>
</tr>
<tr>
<td valign="top">

`oauth2GrantType`

</td>
<td valign="top">

*OAuth Grant Type*

</td>
<td valign="top">

If you have entered `OAuth2` as `authType`:

\[required\] Enter `SAML Bearer` as the grant type used to retrieve an access token.

</td>
</tr>
<tr>
<td valign="top">

`oauth2TokenEndpoint`

</td>
<td valign="top">

*OAuth Token Endpoint*

</td>
<td valign="top">

If you have entered `OAuth2` as `authType`:

\[required\] Enter the SAP SuccessFactors API endpoint to use to request an access token: <code><i class="varname">&lt;SAP SuccessFactors API Server&gt;</i>/oauth/token</code>.

</td>
</tr>
<tr>
<td valign="top">

`oauth2Scope`

</td>
<td valign="top">

*OAuth Scope*

</td>
<td valign="top">

If you have entered `OAuth2` as `authType`:

\[optional\] Enter the OAuth scope, if applicable.

</td>
</tr>
<tr>
<td valign="top">

`oauth2CompanyId`

</td>
<td valign="top">

*OAuth Company ID*

</td>
<td valign="top">

If you have entered `OAuth2` as `authType`:

\[required\] Enter the SAP SuccessFactors company ID \(identifying the SAP SuccessFactors system on the SAP SuccessFactors API server\) to use to request an access token.

</td>
</tr>
<tr>
<td valign="top">

`clientId`

</td>
<td valign="top">

*Client ID*

</td>
<td valign="top">

If you have entered `OAuth2` as `authType`:

\[required\] Enter the API key received when registering SAP Datasphere as OAuth2 client application in SAP SuccessFactors.

</td>
</tr>
<tr>
<td valign="top">

`samlAssertion`

</td>
<td valign="top">

*SAML Assertion*

</td>
<td valign="top">

If you have entered `OAuth2` as `authType`:

\[required\] Enter a valid SAML assertion that has been generated for authentication.

> ### Note:  
> If the SAML assertion expires, the connection gets invalid until you update the connection with a new valid SAML assertion.



</td>
</tr>
<tr>
<td valign="top">

`username`

</td>
<td valign="top">

*User Name* 

</td>
<td valign="top">

If you have entered `Basic` as `authType`:

\[required\] Enter the user name in *<username@companyID\>* format.

</td>
</tr>
<tr>
<td valign="top">

`password`

</td>
<td valign="top">

*Password* 

</td>
<td valign="top">

If you have entered `Basic` as `authType`:

\[required\] Enter the password.

</td>
</tr>
</table>



<a name="loio5aafe32418b14f7e99528b49f48bd3ac__section_REST_API_validate_connections"/>

## Validate Connections

To validate a connection in a space, use the `connections` request and enter:

```
GET https://<tenant_url>/api/v1/datasphere/spaces/<spaceId>/connections/<connection_technical_name>/validation
```



<a name="loio5aafe32418b14f7e99528b49f48bd3ac__section_REST_API_edit_connections"/>

## Edit a Connection to SAP SuccessFactors

To edit an SAP SuccessFactors connection in a space, providing an updated connection definition in a JSON format, use the `connections` request and enter:

```
PUT https://<tenant_url>/api/v1/datasphere/spaces/<space-id>/connections/<connection_technical_name>
```

To provide the modified connection definition, include it as JSON object in the request body.



<a name="loio5aafe32418b14f7e99528b49f48bd3ac__section_REST_API_delete_connections"/>

## Delete Connections

To delete a connection from a space, use the `connections` request and enter:

```
DELETE https://<tenant_url>/api/v1/datasphere/spaces/<spaceId>/connections/<connection_technical_name>
```



<a name="loio5aafe32418b14f7e99528b49f48bd3ac__section_rate_limiting"/>

## API Rate Limiting

Authenticated requests are associated either with the authenticated username, the OAuth client ID, or the tenant ID. Unauthenticated requests are associated with the originating IP address, and not the user.

Requests are limited to approximately 300 per user per minute \(25 per user per minute for the *Connections* and *Certificates* APIs\). If you exceed the limit, you will receive the `HTTP 429 Too Many Requests` response status code and can review the following request response headers for further information:

-   `X-Ratelimit-Limit` - Rate limit per user per minute.
-   `X-Ratelimit-Remaining` - Remaining number of requests for the current timeframe for the current user.
-   `X-Ratelimit-Reset` - Time in seconds until the rate limit is reset to the defined limit.
-   `Retry-After` - Time in seconds the user agent should wait before making a follow-up request.

