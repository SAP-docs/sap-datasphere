<!-- loio9b26536159354aea9024a99cbbe60b4e -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Enabling a Custom SAML Identity Provider \(Legacy Custom IdP\)

By default, SAP Cloud Identity is used by SAP Datasphere. SAP Datasphere also supports single sign-on \(SSO\), using your custom identity provider.



<a name="loio9b26536159354aea9024a99cbbe60b4e__prereq_hps_jsh_3kb"/>

## Prerequisites

To enable and configure your custom identity provider for your SAP Datasphere tenant:

-   You must have an IdP that supports SAML 2.0 protocol.
-   You must be able to configure your IdP.
-   You must have the system owner role for your SAP Datasphere tenant.
-   If your users are connecting from Apple devices using the mobile app, the certificate used by your IdP must be compatible with Apple's App Transport Security \(ATS\) feature.

> ### Note:  
> SAP Datasphere is hosted on non-SAP data centers.



<a name="loio9b26536159354aea9024a99cbbe60b4e__context_axs_j3w_tfc"/>

## Context

A custom identity provider is a separate solution, like for example Azure AD, and is not part of SAP Analytics Cloud or SAP Datasphere. Therefore the change in configuration is to be applied directly in the solution, not within SAP Datasphere. No access to SAP Datasphere is required to make the change, only an access to the IdP.

> ### Note:  
> Be aware that the SAML attributes for SAP Datasphere roles do not cover user assignment to spaces. A user who logs into a SAP Datasphere tenant through SSO must be assigned to the space in order to access the space. If you do not assign a user to a space, the user will not have access to any space.



<a name="loio9b26536159354aea9024a99cbbe60b4e__steps_ips_jsh_3kb"/>

## Procedure

1.  From the side navigation, go to <span class="FPA-icons-V3"></span> \(*System*\) → <span class="Belize-icons"></span> \(*Administration*\) →*Security*.

2.  Select <span class="FPA-icons-V3"></span> \(Edit\).

3.  In the *Authentication Method* area, select *SAML Single Sign-On \(SSO\)* if it is not already selected.

    > ### Note:  
    > By default, SAP Cloud Identity is used for authentication.

4.  In *Step 1*, select *Download* and save the metadata file.

    A SAP Datasphere metadata file is saved.

5.  Upload the SAP Datasphere metadata file to your SAML IdP.

    If you are creating a new SAP Datasphere application on the Identity Authentication Service \(IAS\) side with the type "unknown", set the type to "Unknown".

    The file includes metadata for SAP Datasphere, and is used to create a trust relationship between your SAML Identity Provider and your SAP Datasphere system.

