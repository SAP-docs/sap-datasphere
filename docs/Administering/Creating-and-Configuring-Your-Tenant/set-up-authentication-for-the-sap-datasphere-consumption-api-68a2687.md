<!-- loio68a268723c014510808bde279f4386fa -->

# Set up Authentication for the SAP Datasphere Consumption API

To use the SAP Datasphere Consumption API you must configure a OAuth client to work with your application.



<a name="loio68a268723c014510808bde279f4386fa__context_lvd_g3p_55b"/>

## Context

These are the specific steps to create a OAuth client to use the SAP Datasphere Consumption API.



## Procedure

1.  Go to *System* \> *Administration* \> *App Integration*.

2.  Under *Configured Clients*, select *Add a New OAuth Client*.

3.  In the dialog, add a *Name* for the OAuth client.

4.  From the *Purpose* list, select *Interactive Usage*:

    Accessing protected resources using an interactive usage OAuth client requires a valid SAML-based user context.

5.  Enter a *Redirect URL*. The URL must be the exact URL where access or refresh tokens are returned to. If the URL has dynamic parameters, use a wildcard pattern for the URL. For example, `https://redirect_host/**`

    > ### Note:  
    > For usage with SAP Analytics Cloud OData Service connection use the redirect URL provided in the connection creation dialog.

6.  Select *Add*.

    > ### Note:  
    > The *Token Lifetime* and *Refresh Token Lifetime* cannot be configured.

7.  If you are using OAuth 2.0 you must provide the following information to your client application:

    -   *Authorization URL*: The OAuth 2.0 Authorization URL.
    -   *Token URL*: The OAuth 2.0 Token Service URL.
    -   *OAuth2SAML Token URL*: The OAuth 2.0 Token Service URL to be used in the OAuth 2.0 SAML Bearer Assertion workflow.
    -   *OAuth2SAML Audience*: The audience to be used by the OAuth 2.0 SAML Bearer Assertion workflow.


