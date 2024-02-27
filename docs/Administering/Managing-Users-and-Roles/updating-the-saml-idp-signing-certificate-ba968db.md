<!-- loioba968db845ed4076b5e6a1ff5a93370f -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Updating the SAML IdP Signing Certificate

You can update the SAML identity provider \(IdP\) signing certificate.



<a name="loioba968db845ed4076b5e6a1ff5a93370f__prereq_pnf_hqh_3kb"/>

## Prerequisites

-   You must have the metadata file that contains the new certificate from your custom IdP, and you must be logged into SAP Datasphere before your IdP switches over to using the new certificate.
-   You must be the System Owner in SAP Datasphere.



## Context

To upload the new metadata file, do the following:



## Procedure

1.  From the side navigation, go to <span class="FPA-icons-V3"></span> \(*System*\) → <span class="FPA-icons-V3"></span> \(*Administration*\) →*Security* .

    If you've provisioned SAP Datasphere prior to version 2020.03 you'll see a different UI and need go to <span class="FPA-icons-V3"></span> \(*My Products*\) → <span class="FPA-icons-V3"></span> \(*Analytics*\) → <span class="FPA-icons-V3"></span> \(*System*\) → <span class="FPA-icons-V3"></span> \(*Administration*\) → *Security*.

2.  Select <span class="FPA-icons-V3"></span> \(Edit\) 

3.  Under *Step 2*, select *Update* and provide the new metadata file.

4.  Select <span class="FPA-icons-V3"></span> \(Save\) and confirm the change to complete the update.

    The update will take effect within two minutes.




<a name="loioba968db845ed4076b5e6a1ff5a93370f__result_fhg_sqh_3kb"/>

## Results

> ### Note:  
> You do not have to redo *Step 3* or *Step 4* on the *Security* tab.

