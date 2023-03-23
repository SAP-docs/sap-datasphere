<!-- loioffb0b24bea57480a95145eb094f5bb0f -->

# Add a New OAuth Client

You can add a new OAuth client.



## Procedure

1.  Go to *System* \> *Administration* \> *App Integration*.

2.  Under *Configured Clients*, select *Add a New OAuth Client*.

3.  In the dialog, add a *Name* for the OAuth client.

4.  From the *Purpose* list, select the intended use for your OAuth client:

    -   *Interactive Usage* \(default\)

        Accessing protected resources using an interactive usage OAuth client requires a valid SAML-based user context.

    -   *API Access*

        An API access OAuth client allows a third-party application to access SAP Datasphere public APIs without a SAML assertion. For more information, see [Authorization for API access OAuth Clients](authorization-for-api-access-oauth-clients-74dc627.md).

    -   If you selected *API Access*, choose at least one option from the *Access* list:
        -   *Story Listing*: This OAuth client privilege allows a third-party application to access a list of stories in your system.

        -   *User Provisioning*: This OAuth client privilege allows a third-party application to manage users in your system.



5.  Enter a *Redirect URl*. The URI must be the exact URI where access or refresh tokens are returned too. If the URI has dynamic parameters, use a wildcard pattern for the URI. For example, `https://redirect_host/**`

6.  Select *Add*.

    > ### Note:  
    > The *Token Lifetime* and *Refresh Token Lifetime* cannot be configured.

7.  If you are using OAuth 2.0 you must provide the following information to your client application:

    -   *Authorization URL*: The OAuth 2.0 Authorization URL.
    -   *Token URL*: The OAuth 2.0 Token Service URL.
    -   *OAuth2SAML Token URL*: The OAuth 2.0 Token Service URL to be used in the OAuth 2.0 SAML Bearer Assertion workflow.
    -   *OAuth2SAML Audience*: The audience to be used by the OAuth 2.0 SAML Bearer Assertion workflow.