6.  Map your SAML IdP user attributes and roles.

    Configure your SAML IdP to map user attributes to the following case-sensitive allowlisted assertion attributes. We recommend that you map only the user attributes and roles that will be used in SAP Analytics Cloud. Mapping additional user attributes may result in a large SAML assertion, which could produce a login error.


    <table>
    <tr>
    <th valign="top">

    Attribute Name
    
    </th>
    <th valign="top">

    Notes
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    email
    
    </td>
    <td valign="top">
    
    Required if your `NameID` is "email".
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Groups
    
    </td>
    <td valign="top">
    
    Required. The value must be set to "sac", even in case of SAP Datasphere. The Groups attribute is a custom attribute and must be added if it does not exist yet. You need to contact your administrator to get the path where the mapping needs to be changed.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    familyName
    
    </td>
    <td valign="top">
    
    Optional. `familyName` is the user's last name \(surname\).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    displayName
    
    </td>
    <td valign="top">
    
    Optional.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    functionalArea
    
    </td>
    <td valign="top">
    
    Optional.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    givenName
    
    </td>
    <td valign="top">
    
    Optional. `givenName` is the user's first name.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    preferredLanguage
    
    </td>
    <td valign="top">
    
    Optional.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    custom1
    
    </td>
    <td valign="top">
    
    Optional. For SAML role assignment.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    custom2
    
    </td>
    <td valign="top">
    
    Optional. For SAML role assignment.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    custom3
    
    </td>
    <td valign="top">
    
    Optional. For SAML role assignment.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    custom4
    
    </td>
    <td valign="top">
    
    Optional. For SAML role assignment.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    custom5
    
    </td>
    <td valign="top">
    
    Optional. For SAML role assignment.
    
    </td>
    </tr>
    </table>
    
    Example of SAML assertion:

    ```
    <AttributeStatement>
                <Attribute
                    Name="email">
                    <AttributeValue>abc.def@mycompany.com</AttributeValue>
                </Attribute>
                <Attribute
                    Name="givenName">
                    <AttributeValue>Abc</AttributeValue>
                </Attribute>
                <Attribute
                    Name="familyName">
                    <AttributeValue>Def</AttributeValue>
                </Attribute>
                <Attribute
                    Name="displayName">
                    <AttributeValue>Abc Def</AttributeValue>
                </Attribute>
                <Attribute
                    Name="Groups">
                    <AttributeValue>sac</AttributeValue>
                </Attribute>
                <Attribute
                    Name="custom1">
                    <AttributeValue>Domain Users</AttributeValue>
                    <AttributeValue>Enterprise Admins</AttributeValue>
                    <AttributeValue>Enterprise Key Admins</AttributeValue>
                </Attribute>
            </AttributeStatement>
    
    ```

    > ### Note:  
    > If you are using the SAP Cloud Identity Authentication service as your IdP, map the `Groups` "sac" attribute under *Default Attributes* for your SAP Datasphere tenant. The remaining attributes should be mapped under *Assertion Attributes* for your SAP Datasphere tenant.

7.  Download metadata from your SAML IdP.

8.  In *Step 2*, select *Upload*, and choose the metadata file you downloaded from your SAML IdP.

9.  In *Step 3*, select a *User Attribute*.

    The attribute will be used to map users from your existing SAML user list to SAP Datasphere`NameID` used in your custom SAML assertion:

    ```
    <NameID Format="urn:oasis:names:tc:SAML:1.1:nameid-format:unspecified"><Your Unique Identifier></NameID>
    ```

    Determine what your `NameID` maps to in your SAP Datasphere system. It should map to . The user attribute you select must match the *User ID*, *Email* or a custom attribute. You can view your SAP Datasphere user attributes in *Security* \> *Users*.

    > ### Note:  
    > `NameID` is case sensitive. The *User ID*, *Email*, or *Custom SAML User Mapping* must match the values in your SAML IdP exactly. For example, if the `NameId` returned by your SAML IdP is `user@company.com` and the email you used in SAP Datasphere is `User@company.com` the mapping will fail.

    Choose one of the following options:

    -   *USER ID*: If `NameID` maps to the SAP Datasphere *User ID*.
    -   *Email*: If `NameID` maps to SAP Datasphere *Email* address.

        > ### Note:  
        > If your `NameID` email is not case-sensitive and contains mixed-case, for example `User@COMPANY.com`, consider choosing *Custom SAML User Mapping* instead.

    -   *Custom SAML User Mapping*: If `NameID` maps to a custom value.

        > ### Note:  
        > If you select this option, there will be a new column named *SAML User Mapping* in *Security* \> *Users*. The. After switching to your SAML IdP, you must manually update this column for all existing users.


    > ### Note:  
    > If you are using a live connection to SAP S/4HANA Cloud Edition with *OAuth 2.0 SAML Bearer Assertion*, `NameId` must be identical to the user name of the business user on your SAP S/4HANA system.
    > 
    > For example, if you want to map an SAP Datasphere user with the user ID `SACUSER` to your SAP S/4HANA Cloud user with the user name `S4HANAUSER`, you must select *Custom SAML User Mapping* and use `S4HANAUSER` as the *Login Credential* in Step 10.
    > 
    > If you are using SAP Cloud Identity as your SAML IdP, you can choose *Login Name* as the *NameID* attribute for SAP Datasphere, then you can set the login name of your SAP Datasphere user as `S4HANAUSER`.

