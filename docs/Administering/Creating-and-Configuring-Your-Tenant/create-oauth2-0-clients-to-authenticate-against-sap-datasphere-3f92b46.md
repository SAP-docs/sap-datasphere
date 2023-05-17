<!-- loio3f92b46fe0314e8ba60720e409c219fc -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Create OAuth2.0 Clients to Authenticate Against SAP Datasphere

Users with the *DW Administrator* role can create OAuth2.0 clients and provide the client parameters to users who need to connect clients, tools, or apps to SAP Datasphere.



## Context

Users that have access to an OAuth client can:

-   [Consume SAP Datasphere Data in SAP Analytics Cloud via an OData Service](https://help.sap.com/viewer/43509d67b8b84e66a30851e832f66911/cloud/en-US/9de2c660fd3b4db2b89ad25e584e8857.html "You can create an import data connection in SAP Analytics Cloud to consume data from a view exposed via the SAP Datasphere OData API and consume it in an SAP Analytics Cloud model.") :arrow_upper_right:
-   [Consume Data in Power BI and Other Clients, Tools, and Apps via an OData Service](https://help.sap.com/viewer/43509d67b8b84e66a30851e832f66911/cloud/en-US/add771abf6f54c9d8de4c7e470a0e6f0.html "You can consume data exposed as views in Microsoft Power BI and other third-party clients, tools, and apps via the OData API.") :arrow_upper_right:

    > ### Note:  
    > Consuming exposed data in third-party clients, tools, and apps via an OData service requires a three-legged OAuth2.0 flow with type `authorization_code`. Users must manually authenticate against the configured IDP in order to generate the authorization code before continuing with the remaining OAuth2.0 steps.

-   [Log into the Command Line Interface via an OAuth Client](../Creating-Spaces-and-Allocating-Storage/log-into-the-command-line-interface-via-an-oauth-client-eb7228a.md)



<a name="loio3f92b46fe0314e8ba60720e409c219fc__steps_bh1_spq_gxb"/>

## Procedure

1.  In the side navigation area, click <span class="FPA-icons"></span> \(*System*\) ** \> ** <span class="Belize-icons"></span> \(*Administration*\) ** \> *App Integration*.

2.  Under *Configured Clients*, select *Add a New OAuth Client*.

3.  In the dialog, add a *Name* for the OAuth client.

4.  From the *Purpose* list, select *Interactive Usage*.

    > ### Note:  
    > The *API Access* purpose is not used in SAP Datasphere.

5.  Enter a *Redirect URl* to indicate to where the user will be redirected after authorization. If the URI has dynamic parameters, use a wildcard pattern \(for example, `https://redirect_host/**`\).

    The client, tool, or app that you want to connect is responsible for providing the redirect URI.

    When creating an OAuth client to allow SAP Analytics Cloud to connect to SAP Datasphere via an OData services connection \(see [Consume SAP Datasphere Data in SAP Analytics Cloud via an OData Service](https://help.sap.com/viewer/43509d67b8b84e66a30851e832f66911/cloud/en-US/9de2c660fd3b4db2b89ad25e584e8857.html "You can create an import data connection in SAP Analytics Cloud to consume data from a view exposed via the SAP Datasphere OData API and consume it in an SAP Analytics Cloud model.") :arrow_upper_right:\), use the *Redirect URl* provided in the SAP Analytics Cloud connection dialog.

6.  Select *Add*.

    > ### Note:  
    > The *Token Lifetime* and *Refresh Token Lifetime* cannot be configured.

    Provide the following information to users who will use the client:

    -   *Client ID*
    -   *Secret*
    -   *OAuth2SAML Token URL* - To be used in the OAuth 2.0 SAML Bearer Assertion workflow.
    -   *OAuth2SAML Audience* - To be used in the OAuth 2.0 SAML Bearer Assertion workflow.

    > ### Note:  
    > Consuming exposed data in third-party clients, tools, and apps via an OData service requires a three-legged OAuth2.0 flow with type `authorization_code`. Users must manually authenticate against the configured IDP in order to generate the authorization code before continuing with the remaining OAuth2.0 steps.


