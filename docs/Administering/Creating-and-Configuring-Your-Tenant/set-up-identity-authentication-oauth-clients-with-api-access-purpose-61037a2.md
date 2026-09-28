<!-- loio61037a287ba04cbdb289c1bff3b9df54 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Set Up Identity Authentication OAuth Clients with API Access Purpose

Users with an administrator role can set up Open Authorization \(OAuth\) access using Identity Authentication OAuth Clients with the API Access purpose and provide client parameters to users who need to connect clients, tools, or apps to SAP Datasphere.



## Context

You can set up Identity Authentication OAuth Clients with an API Access purpose to provide access with tenant-wide privileges.

> ### Note:  
> To limit users’ access to specific spaces, consider using an OAuth client with a *Technical User* purpose \(see [Set Up Identity Authentication OAuth Clients with Technical User Purpose](set-up-identity-authentication-oauth-clients-with-technical-user-purpose-4298cd0.md)\).



## Procedure

1.  In the side navigation area, select <span class="FPA-icons-V3"></span> \(*System*\) ** \> ** <span class="Belize-icons"></span> \(*Administration*\) ** \> *App Integration*.

2.  In the *Identity Authentication OAuth Clients* section, under *Configured Clients*, choose *Register OAuth Client from Identity Authentication*.

3.  In the *Select Client* screen, you must select an available client by typing the Identity Authentication application name or OAuth client ID in the search bar or selecting it in the *Available Clients* list.

    > ### Note:  
    > The OAuth clients already being used cannot be selected again, as each Identity Authentication client can only be used once.

4.  After selecting a client, choose *Next Step*.

5.  In the *Client Details* screen, in the *Name* field, enter a name to identify the Identity Authentication client. The *Application Name*, *Application ID*, and *Purpose* fields are automatically selected and cannot be changed.

6.  From the *Purpose* options, select *API Access*.

7.  From the *Access* options, assign one or more access scopes to the API Access, then choose *Next Step*.

    > ### Note:  
    > The Identity Authentication creates OAuth clients using API Access, and it grants permissions based on selected access scopes. An API Access OAuth client allows a third-party application to access public APIs without a SAML assertion. For more information, see the Authorize API Access for OAuth Clients section.

8.  In the *Review* screen, you review the name and access scopes, then choose *Add*. SAP Business Data Cloud supports a maximum of 100 OAuth clients simultaneously.

9.  *Configured Clients* shows the added clients, and you can hover over the list to update or delete them.

    > ### Caution:  
    > If you need to revert to a previously used OAuth client authentication, delete any new Identity Authentication OAuth Clients that are no longer necessary.


