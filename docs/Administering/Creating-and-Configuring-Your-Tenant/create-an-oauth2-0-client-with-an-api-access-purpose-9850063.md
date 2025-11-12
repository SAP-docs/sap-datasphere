<!-- loio98500631fdd14762b702ad97d106c663 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Create an OAuth2.0 Client with an API Access Purpose

Users with an administrator role can create OAuth2.0 clients with an API access purpose and provide the client parameters to users who need to connect clients, tools, or apps to SAP Datasphere.



## Context

You create an OAuth2.0 Client with an *API Access* purpose:

-   To use the SCIM 2.0 API \(see [Create Users and Assign Them to Roles via the SCIM 2.0 API](../Managing-Users-and-Roles/create-users-and-assign-them-to-roles-via-the-scim-2-0-api-1ca8c4a.md)\).
-   To transport content through SAP Cloud Transport Management \(see [Transporting Your Content through SAP Cloud Transport Management](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/05383980f0704c71ab9872360ce45622.html "Integrate SAP Datasphere with SAP Cloud Transport Management service to transport content packages across different landscapes.") :arrow_upper_right:\).

> ### Note:  
> An *API Access* purpose provides tenant-wide privileges. To limit users’ access to specific spaces, consider using an OAuth client with a *Technical User* purpose.



## Procedure

1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(*System*\) ** \> ** <span class="Belize-icons"></span> \(*Administration*\) ** \> *App Integration*.

2.  Under *Configured Clients*, select *Add a New OAuth Client*.

3.  In the dialog, enter or review the following properties as appropriate:


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
    
    Name
    
    </td>
    <td valign="top">
    
    Enter a name to identify the OAuth client.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    OAuth Client ID
    
    </td>
    <td valign="top">
    
    \[read-only\] Displays the ID once the client is created.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Purpose
    
    </td>
    <td valign="top">
    
    Select *API Access*.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Access
    
    </td>
    <td valign="top">
    
    Select the appropriate access:

    -   *User Provisioning* - To use the SCIM 2.0 API \(see [Create Users and Assign Them to Roles via the SCIM 2.0 API](../Managing-Users-and-Roles/create-users-and-assign-them-to-roles-via-the-scim-2-0-api-1ca8c4a.md)\).
    -   *Analytics Content Network Interaction* - To transport content through SAP Cloud Transport Management \(see [Transporting Your Content through SAP Cloud Transport Management](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/05383980f0704c71ab9872360ce45622.html "Integrate SAP Datasphere with SAP Cloud Transport Management service to transport content packages across different landscapes.") :arrow_upper_right:\).


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Authorization Grant
    
    </td>
    <td valign="top">
    
    Select one of the following:

    -   *Client Credentials* - If the client application is accessing its own resources or when the permission to access resources has been granted by the resource owner via another mechanism. To use the SCIM 2.0 API, select this option \(see [Create Users and Assign Them to Roles via the SCIM 2.0 API](../Managing-Users-and-Roles/create-users-and-assign-them-to-roles-via-the-scim-2-0-api-1ca8c4a.md)\).
    -   *SAML2.0 Bearer* - If the user context is passed using SAML or to control access based on user permissions using SAML. This option requires specific client-side infrastructure to support SAML.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Secret
    
    </td>
    <td valign="top">
    
    \[read-only\] Allows the secret to be copied immediately after the client is created. 

    > ### Note:  
    > Once you close the dialog, the secret is no longer available.

    > ### Note:  
    > Clients created before v2024.08 have a *Show Secret* button, which allows you to display and copy the secret at any time after the client is created.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Token Lifetime
    
    </td>
    <td valign="top">
    
    Enter a lifetime for the access token from a minimum of 60 seconds to a maximum of one day.

    Default: 60 minutes
    
    </td>
    </tr>
    </table>
    
4.  Click *Add* to create the client and generate the ID and secret.

5.  Copy the secret, save it securely, and then close the dialog.

    > ### Note:  
    > You won't be able to copy the secret again. If you lose it, you will need to create a new client.

6.  Provide the following information to users who will use the client:


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

    Users of a client with a *Technical User* purpose can then access their resource directly. Users of clients with other purposes must authenticate with their third-party app, which has a trusted relationship with the IDP, and do not need to re-authenticate \(see [Add a Trusted Identity Provider](add-a-trusted-identity-provider-ea0688a.md)\). See also the blog [Integrating with SAP Datasphere Consumption APIs using SAML Bearer Assertion](https://community.sap.com/t5/technology-blogs-by-sap/integrating-with-sap-datasphere-consumption-apis-using-saml-bearer/ba-p/13647905) \(published March 2024\). 
    
    </td>
    </tr>
    </table>
    

