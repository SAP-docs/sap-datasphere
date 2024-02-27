<!-- loio0cfc214f1d5f4a928700cf3715825932 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Renewing the SAP Analytics Cloud SAML Signing Certificate

To continue using SAML SSO, an administrator must renew the certificate before it expires.



## Context

An email with details on how to renew the SAML X509 certificate is sent to administrators before the certificate expiry date. If the certificate expiry is less than 30 days away, a warning message appears when you log on to SAP Datasphere.

> ### Note:  
> If you click the *Renew* link on the warning message, you're taken to the *Security* tab on the <span class="FPA-icons-V3"></span> \(*Administration*\) page.



## Procedure

1.  From the side navigation, go to <span class="FPA-icons-V3"></span> \(*System*\) → <span class="FPA-icons-V3"></span> \(*Administration*\)→ *Security*.

2.  Select *Renew*.

    A confirmation dialog appears. When you confirm the renewal, a new metadata file is automatically downloaded.

    > ### Note:  
    > The renewal process takes around five minutes to complete.

3.  If you use a custom identity provider, upload the SAP Datasphere metadata file to your SAML Identity Provider \(IdP\).

    > ### Note:  
    > This step is not required if you use SAP Cloud ID for authentication.

4.  If you have live data connections to SAP HANA systems that use SAML SSO, you must also upload the new metadata file to your SAP HANA systems.

5.  Log on to SAP Datasphere when five minutes has passed.




<a name="loio0cfc214f1d5f4a928700cf3715825932__result_rhv_ltp_t1b"/>

## Results

If you are able to log on, the certificate renewal was successful. If you cannot logon, try one of the following troubleshooting tips.

If you use SAP Cloud ID for authentication:

1.  Clear the browser cache.
2.  Allow up to five minutes for the SAP Cloud ID service to switch to the new certificate.

If you use a custom identity provider for authentication:

1.  Ensure the new metadata file has been uploaded to your IdP. For more information, see [Enabling a Custom SAML Identity Provider](enabling-a-custom-saml-identity-provider-9b26536.md).
2.  Clear the browser cache.
3.  Allow up to five minutes for your IdP to switch to the new certificate with the newly uploaded metadata.

