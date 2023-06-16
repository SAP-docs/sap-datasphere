<!-- loiodf15ed86297f436b89135e4132e665c7 -->

# Identity Provider Administration

The Identity Provider Administration tool allows system owners to manage the custom identity provider configured with SAP Datasphere. Through the tool, the system owner can choose to upload new metadata for the current custom identity provider, or revert to using the default identity provider.



<a name="loiodf15ed86297f436b89135e4132e665c7__prereq_jbj_4mm_hkb"/>

## Prerequisites

-   SAP Datasphere must already be configured to use a custom identity provider.
-   You must be the system owner.



## Procedure

1.  Access the *Identity Provider Administration* tool using the following URL pattern:

    `https://console.<data center>.sapanalytics.cloud/idp-admin/`

    For example, if your SAP Datasphere system is on eu10, then the URL is:

    `https://console.eu10.sapanalytics.cloud/idp-admin/`

    If your SAP Datasphere system is on cn1, then the URL is:

    `https://console.cn1.sapanalyticscloud.cn/idp-admin/`

    If your tenant is on EUDP:


    <table>
    <tr>
    <td valign="top">
    
        https://console-eudp.eu1.sapanalytics.cloud/idp-admin/


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
        https://console-eudp.eu2.sapanalytics.cloud/idp-admin/


    
    </td>
    </tr>
    </table>
    
2.  Log in with an S-user that has the same email address as the system owner of your system. If you don't yet have such an S-user, you can click the “Register” button and create a P-user.

    If you create a new P-user, you'll receive an email with an activation link that will let you set your password.

3.  Once you're logged in, you'll see a list of SAP Datasphere systems for which you are the system owner.

    Select the system you want to work on by clicking on its row.

    Once you're in the settings page for your system, you can see information about your current custom identity provider. If you need to reacquire your system's metadata, you can click the “Service Provider Metadata Download” link.

    If you don't want to manage your custom identity provider through Identity Provider Administration, you can disconnect your system by clicking “Disconnect IdP Admin from your system”.

4.  To proceed with either reverting to the default identity provider or updating the current custom identity provider, select the corresponding radio button and then click “Step 2”.

    > ### Note:  
    > Your SAP Datasphere system is connected to the Identity Provider Administration tool by default. The connection status for your system is displayed under the “Status” column of the systems list page. If you'd like to disconnect your system from the console, you can do so in either of two places:
    > 
    > -   In SAP Datasphere, navigate to *System* \> *Administration* \> *Security* \> *Optional: Configure Identity Provider Administration Tool*, click the *Connected* switch, and then save the changes.
    > -   Click “Disconnect IdP Admin from your system” after selecting your system in Identity Provider Administration.

5.  \(Optional\) Revert to the default identity provider.

    Choose this option if you're having problems logging in with your custom identity provider and would like to revert to the default identity provider. Once the reversion has finished, you can exit the Identity Provider Administration tool and log in to your SAP Datasphere system to reconfigure your custom identity provider.

    1.  Select the “Yes” radio button to revert to the default IdP.

    2.  Select “Yes” in the confirmation dialog to revert your authentication method back to the default IdP.

    3.  Click “Step 3” to proceed to the validation step.

    4.  Click “Log into SAP Datasphere” to open a new tab and navigate to your system. Log in with your default identity provider credentials. If you get an error saying “Your profile is not configured”, please create a support ticket under the component LOD-ANA-BI.


6.  \(Optional\) Upload new metadata for the current custom identity provider.

    Choose this option if you need to reconfigure trust between your custom identity provider and your SAP Datasphere system. A common use case is to upload new metadata from your identity provider when a new signing certificate has been generated.

    1.  Click “Browse” to select the new metadata file for your current custom identity provider.

    2.  Click “Upload File” to upload the provided metadata file. After the upload is successful, it can take up to five minutes for the new metadata file to be applied.

    3.  Click “Step 3” to proceed to the validation step.

    4.  Click “Log into SAP Datasphere” to open a new tab and navigate to your system. If you have any login problems related to the identity provider configuration, as opposed to a user-specific problem, you can return to the Identity Provider Administration tool and either re-upload the metadata file or revert to the default identity provider.



