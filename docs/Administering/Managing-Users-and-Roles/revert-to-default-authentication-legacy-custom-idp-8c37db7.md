<!-- loio8c37db740bf24788a6e21ada78552d56 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Revert to Default Authentication \(Legacy Custom IdP\)

You can revert your tenant to the default authentication method.



To revert your custom IdP authentication back to the default method, you can use the *Security* page in SAP Datasphere. If you are having problems signing in, you can use the Identity Provider Administration tool.



<a name="loio8c37db740bf24788a6e21ada78552d56__section_bwk_l1p_tfc"/>

## Revert to the Default Authentication Method Using the Security Page

You can revert your custom IdP to the default authentication method directly in the *Security* page of SAP Datasphere.

1.  From the side navigation, go to <span class="FPA-icons-V3"></span> \(*System*\)→ <span class="FPA-icons-V3"></span> \(*Administration*\) → *Security*.
2.  Select <span class="FPA-icons-V3"></span> \(Edit\) .
3.  In the *Authentication Method* area, select *SAP Cloud Identity \(default\)*.

    The system will perform a check to see if all users also exist in SAP Cloud Identity.

    If users do not exist in SAP Cloud Identity, you will be prompted to *Synchronize Users*.

    A progress bar will track the status of the synchronization process.

    > ### Note:  
    > A user validation error may occur if users do not have a valid email address, or if duplicate email addresses are found. User validation errors must be corrected on the *Users* page before synchronization can be completed.

4.  Select <span class="FPA-icons-V3"></span> \(Save\) .

When conversion is complete, you will be logged out and directed to the SAP Cloud Identity logon page.



<a name="loio8c37db740bf24788a6e21ada78552d56__section_zl2_12p_tfc"/>

## Revert to the Default Authentication Method Using the Identity Provider Administration Tool

You can use the Identity Provider Administration tool to revert your tenant to the default authentication method.

1.  Sign in to the Identity Provider Administration tool. For more information, see [Access the Identity Provider Administration Tool](access-the-identity-provider-administration-tool-df15ed8.md).
2.  On the card for the tenant that you want to revert, select <span class="FPA-icons-V3"></span>** \> *Repair IdP*.
3.  Select *Revert to the Default Identity Provider*.
4.  Select the *Yes* radio button to revert to the default IdP.
5.  Select *Yes* in the confirmation dialog to revert your authentication method back to the default IdP.
6.  Click *Step 2* to proceed to the user synchronization step.
7.  Click *Synchronize Users*.

    The system will perform a check to see if all custom SAML IdP users also exist in SAP Cloud Identity. If any users do not exist in SAP Cloud Identity, you will be prompted to *Synchronize Users*. A progress bar will track the status of the synchronization process.

    > ### Note:  
    > A user validation error may occur if users do not have a valid email address, or if duplicate email addresses are found. User validation errors must be corrected before synchronization can be completed.

8.  Click *Step 3* to proceed to the validation step.
9.  Click *Log into SAP Datasphere* to open a new tab and navigate to your SAP Datasphere system. Log in with your default identity provider credentials. If you get an error saying “Your profile is not configured”, please create a support ticket under the component LOD-ANA-BI.

Once the reversion has finished, you can exit the Identity Provider Administration tool and do additional configuration in SAP Datasphere.

