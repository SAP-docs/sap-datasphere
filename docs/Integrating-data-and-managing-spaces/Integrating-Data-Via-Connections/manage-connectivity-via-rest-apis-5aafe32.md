<!-- loio5aafe32418b14f7e99528b49f48bd3ac -->

# Manage Connectivity via REST APIs

You can manage TLS server certificates and connections via the *Certificates* and *Connections* REST APIs. Creating and editing connections via the API is supported for SAP SuccessFactors connections only.

This topic contains the following sections:

-   [Prerequisites](manage-connectivity-via-rest-apis-5aafe32.md#loio5aafe32418b14f7e99528b49f48bd3ac__section_REST_API_prerequisites)
-   [Introduction to the Connectivity REST APIs](manage-connectivity-via-rest-apis-5aafe32.md#loio5aafe32418b14f7e99528b49f48bd3ac__section_REST_API_introduction)
-   [Log in with an OAuth Client](manage-connectivity-via-rest-apis-5aafe32.md#loio5aafe32418b14f7e99528b49f48bd3ac__section_REST_API_OAuth_login)
-   [Obtain a CSRF Token](manage-connectivity-via-rest-apis-5aafe32.md#loio5aafe32418b14f7e99528b49f48bd3ac__section_REST_API_CSRF_Token)
-   [List TLS Server Certificates](manage-connectivity-via-rest-apis-5aafe32.md#loio5aafe32418b14f7e99528b49f48bd3ac__section_REST_API_list_certificates)
-   [Upload TLS Server Certificates](manage-connectivity-via-rest-apis-5aafe32.md#loio5aafe32418b14f7e99528b49f48bd3ac__section_REST_API_upload_certificates)
-   [Delete TLS Server Certificates](manage-connectivity-via-rest-apis-5aafe32.md#loio5aafe32418b14f7e99528b49f48bd3ac__section_REST_API_delete_certificates)
-   [List Connections in a Space](manage-connectivity-via-rest-apis-5aafe32.md#loio5aafe32418b14f7e99528b49f48bd3ac__section_REST_API_list_connections)
-   [Read Connection Details](manage-connectivity-via-rest-apis-5aafe32.md#loio5aafe32418b14f7e99528b49f48bd3ac__section_REST_API_read_connections)
-   [Create Connection to SAP SuccessFactors](manage-connectivity-via-rest-apis-5aafe32.md#loio5aafe32418b14f7e99528b49f48bd3ac__section_REST_API_create_connections)
-   [Validate Connections](manage-connectivity-via-rest-apis-5aafe32.md#loio5aafe32418b14f7e99528b49f48bd3ac__section_REST_API_validate_connections)
-   [Edit Connection to SAP SuccessFactors](manage-connectivity-via-rest-apis-5aafe32.md#loio5aafe32418b14f7e99528b49f48bd3ac__section_REST_API_edit_connections)
-   [Delete Connections](manage-connectivity-via-rest-apis-5aafe32.md#loio5aafe32418b14f7e99528b49f48bd3ac__section_REST_API_delete_connections)



<a name="loio5aafe32418b14f7e99528b49f48bd3ac__section_REST_API_prerequisites"/>

## Prerequisites

To manage certificates, you must have a global role that grants you the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *System Information* \(`-RU-----`\) - To access the *Configuration* area in the *System* tool.

The *DW Administrator* global role, for example, grants these privileges. For more information, see [Privileges and Permissions](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/d7350c6823a14733a7a5727bad8371aa.html "A privilege represents a task or an area in SAP Datasphere and can be assigned to a specific role. The actions that can be performed in the area are determined by the permissions assigned to a privilege.") :arrow_upper_right: and [Standard Roles Delivered with SAP Datasphere](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/a50a51d80d5746c9b805a2aacbb7e4ee.html "SAP Datasphere is delivered with several standard roles. A standard role includes a predefined set of privileges and permissions.") :arrow_upper_right:. 

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

## Introduction to the Connectivity REST APIs

SAP Datasphere exposes REST APIs that allow you to programmatically manage TLS server certificates and connections using dedicated endpoints.

Using the **Certificates API**, you can perform the following actions:

-   List TLS server certificates

-   Upload and delete TLS server certificates


Using the **Connections API**, you can perform the following actions:

-   List connections in a space

-   Read connection details

-   Validate and delete connections

-   Create and edit connections to SAP SuccessFactors


The API specifications are available at the [SAP Business Accelerator Hub](https://api.sap.com/package/sapdatasphere/overview).



<a name="loio5aafe32418b14f7e99528b49f48bd3ac__section_REST_API_OAuth_login"/>

## Log in with an OAuth Client

With the OAuth Client created in your SAP Datasphere tenant, your client, tool, or application will be able to authenticate against the system’s OAuth service and obtain authorization to authenticate against the API.

To obtain an OAuth access token, send a GET request to one of the API endpoints \(see below\) including <code>Authorization: Auth Type <i class="varname">&lt;OAuth 2.0&gt;</i></code> and passing the *<client ID\>*, *<secret\>*, *<authorization URL\>*, and *<token URL\>* values.

You must pass the access token in the `Authorization` header of all requests that you make to the API.

Example syntax of the GET request:

> ### Sample Code:  
> ```
> https://<tenant_url>/api/v1/datasphere/configuration/security/certificates
> ```



<a name="loio5aafe32418b14f7e99528b49f48bd3ac__section_REST_API_CSRF_Token"/>

## Obtain a CSRF Token

You must have a valid `x-csrf-token` before creating a POST, PUT, or DELETE request to the API endpoints.

You can get a token by sending a GET request to one of the API endpoints \(see below\) including the `x-csrf-token: fetch` header.

The CSRF token is returned in the `x-csrf-token` response header. You must pass the token in the <code>x-csrf-token:<i class="varname">&lt;token&gt;</i></code> header of all POST, PUT, or DELETE requests that you make to the API.

Example syntax of the GET request:

> ### Sample Code:  
> ```
> https://<tenant_url>/api/v1/datasphere/configuration/security/certificates
> ```



<a name="loio5aafe32418b14f7e99528b49f48bd3ac__section_REST_API_list_certificates"/>

## List TLS Server Certificates

To retrieve a list of TLS server certificates available in the tenant, use the GET request with the`/api/v1/datasphere/configuration/security/certificates` endpoint and enter:

```
https://<tenant_url>/api/v1/datasphere/configuration/security/certificates
```



<a name="loio5aafe32418b14f7e99528b49f48bd3ac__section_REST_API_upload_certificates"/>

## Upload TLS Server Certificates

To upload a TLS server certificate, use the POST request with the`/api/v1/datasphere/configuration/security/certificates` endpoint and enter:

```
https://<tenant_url>/api/v1/datasphere/configuration/security/certificates
```

> ### Note:  
> The file that you upload must have a supported file extension: .pem \(privacy-enhanced mail\), .crt, or .cer.



<a name="loio5aafe32418b14f7e99528b49f48bd3ac__section_REST_API_delete_certificates"/>

## Delete TLS Server Certificates

To delete a TLS server certificate from the tenant, use the DELETE request with the<code>/api/v1/datasphere/configuration/security/certificates/<i class="varname">&lt;fingerprint&gt;</i></code> endpoint and enter:

```
https://<tenant_url>/api/v1/datasphere/configuration/security/certificates/<fingerprint>
```

> ### Note:  
> You can retrieve the fingerprint from the list of certificates.



<a name="loio5aafe32418b14f7e99528b49f48bd3ac__section_REST_API_list_connections"/>

## List Connections in a Space

To list all connections of a space, use the GET request with the<code>/api/v1/datasphere/spaces/<i class="varname">&lt;space_id&gt;</i>/connections</code> endpoint and enter:

```
https://<tenant_url>/api/v1/datasphere/spaces/<space_id>/connections
```



<a name="loio5aafe32418b14f7e99528b49f48bd3ac__section_REST_API_read_connections"/>

## Read Connection Details

To read the JSON definition of a connection \(without its credentials\) in a space , use the GET request with the<code>/api/v1/datasphere/spaces/<i class="varname">&lt;space_id&gt;</i>/connections/<i class="varname">&lt;connection_technical_name&gt;</i></code> endpoint and enter:

```
https://<tenant_url>/api/v1/datasphere/spaces/<space_id>/connections/<connection_technical_name>
```



<a name="loio5aafe32418b14f7e99528b49f48bd3ac__section_REST_API_create_connections"/>

## Create Connection to SAP SuccessFactors

To create an SAP SuccessFactors connection in a space by providing the connection definition in stringified json format, use the POST request with the<code>/api/v1/datasphere/spaces/<i class="varname">&lt;space_id&gt;</i>/connections</code> endpoint and enter:

```
https://<tenant_url>/api/v1/datasphere/spaces/<space_id>/connections
```

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
>     "authType": "<OAuth2>",
>     "url": "https://<SAP SuccessFactors API Server>/odata/v2/",
>     "version": "V2",
>     "oauth2GrantType":"saml_bearer",
>     "oauth2TokenEndpoint": "https://<oauth2TokenEndpoint.com>/oauth/token",
>     "oauth2CompanyId": "<SAP SuccessFactors company ID>",
>     "clientId": "<client id>",
>     "clientSecret":"<SAML assertion>"
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
> HTTP basic authentication in SAP SuccessFactors will soon be retired. For more information, see [Deprecation of HTTP Basic Authentication](https://help.sap.com/doc/62fddbd651204629b46bbccbabf886ba/cloud/en-US/fcc05a902b4140e585d968c2fe4a96bc.html) in *SAP SuccessFactors What's New Viewer*.



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

\[required\] Enter the OData version used to implement the SAP SuccessFactors OData service \(`V2` or `V4`\).

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

\[required\] Enter the API endpoint to use to request an access token: <code><i class="varname">&lt;SAP SuccessFactors API Server&gt;</i>/oauth/token</code>.

</td>
</tr>
<tr>
<td valign="top">

 

</td>
<td valign="top">

*OAuth Scope*

</td>
<td valign="top">

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

\[required\] Enter the API key received when registering SAP Datasphere as OAuth2 client application in SAP SuccessFactors.

</td>
</tr>
<tr>
<td valign="top">

`clientSecret`

</td>
<td valign="top">

*SAML Assertion*

</td>
<td valign="top">

\[required\] Enter a valid SAML assertion that has been generated for authentication.

> ### Note:  
> If the SAML assertion expires, the connection gets invalid until you update the connection with a new valid SAML assertion.



</td>
</tr>
</table>



<a name="loio5aafe32418b14f7e99528b49f48bd3ac__section_REST_API_validate_connections"/>

## Validate Connections

To validate a connection in a space, use the GET request with the<code>/api/v1/datasphere/spaces/<i class="varname">&lt;space_id&gt;</i>/connections/<i class="varname">&lt;connection_technical_name&gt;</i>/validation</code> endpoint and enter:

```
https://<tenant_url>/api/v1/datasphere/spaces/<spaceId>/connections/<connection_technical_name>/validation
```



<a name="loio5aafe32418b14f7e99528b49f48bd3ac__section_REST_API_edit_connections"/>

## Edit Connection to SAP SuccessFactors

To edit an SAP SuccessFactors connection in a space by providing a new definition, use the PUT request with the<code>/api/v1/datasphere/spaces/<i class="varname">&lt;space_id&gt;</i>/connections/<i class="varname">&lt;connection_technical_name&gt;</i></code> endpoint and enter:

```
https://<tenant_url>/api/v1/datasphere/spaces/<space-id>/connections/<connection_technical_name>
```



<a name="loio5aafe32418b14f7e99528b49f48bd3ac__section_REST_API_delete_connections"/>

## Delete Connections

To delete a connection from a space, use the DELETE request with the<code>/api/v1/datasphere/spaces/<i class="varname">&lt;spaceId&gt;</i>/connections/<i class="varname">&lt;connection_technical_name&gt;</i></code> endpoint and enter:

```
https://<tenant_url>/api/v1/datasphere/spaces/<spaceId>/connections/<connection_technical_name>
```

