<!-- loio1ca8c4a9467f43df9ae6d4ed3734f05a -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Create Users and Assign Them to Roles via the SCIM 2.0 API

You can create, read, update, and delete users and add them to roles via the SCIM 2.0 API.

This topic contains the following sections:

-   [Introduction](create-users-and-assign-them-to-roles-via-the-scim-2-0-api-1ca8c4a.md#loio1ca8c4a9467f43df9ae6d4ed3734f05a__section_jzc_m3q_rbc)
-   [Log in with a OAuth Client](create-users-and-assign-them-to-roles-via-the-scim-2-0-api-1ca8c4a.md#loio1ca8c4a9467f43df9ae6d4ed3734f05a__section_th4_syw_tbc)
-   [Obtain a CSRF Token](create-users-and-assign-them-to-roles-via-the-scim-2-0-api-1ca8c4a.md#loio1ca8c4a9467f43df9ae6d4ed3734f05a__section_wzz_v2w_rbc)
-   [List Users](create-users-and-assign-them-to-roles-via-the-scim-2-0-api-1ca8c4a.md#loio1ca8c4a9467f43df9ae6d4ed3734f05a__section_js2_yfw_rbc)
-   [Get a Specific User](create-users-and-assign-them-to-roles-via-the-scim-2-0-api-1ca8c4a.md#loio1ca8c4a9467f43df9ae6d4ed3734f05a__section_esx_kxt_vbc)
-   [Create a User](create-users-and-assign-them-to-roles-via-the-scim-2-0-api-1ca8c4a.md#loio1ca8c4a9467f43df9ae6d4ed3734f05a__section_nqs_5lp_tbc)
-   [Modify a User](create-users-and-assign-them-to-roles-via-the-scim-2-0-api-1ca8c4a.md#loio1ca8c4a9467f43df9ae6d4ed3734f05a__section_zq5_rlp_tbc)
-   [Delete a User](create-users-and-assign-them-to-roles-via-the-scim-2-0-api-1ca8c4a.md#loio1ca8c4a9467f43df9ae6d4ed3734f05a__section_jhl_xlp_tbc)
-   [Optional User Properties](create-users-and-assign-them-to-roles-via-the-scim-2-0-api-1ca8c4a.md#loio1ca8c4a9467f43df9ae6d4ed3734f05a__section_vpq_skn_xbc)
-   [Get Information About the SCIM API](create-users-and-assign-them-to-roles-via-the-scim-2-0-api-1ca8c4a.md#loio1ca8c4a9467f43df9ae6d4ed3734f05a__section_n1l_vdy_rbc)



<a name="loio1ca8c4a9467f43df9ae6d4ed3734f05a__section_jzc_m3q_rbc"/>

## Introduction

This API allows you to programmatically manage users using a SCIM 2.0 compliant endpoint.

SAP Datasphere exposes a REST API based on the System for Cross-domain Identity Management \(SCIM 2.0\) specification. This API allows you to keep your SAP Datasphere system synchronized with your preferred identity management solution.

Using this API, you can perform the following actions:

-   Create, read, update, patch, delete users.

-   Add users to existing scoped or global roles.

    > ### Note:  
    > You cannot create new roles using this API.

-   List users.

-   Get information on the identity provider, available schemas, and resource types.


This API uses SCIM 2.0. For more information, see [SCIM Core Schema](https://tools.ietf.org/html/rfc7643).

To access the API specification and try out the functionality in SAP Analytics Cloud, see the [SAP Business Accelerator Hub](https://api.sap.com/api/Story_API/resource/Users).



<a name="loio1ca8c4a9467f43df9ae6d4ed3734f05a__section_th4_syw_tbc"/>

## Log in with a OAuth Client

Beforehand you can log in with a Oauth client, a user with the administrator role must create an OAuth2.0 client in your SAP Datasphere tenant and provide you with the OAuth client ID and secret parameters \(see [Create OAuth2.0 Clients to Authenticate Against SAP Datasphere](../Creating-and-Configuring-Your-Tenant/create-oauth2-0-clients-to-authenticate-against-sap-datasphere-3f92b46.md)\).

To log in to the OAuth client, send a GET request with the following elements:


<table>
<tr>
<th valign="top">

Request Component

</th>
<th valign="top">

Setting

</th>
<th valign="top">

Value

</th>
</tr>
<tr>
<td valign="top">

Parameter

</td>
<td valign="top">

key

</td>
<td valign="top">

`?grant_type=client_credentials`

</td>
</tr>
<tr>
<td valign="top">

Authorization

</td>
<td valign="top">

type

</td>
<td valign="top">

`Basic Auth`

</td>
</tr>
<tr>
<td valign="top">

Authorization

</td>
<td valign="top">

username

</td>
<td valign="top">

*<OAuth Client ID\>*

</td>
</tr>
<tr>
<td valign="top">

Authorization

</td>
<td valign="top">

password

</td>
<td valign="top">

*<OAuth Client Secret\>*

</td>
</tr>
</table>

Syntax of GET request:

```
https://<token_url>/oauth/token?grant_type=client_credentials
```

> ### Note:  
> You can find the token URL in <span class="FPA-icons-V3"></span> \(*System*\) ** \> ** <span class="Belize-icons"></span> \(*Administration*\) ** \> *App Integration* \> *OAuth Clients* \> *Token URL*.

The response body returns the access token, which you'll then use as the bearer token to obtain the csrf token.



<a name="loio1ca8c4a9467f43df9ae6d4ed3734f05a__section_wzz_v2w_rbc"/>

## Obtain a CSRF Token

To obtain a csrf token, send a GET request with the following elements:


<table>
<tr>
<th valign="top">

Request Component

</th>
<th valign="top">

Setting

</th>
<th valign="top">

Value

</th>
</tr>
<tr>
<td valign="top">

Authorization

</td>
<td valign="top">

type

</td>
<td valign="top">

`Bearer Token`

</td>
</tr>
<tr>
<td valign="top">

Authorization

</td>
<td valign="top">

token

</td>
<td valign="top">

*<access token retrieved when logging in with the OAuth client\>*

</td>
</tr>
<tr>
<td valign="top">

Header

</td>
<td valign="top">

key

</td>
<td valign="top">

`x-sap-sac-custom-auth=true`

</td>
</tr>
<tr>
<td valign="top">

Header

</td>
<td valign="top">

key

</td>
<td valign="top">

`x-csrf-token: fetch`

</td>
</tr>
</table>

Syntax of GET request:

```
<tenant_url>/api/v1/csrf
```

The CSRF token is returned in the `x-csrf-token` response header. This token can then be included in the POST, PUT, PATCH, or DELETE request in the <code>x-csrf-token:<i class="varname">&lt;token&gt;</i></code> header.



<a name="loio1ca8c4a9467f43df9ae6d4ed3734f05a__section_js2_yfw_rbc"/>

## List Users

To retrieve users, use the GET request with the`/api/v1/scim2/Users` endpoint and the following elements:


<table>
<tr>
<th valign="top">

Request Component

</th>
<th valign="top">

Setting

</th>
<th valign="top">

Value

</th>
</tr>
<tr>
<td valign="top">

Authorization

</td>
<td valign="top">

type

</td>
<td valign="top">

`Bearer Token`

</td>
</tr>
<tr>
<td valign="top">

Authorization

</td>
<td valign="top">

token

</td>
<td valign="top">

*<access token retrieved when logging in with the OAuth client\>*

</td>
</tr>
<tr>
<td valign="top">

Header

</td>
<td valign="top">

key

</td>
<td valign="top">

`x-sap-sac-custom-auth=true`

</td>
</tr>
</table>

To list all the users existing in the tenant, enter:

```
https://<tenant_url>/api/v1/scim2/Users
```

You can control the list of users to retrieve by using one or more of the following optional URL parameters:


<table>
<tr>
<th valign="top">

Parameter

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

`sortBy`

</td>
<td valign="top">

Specifies the user attribute to sort the results by.

For example, to retieve the list of users sorted by user name:

```
sortBy=userName
```



</td>
</tr>
<tr>
<td valign="top">

`sortOrder`

</td>
<td valign="top">

Specifies the order in which items are returned, either ascending or descending. By default, an ascending sort order is used.

To retieve the list of users by descending order:

```
sortOrder=descending
```



</td>
</tr>
<tr>
<td valign="top">

`startIndex`

</td>
<td valign="top">

Specifies the index of the first user to fetch.

For example, so that the tenth user is the first user retireved:

```
startIndex=10
```



</td>
</tr>
<tr>
<td valign="top">

`count`

</td>
<td valign="top">

Specifies the number of users to return on each page.

For example, to display a maximum of 8 users on a page:

```
count=8
```



</td>
</tr>
<tr>
<td valign="top">

<code>filter=<i class="varname">&lt;attribute&gt;</i></code>

</td>
<td valign="top">

Adds a filter to the request.

For example, to display the users whose user name include the letter K:

```
filter=userName co "K"
```

See the user schema for available attributes. All operators are supported.

</td>
</tr>
</table>

Example of a GET request with the various parameters:

```
https://<tenant_url>/api/v1/scim2/Users/?filter=emails.value co "a"&sortOrder=descending&startIndex=3&count=2&sortBy=emails.value
```

> ### Caution:  
> GET requests send personal identifiable information as part of the URL, such as the user name in this case. Consider using the POST request with the /api/v1/scim2/Users/.search endpoint instead for enhanced privacy of personal information. Syntax of POST request:
> 
> ```
> https://<tenant_url>/api/v1/scim2/Users/.search 
> ```

> ### Note:  
> In the response body, if the users listed are assigned to roles, you can identify the roles as they are prefixed with `PROFILE`.



<a name="loio1ca8c4a9467f43df9ae6d4ed3734f05a__section_esx_kxt_vbc"/>

## Get a Specific User

To retrieve a specific user based on its ID, use the GET request with the <code>/api/v1/scim2/Users/<i class="varname">&lt;user ID&gt;</i></code> endpoint and the following elements:


<table>
<tr>
<th valign="top">

Request Component

</th>
<th valign="top">

Setting

</th>
<th valign="top">

Value

</th>
</tr>
<tr>
<td valign="top">

Authorization

</td>
<td valign="top">

type

</td>
<td valign="top">

`Bearer Token`

</td>
</tr>
<tr>
<td valign="top">

Authorization

</td>
<td valign="top">

token

</td>
<td valign="top">

*<access token retrieved when logging in with the OAuth client\>*

</td>
</tr>
<tr>
<td valign="top">

Header

</td>
<td valign="top">

key

</td>
<td valign="top">

`x-sap-sac-custom-auth=true`

</td>
</tr>
</table>

To retrieve a specific user based on its ID, enter the GET request:

```
https://<tenant_url>/api/v1/scim2/Users/<user ID>
```

The user ID must be the UUID \(universally unique identifier\), which you can get by sending the GET request:

```
https://<tenant_url>/api/v1/scim2/Users
```

> ### Note:  
> In the response body, if the user is assigned to roles, you can identify with their prefix `PROFILE`.



<a name="loio1ca8c4a9467f43df9ae6d4ed3734f05a__section_nqs_5lp_tbc"/>

## Create a User

To create a user, use the POST request with the`/api/v1/scim2/Users/` endpoint and the following elements:


<table>
<tr>
<th valign="top">

Request Component

</th>
<th valign="top">

Setting

</th>
<th valign="top">

Value

</th>
</tr>
<tr>
<td valign="top">

Authorization

</td>
<td valign="top">

type

</td>
<td valign="top">

`Bearer Token`

</td>
</tr>
<tr>
<td valign="top">

Authorization

</td>
<td valign="top">

token

</td>
<td valign="top">

*<access token retrieved when logging in with the OAuth client\>*

</td>
</tr>
<tr>
<td valign="top">

Header

</td>
<td valign="top">

key

</td>
<td valign="top">

`x-sap-sac-custom-auth=true`

</td>
</tr>
<tr>
<td valign="top">

Header

</td>
<td valign="top">

key

</td>
<td valign="top">

`x-csrf-token: csrf token value`

</td>
</tr>
</table>

Syntax of POST request: <code>https://<i class="varname">&lt;Tenant_URL&gt;</i>/api/v1/scim2/Users/</code>

> ### Note:  
> The following information are required: `userName`, `name`, and `emails` information. Other information that are not provided will be either left empty or set to its default value.
> 
> If you are using SAML authentication, `idpUserId` should be set to the property you are using for your SAML mapping. For example, the user's *USER ID*, *EMAIL*, or *CUSTOM SAML MAPPING*. If your SAML mapping is set to *EMAIL*, the email address you add to `idpUserId` must match the email address you use for `email`.
> 
> To find this information, log on to SAP Datasphere and go to *\(Security\)* \> *\(Users\)*.

> ### Note:  
> When creating or modifying a user, you can add optional properties to the user.

The following example shows how to create a new user:

```
{
    "schemas": [
        "urn:ietf:params:scim:schemas:core:2.0:User",
        "urn:ietf:params:scim:schemas:extension:enterprise:2.0:User"
    ],
    "userName": "LGARCIA",
    "name": {
        "familyName": "Garcia",
        "givenName": "Lisa",
        "formatted": "Lisa Garcia"
    },
    "displayName": "Lisa Garcia",
    "preferredLanguage": "en",
    "active": true,
    "emails": [
    {
        "value": "lisa.garcia@company.com",
        "type": "work",
        "primary": true
    }
    ],
    "urn:sap:params:scim:schemas:extension:sac:2.0:user-custom-parameters": {
        "idpUserId": "lisa.garcia@company.com"
     }
}

```

The following example shows how to create a new user and assign it to a role:

```
{
    "schemas": [
        "urn:ietf:params:scim:schemas:core:2.0:User",
        "urn:ietf:params:scim:schemas:extension:enterprise:2.0:User"
    ],
    "userName": "LGARCIA",
    "name": {
        "familyName": "Garcia",
        "givenName": "Lisa",
        "formatted": "Lisa Garcia"
    },
    "displayName": "Lisa Garcia",
    "preferredLanguage": "en",
    "active": true,
    "emails": [
    {
        "value": "lisa.garcia@company.com",
        "type": "work",
        "primary": true
    }
    ],
	"roles": [
        {
            "value": "PROFILE:t.V:Sales_Modeler",
            "display": "Sales_Modeler",
            "primary": true
        }    ],
    "urn:sap:params:scim:schemas:extension:sac:2.0:user-custom-parameters": {
        "idpUserId": "lisa.garcia@company.com"
     }
}

```

The response body returns the ID of the user created, which is the user UUID \(universally unique identifier\).

> ### Note:  
> When creating or modifying a user via the API, you can also assign the user to one or more roles - either global or scoped, provided that the roles already exist in the tenant:
> 
> -   Before you can add one or more users to a scoped role, one space at least must be assigned to the scoped role.
> 
> -   When a user is added to a scoped role, the user is given access to all the spaces included in the scoped role.
> 
> -   All roles are prefixed with `PROFILE`. Custom and scoped roles have IDs in the following format: PROFILE:<t.\#\>:<role\_name\>.



<a name="loio1ca8c4a9467f43df9ae6d4ed3734f05a__section_zq5_rlp_tbc"/>

## Modify a User

You can modify a specific user either way:

-   To override all information related to a specific user, use a PUT request. The user properties are updated with the properties you provide and all the properties that you do not provide are either left empty or set to their default value.
-   To update only some information related to a specific user, use a PATCH request. The user properties are updated with the changes you provide and all properties that you do not provide remain unchanged.

You can use either the PUT \(override\) or PATCH \(update\) request with the<code>/api/v1/scim2/Users/<i class="varname">&lt;user ID&gt;</i></code> endpoint and the following elements:


<table>
<tr>
<th valign="top">

Request Component

</th>
<th valign="top">

Setting

</th>
<th valign="top">

Value

</th>
</tr>
<tr>
<td valign="top">

Authorization

</td>
<td valign="top">

type

</td>
<td valign="top">

`Bearer Token`

</td>
</tr>
<tr>
<td valign="top">

Authorization

</td>
<td valign="top">

token

</td>
<td valign="top">

*<access token retrieved when logging in with the OAuth client\>*

</td>
</tr>
<tr>
<td valign="top">

Header

</td>
<td valign="top">

key

</td>
<td valign="top">

`x-sap-sac-custom-auth=true`

</td>
</tr>
<tr>
<td valign="top">

Header

</td>
<td valign="top">

key

</td>
<td valign="top">

`x-csrf-token: csrf token value`

</td>
</tr>
</table>

Syntax of PUT or PATCH request:

```
https://<tenant_url>/api/v1/scim2/Users/<user ID>
```

> ### Note:  
> If you are using SAML authentication, and you are using *USER ID* as your SAML mapping, you cannot change the `userName` using this API. The `userName` you use in the request body must match the user *<ID\>*.
> 
> The `active` attribute is not currently used and will not activate or deactivate users.

> ### Note:  
> When creating or modifying a user, you can add optional properties to the user.

The following example shows how to assign a user to a role:

```
{
    "schemas": [
        "urn:sap:params:scim:schemas:extension:sac:2.0:user-custom-parameters",
        "urn:ietf:params:scim:schemas:core:2.0:User"
    ],
    "id": "userID-00001",
    "meta": {
        "resourceType": "User",
        "location": "/api/v1/scim2/Users/userID-00001"
    },
    "userName": "LGARCIA",
    "name": {
        "familyName": "Garcia",
        "givenName": "Lisa",
        "formatted": "Lisa Garcia"
    },
    "displayName": "Lisa Garcia",
    "preferredLanguage": "en",
    "active": true,
    "emails": [
        {
            "value": "lisa.garcia@company.com",
            "type": "work",
            "primary": true
        }
    ],
    "roles": [
        {
            "value": "PROFILE:t.V:Sales_Modeler",
            "display": "Sales_Modeler",
            "primary": true
        }    ],
    "urn:sap:params:scim:schemas:extension:sac:2.0:user-custom-parameters": {
        "idpUserId": "lisa.garcia@company.com"
        }
}

```

> ### Note:  
> When creating or modifying a user via the API, you can also assign the user to one or more roles - either global or scoped, provided that the roles already exist in the tenant:
> 
> -   Before you can add one or more users to a scoped role, one space at least must be assigned to the scoped role.
> 
> -   When a user is added to a scoped role, the user is given access to all the spaces included in the scoped role.
> 
> -   All roles are prefixed with `PROFILE`. Custom and scoped roles have IDs in the following format: PROFILE:<t.\#\>:<role\_name\>.



<a name="loio1ca8c4a9467f43df9ae6d4ed3734f05a__section_jhl_xlp_tbc"/>

## Delete a User

To delete a user, use the DELETE request with the<code>/api/v1/scim2/Users/<i class="varname">&lt;user ID&gt;</i></code> endpoint and the following elements:


<table>
<tr>
<th valign="top">

Request Component

</th>
<th valign="top">

Setting

</th>
<th valign="top">

Value

</th>
</tr>
<tr>
<td valign="top">

Authorization

</td>
<td valign="top">

type

</td>
<td valign="top">

`Bearer Token`

</td>
</tr>
<tr>
<td valign="top">

Authorization

</td>
<td valign="top">

token

</td>
<td valign="top">

*<access token retrieved when logging in with the OAuth client\>*

</td>
</tr>
<tr>
<td valign="top">

Header

</td>
<td valign="top">

key

</td>
<td valign="top">

`x-sap-sac-custom-auth=true`

</td>
</tr>
<tr>
<td valign="top">

Header

</td>
<td valign="top">

key

</td>
<td valign="top">

`x-csrf-token: csrf token value`

</td>
</tr>
</table>

To delete a specific user based on its ID, enter the DELETE request:

```
https://<tenant_url>/api/v1/scim2/Users/<user ID>
```

The user ID must be the UUID \(universally unique identifier\), which you can get by sending the GET request:

```
https://<tenant_url>/api/v1/scim2/Users
```



<a name="loio1ca8c4a9467f43df9ae6d4ed3734f05a__section_vpq_skn_xbc"/>

## Optional User Properties

You can add optional parameters to the user when creating or modifying a user, in addition to the required properties \(`userName`, `name`, and `emails`\).


<table>
<tr>
<th valign="top">

Parameter

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

`preferredLanguage`

</td>
<td valign="top">

Specifies the language in which to view the SAP Datasphere interface.

Allowed values:

-   ISO 639-1 two-letter language code. For example, `en`.

-   Concatenation of an ISO 639-1 two-letter language code, a dash, and ISO 3166-1 two-letter country code. For example, `en-us`.


Default value: `en`

Example

```
"preferredLanguage": "en",
```



</td>
</tr>
<tr>
<td valign="top" colspan="2">

The following parameters must be included in an `urn:ietf:params:scim:schemas:extension:sap:user-custom-parameters:1.0` block within the user schema.

</td>
</tr>
<tr>
<td valign="top">

`dataAccessLanguage`

</td>
<td valign="top">

Specifies the default language in which to display text data in SAP Analytics Cloud.

Allowed values:

-   ISO 639-1 two-letter language code. For example, `en`.

-   Concatenation of an ISO 639-1 two-letter language code, a dash, and ISO 3166-1 two-letter country code. For example, `en-us`.


Default value: `en`

</td>
</tr>
<tr>
<td valign="top">

`dateFormatting`

</td>
<td valign="top">

Specifies the date display format.

Allowed values:

-   `MMM d, yyyy`
-   `MMM dd, yyyy`
-   `yyyy.MM.dd`
-   `dd.MM.yyyy`
-   `MM.dd.yyyy`
-   `yyyy/MM/dd`
-   `dd/MM/yyyy`
-   `MM/dd/yyyy`

Default value: `MMM d, yyyy`

</td>
</tr>
<tr>
<td valign="top">

`numberFormatting`

</td>
<td valign="top">

Specifies the number format.

Allowed values: `1,234.56`, `1.234,56` or `1 234,56`

Default value: `1,234.56`

</td>
</tr>
<tr>
<td valign="top">

`timeFormatting`

</td>
<td valign="top">

Specifies the time display format.

Allowed values:

`H:mm:ss`, `h:mm:ss a` or `h:mm:ss A`

> ### Note:  
> -   `H:mm:ss` corresponds to 24-Hour Format. For example, 16:05:10.
> -   `h:mm:ss a` corresponds to 12-Hour Format. For example, 4:05:10 p.m.
> -   `h:mm:ss A` corresponds to 12-Hour Format. For example, 4:05:10 PM.

Default value: `H:mm:ss`

</td>
</tr>
</table>

Example:

```
"urn:ietf:params:scim:schemas:extension:sap:user-custom-parameters:1.0": {
  "dataAccessLanguage": "en",
  "dateFormatting": "MMM d, yyyy",
  "timeFormatting": "H:mm:ss",
  "numberFormatting": "1,234.56",
  "cleanUpNotificationsNumberOfDays": 0,
  "systemNotificationsEmailOptIn": true,
  "marketingEmailOptIn": false
  },
```



<a name="loio1ca8c4a9467f43df9ae6d4ed3734f05a__section_n1l_vdy_rbc"/>

## Get Information About the SCIM API

Using the GET request, you can obtain the following information about the SCIM API:

-   `/scim2/ServiceProviderConfig` - Gets information about the identity provider being used with your SAP Datasphere tenant.

-   `/scim2/Schemas` - Gets information on the schemas used for user management.

-   `/scim2/ResourceTypes` - Gets information on all available resource types.

-   <code>/scim2/ResourceTypes/<i class="varname">&lt;Type&gt;</i></code> - Gets information on a specific resource type.


