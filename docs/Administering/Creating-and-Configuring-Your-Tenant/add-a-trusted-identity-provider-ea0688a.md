<!-- loioea0688aef2f94b35ae34d930b3cb0c10 -->

# Add a Trusted Identity Provider

If you use the OAuth 2.0 SAML Bearer Assertion workflow, you must add a trusted identity provider to SAP Datasphere.



<a name="loioea0688aef2f94b35ae34d930b3cb0c10__prereq_v2y_pct_yfb"/>

## Prerequisites

The corresponding OAuth Client must be added to SAP Datasphere. For more information, see [Create OAuth2.0 Clients to Authenticate Against SAP Datasphere](create-oauth2-0-clients-to-authenticate-against-sap-datasphere-3f92b46.md).



<a name="loioea0688aef2f94b35ae34d930b3cb0c10__context_ygg_5r5_bpb"/>

## Context

The OAuth 2.0 SAML Bearer Assertion workflow allows a third-party application access to protected resources without prompting users to log into SAP Datasphere when there is an existing SAML assertion from the third-party application identity provider.

> ### Note:  
> Both SAP Datasphere and the third-party application must be configured with the same identity provider.



<a name="loioea0688aef2f94b35ae34d930b3cb0c10__steps_zgg_5r5_bpb"/>

## Procedure

1.  Go to *System* \> *Administration* \> *App Integration*.

2.  In *Trusted Identity Providers*, select *Add a Trusted Identity Provider*.

3.  In the dialog, add a unique *Name* for the trusted identity provider. This name is used only for identification purposes, and will appear in the list of trusted identity providers.

4.  Add the identity provider name. The *Provider Name* must be unique.

    > ### Note:  
    > The provider name can contain only alphabet characters \(a-z & A-Z\), numbers \(0-9\), underscore \(\_\), dot \(.\), hyphen \(-\), and cannot exceed 36 characters.

5.  Provide signing certificate information for the third-party application server.

    > ### Note:  
    > The signing certificate information must be in X.509 Base64 encoded format.

6.  Select *Add*.




<a name="loioea0688aef2f94b35ae34d930b3cb0c10__postreq_uk1_nct_yfb"/>

## Next Steps

The identity providers that you added will appear in lists on the *App Integration* page. Hover over an identity provider and select*Edit* to update information or *Delete* to delete it.

You may need to use the *Authorization URL* and *Token URL* listed here to complete setup on your OAuth clients.

