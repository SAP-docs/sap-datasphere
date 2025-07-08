<!-- loio48b5c8b637a54fa491594272941855b9 -->

# Managing User Identity and Authentication

The system owner can choose how to manage user identity and authentication for its SAP Datasphere tenant.

There are several methods to authenticate to SAP Datasphere.

> ### Note:  
> Allowed authentication methods for SAP Datasphere tenants before or after the bundling with SAP Cloud Identity Services tenants feature was enabled:
> 
> -   Existing tenants: the default IdP, a custom IdP, or bundled SAP Cloud Identity Services tenants.
> -   New tenants: the default IdP or bundled SAP Cloud Identity Services tenants, which supports forwarding all SSO requests to a corporate IdP.



<a name="loio48b5c8b637a54fa491594272941855b9__section_g3r_4gm_sfc"/>

## Default Identity Provider

SAP Cloud Identity is the default authentication method for SAP Datasphere. Users can sign in to SAP Datasphere but not to other SAP products.



<a name="loio48b5c8b637a54fa491594272941855b9__section_umt_1hm_sfc"/>

## Bundled SAP Cloud Identity Services Tenants

> ### Note:  
> Bundling with SAP Cloud Identity Services tenants is being rolled out over the course of a number of versions. For more details, see SAP Note [3619907](https://me.sap.com/notes/3619907).

To allow users to sign in to your SAP Datasphere tenant and to other SAP products via single sign-on \(SSO\), you can provision an SAP Cloud Identity Services tenant for your SAP Datasphere tenant \(see [Configure Your Bundled SAP Cloud Identity Services Tenant](configure-your-bundled-sap-cloud-identity-services-tenant-fac3155.md)\). SAP Cloud Identity Services tenants support forwarding all SSO requests to a corporate IdP \(see [What Are Cloud Identity Services](https://help.sap.com/docs/IDENTITY_AUTHENTICATION/6d6d63354d1242d185ab4830fc04feb1/what-is-identity-authentication)\).



<a name="loio48b5c8b637a54fa491594272941855b9__section_rmv_1hm_sfc"/>

## \(Legacy\) Custom Identity Provider

For your SAP Datasphere tenant, you can enable single sign-on authentication to a custom IdP, which is a separate solution, for example Azure AD. For more information, see [Enabling a Custom SAML Identity Provider \(Legacy Custom IdP\)](enabling-a-custom-saml-identity-provider-legacy-custom-idp-9b26536.md).

If you are having trouble signing in, you can use the Identity Provider Administration tool to repair your custom IdP. For more information, see [Access the Identity Provider Administration Tool](access-the-identity-provider-administration-tool-df15ed8.md).

