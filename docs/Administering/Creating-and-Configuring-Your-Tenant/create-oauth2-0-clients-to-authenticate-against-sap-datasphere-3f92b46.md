<!-- loio3f92b46fe0314e8ba60720e409c219fc -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Create OAuth2.0 Clients to Authenticate Against SAP Datasphere

Users with the *DW Administrator* role can create OAuth2.0 clients and provide the client parameters to users who need to connect clients, tools, or apps to SAP Datasphere.



<a name="loio3f92b46fe0314e8ba60720e409c219fc__steps_bh1_spq_gxb"/>

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
    
    Select the appropriate purpose:

    -   *Interactive Usage*:
        -   To use the `datasphere` command line interface \([Log into the Command Line Interface via an OAuth Client](https://help.sap.com/viewer/9b8363ae47c347de9a027c0e5567a37a/DEV_CURRENT/en-US/eb7228a171a842fa84e48c899d48c970.html "If an administrator has created an OAuth client (with Purpose set to Interactive Usage) for datasphere command line interface users to log into, there are several methods for accessing it.") :arrow_upper_right:\).
        -   To consume data via the OData API \(see [Consume SAP Datasphere Data in SAP Analytics Cloud via an OData Service](https://help.sap.com/viewer/43509d67b8b84e66a30851e832f66911/cloud/en-US/9de2c660fd3b4db2b89ad25e584e8857.html "You can create an import data connection in SAP Analytics Cloud to consume data from a view exposed via the SAP Datasphere OData API and consume it in an SAP Analytics Cloud model.") :arrow_upper_right:\).

            > ### Note:  
            > Consuming exposed data in third-party clients, tools, and apps via an OData service requires a three-legged OAuth2.0 flow with type `authorization_code`.


    -   *API Access*:
        -   To use the SCIM 2.0 API \(see [Create Users and Assign Them to Roles via the SCIM 2.0 API](../Managing-Users-and-Roles/create-users-and-assign-them-to-roles-via-the-scim-2-0-api-1ca8c4a.md)\).
        -   To transport content through SAP Cloud Transport Management \(see [Transporting Your Content through SAP Cloud Transport Management](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/05383980f0704c71ab9872360ce45622.html "Integrate SAP Datasphere with SAP Cloud Transport Management service to transport content packages across different landscapes.") :arrow_upper_right:\).



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Access
    
    </td>
    <td valign="top">
    
    \[API Access only\] Select the appropriate access:

    -   *User Provisioning* - To use the SCIM 2.0 API \(see [Create Users and Assign Them to Roles via the SCIM 2.0 API](../Managing-Users-and-Roles/create-users-and-assign-them-to-roles-via-the-scim-2-0-api-1ca8c4a.md)\).
    -   *Analytics Content Network Interaction* - To transport content through SAP Cloud Transport Management \(see [Transporting Your Content through SAP Cloud Transport Management](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/05383980f0704c71ab9872360ce45622.html "Integrate SAP Datasphere with SAP Cloud Transport Management service to transport content packages across different landscapes.") :arrow_upper_right:\).


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Authorization Grant
    
    </td>
    <td valign="top">
    
    Depending on the purpose selected, the following authorization grants are available:

    -   *Interactive Usage* - *Authorization Code* is selected and cannot be changed.
    -   *API Access* - select one of the following:
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
    
    Redirect URI
    
    </td>
    <td valign="top">
    
    Enter a URI to indicate to where the user will be redirected after authorization. If the URI has dynamic parameters, use a wildcard pattern \(for example, `https://redirect_host/**`\).

    The client, tool, or app that you want to connect is responsible for providing the redirect URI:

    -   When working with the `datasphere` command line interface, set this value to `http://localhost:8080/` \(see [Accessing SAP Datasphere via the Command Line](https://help.sap.com/viewer/9b8363ae47c347de9a027c0e5567a37a/DEV_CURRENT/en-US/3f9a42ccde6b4b6aba121e2aab79c36d.html "Many of the features available to SAP Datasphere users can also be accessed via the command line.") :arrow_upper_right:\).
    -   When connecting SAP Analytics Cloud to SAP Datasphere via an OData services connection, use the *Redirect URl* provided in the SAP Analytics Cloud connection dialog \(see [Consume SAP Datasphere Data in SAP Analytics Cloud via an OData Service](https://help.sap.com/viewer/43509d67b8b84e66a30851e832f66911/cloud/en-US/9de2c660fd3b4db2b89ad25e584e8857.html "You can create an import data connection in SAP Analytics Cloud to consume data from a view exposed via the SAP Datasphere OData API and consume it in an SAP Analytics Cloud model.") :arrow_upper_right:\).

    > ### Note:  
    > *Redirect URI* is not available if you've selected *API Access* as the purpose.


    
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
    <tr>
    <td valign="top">
    
    Refresh Token Lifetime
    
    </td>
    <td valign="top">
    
    Enter a lifetime for the refresh token from a minimum of 60 seconds to a maximum of 180 days.

    Default: 30 days
    
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
    -   *Authorization URL*
    -   *Token URL*.

    Users must manually authenticate against the IDP in order to generate the authorization code before continuing with the remaining OAuth2.0 steps.
    
    </td>
    <td valign="top">
    
    -   *Client ID*
    -   *Secret*
    -   *OAuth2SAML Token URL*
    -   *OAuth2SAML Audience*

    Users authenticate with their third-party app, which has a trusted relationship with the IDP, and do not need to re-authenticate \(see [Add a Trusted Identity Provider](add-a-trusted-identity-provider-ea0688a.md)\).
    
    </td>
    </tr>
    </table>
    

