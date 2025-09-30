<!-- loioba968db845ed4076b5e6a1ff5a93370f -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Update SAML Signing Certificates \(Legacy Custom IdP\)

If you are using a custom IdP for authentication, you may need to update your SAML IdP signing certificate.



A common use case is to upload new SAML metadata from your identity provider when a new signing certificate has been generated.

If you can't sign in to SAP Datasphere you can use the Identity Provider Administration tool to upload new SAML metadata or download your tenant signing certificate.



<a name="loioba968db845ed4076b5e6a1ff5a93370f__section_s5m_fdb_4gc"/>

## Prerequisites

You must have the IdP SAML metadata .xml file that contains the new signing certificate.



<a name="loioba968db845ed4076b5e6a1ff5a93370f__section_j2v_qgj_tfc"/>

## Update the IdP SAML Metadata with a New Signing Certificate Using the Security Page

Upload a new SAML metadata .xml file, which contains a new signing certificate, to reconfigure trust between your custom IdP and your SAP Datasphere system.

1.  From the side navigation, go to <span class="FPA-icons-V3"></span> \(*System*\) → <span class="FPA-icons-V3"></span> \(*Administration*\) →*Security* .
2.  Select <span class="FPA-icons-V3"></span> \(Edit\).
3.  Under *Step 2*, select *Update* and provide the new SAML metadata file.
4.  Select <span class="FPA-icons-V3"></span> \(Save\) and confirm the change to complete the update.

    The update will take effect within a few minutes.




<a name="loioba968db845ed4076b5e6a1ff5a93370f__section_qcb_cjj_tfc"/>

## Update the IdP SAML Metadata with a New Signing Certificate Using the Identity Provider Administration Tool

Upload a new SAML metadata .xml file, which contains a new signing certificate, to reconfigure trust between your custom IdP and your SAP Datasphere system, using the Identity Provider Administration tool.

1.  Sign in to the Identity Provider Administration tool \(see [Access the Identity Provider Administration Tool](access-the-identity-provider-administration-tool-df15ed8.md)\).
2.  On the card for the tenant that you want to update, select <span class="FPA-icons-V3"></span>** \> *Repair IdP*.
3.  Select *Upload new metadata for the current custom identity provider*.
4.  Click *Browse* to select the new SAML metadata .xml file for your current custom identity provider.
5.  Click *Upload File* to upload the provided metadata file. After the upload is successful, it can take up to five minutes for the new metadata file to be applied.
6.  Click *Step 3* to proceed to the validation step.
7.  Click *Log into SAP Datasphere* to open a new tab and navigate to your SAP Datasphere system.

If you have any sign in problems related to the identity provider configuration, as opposed to a user-specific problem, you can return to the Identity Provider Administration tool and either re-upload the metadata file or revert to the default identity provider. For more information, see [Revert to Default Authentication \(Legacy Custom IdP\)](revert-to-default-authentication-legacy-custom-idp-8c37db7.md).



<a name="loioba968db845ed4076b5e6a1ff5a93370f__section_pw5_sjj_tfc"/>

## Reacquire the SAP Datasphere SAML Metadata File with a Signing Certificate Using the Identity Provider Administration Tool

If you need to reacquire your system metadata, it can be downloaded from the Identity Provider Administration tool.

1.  Sign in to the Identity Provider Administration tool \(see [Access the Identity Provider Administration Tool](access-the-identity-provider-administration-tool-df15ed8.md)\).
2.  On the card for the tenant that you want to use, select <span class="FPA-icons-V3"></span>** \> *Repair IdP*.
3.  Select *Download* to get the SAP Datasphere metadata.

