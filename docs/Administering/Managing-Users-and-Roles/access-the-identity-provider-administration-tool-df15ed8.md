<!-- loiodf15ed86297f436b89135e4132e665c7 -->

# Access the Identity Provider Administration Tool

The Identity Provider Administration tool allows system owners to manage the identity provider configured with SAP Datasphere. Through the tool, the system owner can create or modify an authentication bundle, choose to upload new metadata for a custom identity provider, or revert to using the default identity provider.



<a name="loiodf15ed86297f436b89135e4132e665c7__prereq_jbj_4mm_hkb"/>

## Prerequisites

> ### Note:  
> Bundling with SAP Cloud Identity Services tenants is being rolled out over the course of a number of versions. For more details, see SAP Note [3619907](https://me.sap.com/notes/3619907).

To configure your bundled SAP Cloud Identity Services tenant for your SAP Datasphere tenant:

-   You must have the system owner role for your SAP Datasphere tenant and have multi-factor authentication enabled \(see [Multi-Factor Authentication](https://help.sap.com/docs/cloud-identity-services/cloud-identity-services/user-guide-multi-factor-authentication?version=Cloud)\)
-   You must have a S-user with the same email as the system owner of the SAP Datasphere tenant. If you do not have an S-user, click the *Register* button and create a user with email address used by the system owner.
-   We recommend that the S-user has multi-factor authentication enabled.



## Procedure

1.  Access the *Identity Provider Administration* tool using the following URL: `https://console.<data center>.sapanalytics.cloud/idp-admin/`

    For example, if your SAP Datasphere system is on eu10, then the URL is:

    `https://console.eu10.sapanalytics.cloud/idp-admin/`

    If your SAP Datasphere system is on cn1, then the URL is:

    `https://console.cn1.sapanalyticscloud.cn/idp-admin/`

    If your tenant is on EUDP:

    `https://console-eudp.eu1.sapanalytics.cloud/idp-admin/`

    `https://console-eudp.eu2.sapanalytics.cloud/idp-admin/`

2.  Log in with an S-user that has the same email address as the system owner of SAP Datasphere tenant. If you don't yet have such an S-user, you can click the *Register* button and create a P-user.

    If you create a new P-user, you'll receive an email with an activation link that will let you set your password.

3.  Once you're signed in, the list of SAP Datasphere tenants for which you are the system owner is displayed. Select the tenant you want to work on by clicking on the card.

    > ### Note:  
    > Your SAP Datasphere tenant is connected to the Identity Provider Administration tool by default. If you'd like to disconnect your tenant from the console, you can do so in either of two places:
    > 
    > -   In SAP Datasphere, navigate to *System* \> *Administration* \> *Security* \> *Optional: Configure Identity Provider Administration Tool*, click the *Connected* switch, and then save the changes.
    > -   Click *Disconnect IdP Admin from your system* after selecting your tenant in the Identity Provider Administration tool.