10. \[Optional\] Enable *Dynamic User Creation*.

    When dynamic user creation is enabled, new users will be automatically created and assigned the default role and will be able to use SAML SSO to log onto SAP Datasphere. Once the users are created, you can assign roles using SAML attributes \(see [Assign Users to a Role Using SAML Attributes](assign-users-to-a-role-using-saml-attributes-3315711.md)\).

    > ### Note:  
    > Automatic user deletion is not supported. If a user in SAP Datasphere is removed from your SAML IdP, you must go to *Security* \> *Users* and manually delete users. For more information, see [Delete a User](delete-a-user-3ceb94c.md).
    > 
    > If this option is enabled, dynamic user creation still occurs in SAP Datasphere even when SAML user attributes have not been set for all IdP users. To prevent a user from being automatically created, your SAML IdP must deny the user access to SAP Datasphere.

11. In *Step 4*, enter *<Your Unique Identifier\>*.

    This value must identify the SAP Datasphere system owner. The *Login Credential* provided here are automatically set for your user.

    > ### Note:  
    > The *Login Credential* depends on the *User Attribute* you selected under *Step 3*.

12. Test the SAML IdP setup, by logging in with your IdP, and then clicking *Verify Account* to open a dialog for validation.

    In another browser, log on to the URL provided in the *Verify Your Account* dialog, using your SAML IdP credentials. You can copy the URL by selecting <span class="FPA-icons-V3"></span> \(Copy\).

    You must use a private session to log onto the URL; for example, guest mode in Chrome. This ensures that when you log on to the dialog and select SAP Datasphere, you are prompted to log in and do not reuse an existing browser session.

    > ### Note:  
    > When starting the verification step, you will see a new screen when logging into SAP Datasphere. Two links will be displayed on this page. One will link to your current IdP and the other will link to the new IdP you will switch to. To perform the *Verify Account* step, use the link for the new IdP. Other SAP Datasphere users can continue logging on with the current IdP. Once you have completed Step 16 and the IdP switch has completed, this screen will no longer appear.

    If you can log on successfully, the SAML IdP setup is correct.

13. In the *Verify Your Account* dialog, select *Check Verification*.

    If the verification was successful, a green border should appear around the *Login Credential* box.

14. \[Optional\] Enter a password management URL.

    The URL should link to the password management page of your SAML IdP.

15. \[Optional\] Configure the logout by choosing one of the following logout options:

    -   *IdP Logout*: Log out of your SAML IdP.
    -   *Application log out*: Log out of SAP Datasphere and remain signed in to your IdP system.

    > ### Note:  
    > By default, when users log out of SAP Datasphere, they are automatically logged out of their SAML IdP.

16. Select <span class="FPA-icons-V3"></span> \(Save\).

    The *Convert to SAML Single Sign-On* confirmation dialog will appear.

17. Select *Convert*.

    When the conversion is complete, you will be logged out and directed to the logon page of your SAML IdP.

18. Log on to SAP Datasphere with the credentials you used for the verification step.

19. From the side navigation, go to <span class="FPA-icons-V3"></span> \(*Security*\) → and <span class="FPA-icons-V3"></span> \(*Users*\), look for the <span class="FPA-icons-V3"></span> column of the *User Attribute* you selected in step 9.

    The values in this column should be a case sensitive match with the `NameId` sent by your IdP's SAML assertion.

    > ### Note:  
    > If you selected *Custom SAML User Mapping* as *User Attribute*, you must manually update all fields in the *SAML User Mapping* column.




<a name="loio9b26536159354aea9024a99cbbe60b4e__result_jps_jsh_3kb"/>

## Results

Users will be able to use SAML SSO to log onto SAP Datasphere.

> ### Note:  
> You can also set up your IdP with your Public Key Infrastructure \(PKI\) so that you can automatically log in your users with a client side X.509 certificate.



<a name="loio9b26536159354aea9024a99cbbe60b4e__postreq_l1p_xnv_2fb"/>

## Next Steps

Switching to a Different Custom IdP: If SAML SSO is enabled and you would like to switch to a different SAML IdP, you can repeat the above steps using the new SAML IdP metadata.

