<!-- loiofac3155d77154775b919ceba36ffc325 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Configure Your Bundled SAP Cloud Identity Services Tenant

Provision and configure your bundled SAP Cloud Identity Services tenant to authentication to SAP Datasphere.

This topic contains the following sections:

-   [Provision an SAP Cloud Identity Services Tenant](configure-your-bundled-sap-cloud-identity-services-tenant-fac3155.md#loiofac3155d77154775b919ceba36ffc325__section_qd4_35n_sfc)
-   [Configure Authentication](configure-your-bundled-sap-cloud-identity-services-tenant-fac3155.md#loiofac3155d77154775b919ceba36ffc325__section_dns_xxn_sfc)
-   [Modify Your Authentication Setup](configure-your-bundled-sap-cloud-identity-services-tenant-fac3155.md#loiofac3155d77154775b919ceba36ffc325__section_xly_x14_sfc)
-   [Disable Your SAP Cloud Identity Services Tenant and Revert to Default IdP](configure-your-bundled-sap-cloud-identity-services-tenant-fac3155.md#loiofac3155d77154775b919ceba36ffc325__section_xrg_yqx_tfc)
-   [Disable Your SAP Cloud Identity Services Tenant and Revert to Your Custom IdP](configure-your-bundled-sap-cloud-identity-services-tenant-fac3155.md#loiofac3155d77154775b919ceba36ffc325__section_jtc_n4f_5fc)

> ### Note:  
> Bundling with SAP Cloud Identity Services tenants is being rolled out over the course of a number of versions. For more details, see SAP Note [3619907](https://me.sap.com/notes/3619907).

> ### Note:  
> If you currently use a custom IdP, we recommend that you migrate to an SAP Cloud Identity Services tenant and configure the tenant to work with your corporate IdP \(see [Forward All SSO Requests to Corporate IdP](https://help.sap.com/docs/cloud-identity-services/cloud-identity-services/forward-all-sso-requests-to-corporate-idp)\). Using SAP Cloud Identity Services to federate the identity of a custom IdP brings several benefits \(see [What Are Cloud Identity Services](https://help.sap.com/docs/IDENTITY_AUTHENTICATION/6d6d63354d1242d185ab4830fc04feb1/what-is-identity-authentication)\).

You provision and configure a bundled SAP Cloud Identity Services tenant for your SAP Datasphere tenant to allow users to sign in via single sign-on \(SSO\) to SAP Datasphere and to other SAP products that use the same SAP Cloud Identity Services tenant. For more information about bundles, see [Bundles](https://help.sap.com/docs/cloud-identity-services/cloud-identity-services/bundles).



<a name="loiofac3155d77154775b919ceba36ffc325__section_syp_ryh_vfc"/>

## Prerequisites

To configure your bundled SAP Cloud Identity Services tenant for your SAP Datasphere tenant:

-   You must have the system owner role for your SAP Datasphere tenant and have multi-factor authentication enabled \(see [Multi-Factor Authentication](https://help.sap.com/docs/cloud-identity-services/cloud-identity-services/user-guide-multi-factor-authentication?version=Cloud)\)
-   You must have a S-user with the same email as the system owner of the SAP Datasphere tenant. If you do not have an S-user, click the *Register* button and create a user with email address used by the system owner.
-   We recommend that the S-user has multi-factor authentication enabled.



<a name="loiofac3155d77154775b919ceba36ffc325__section_qd4_35n_sfc"/>

## Provision an SAP Cloud Identity Services Tenant

You can provision up to two bundled SAP Cloud Identity Services tenant roles: test and production.

1.  Sign in to the Identity Provider Administration tool \(see [Access the Identity Provider Administration Tool](access-the-identity-provider-administration-tool-df15ed8.md)\).

    All tenants that you own will appear as cards on the *My Tenants* page. Under *Current IdP*, the name and type of authentication method used will appear: default, bundled, or custom.

2.  On the tenant card that you want to bundle, select <span class="FPA-icons-V3"></span> *\+ Add SAP Cloud Identity Services.*

    All the SAP Cloud Identity Services tenants that you own will be listed.

3.  Select an existing SAP Cloud Identity Services tenant or *\+ Provision New SCI Tenant*.


    <table>
    <tr>
    <th valign="top">

    Option
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Provision a New SAP Cloud Identity Services Tenant
    
    </td>
    <td valign="top">
    
    1.  If you are provisioning a new SAP Cloud Identity Services tenant, enter information for the SAP Cloud Identity Services tenant administrator's first name, last name, and email. By default, the fields will be populated with your information, but the fields are editable in case you want to provide different information.
    2.  Click *Step 3*.

    When you provision a new tenant, its tenant role will match the tenant type used by SAP Datasphere. For example, if your SAP Datasphere tenant is a test system, the SAP Cloud Identity Services tenant will be assigned the tenant role: *Test*.

    > ### Note:  
    > This option is only available if you do not have an existing SAP Cloud Identity Services tenant with a role that matches your SAP Datasphere tenant type.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Use an Existing SAP Cloud Identity Services tenant
    
    </td>
    <td valign="top">
    
    1.  Select the SAP Cloud Identity Services tenant you want to use with the authentication bundle.
    2.  Click *Step 2*. A summary page will appear containing the tenant name, and information about the tenant administrator.

        > ### Note:  
        > If you do not already have a user on the SAP Cloud Identity Services tenant, a standard user will be created for you. A standard user does not have administration rights on the tenant, and you must request permissions from an existing administrator if you want to make changes to the tenant in the future.



    
    </td>
    </tr>
    </table>
    
4.  Select *Finish*.

    A warning will appear before provisioning begins.

5.  Select *Yes* to start the tenant provisioning.

    Tenant provisioning can take up to 1 hour to complete. A progress bar will indicate your provisioning status. It will change to a success message once the provisioning is complete.

    If you select *Close* to leave the progress dialog before it is complete, tenant provisioning will continue in the background. If you return to the *My Tenants* page, the tenant's provisioning status will appear on the tenant card. You can click the status to return to the progress bar.


You then need to configure authentication to work with your SAP Cloud Identity Services tenant.



<a name="loiofac3155d77154775b919ceba36ffc325__section_dns_xxn_sfc"/>

## Configure Authentication

As a prerequisite, an SAP Cloud Identity Services tenant must be provisioned for the selected SAP Datasphere tenant.

1.  Access the configuration dialog one of two ways:
    1.  From the SAP Cloud Identity Services tenant provisioning progress bar, select *Continue*.
    2.  From the *My Tenants* page, go to the tenant you are bundling, then select <span class="FPA-icons-V3"></span> ** \> *Configure Authentication*.

2.  Select a *User Attribute*.

    The attribute will be used to map users from your existing user list to SAP Datasphere.

    Determine what your `Subject Name Identifier` maps to in your SAP Datasphere system. It should map to *User ID*, *Email* or a custom attribute. You can view your SAP Datasphere user attributes in *Security* \> *Users*.

    > ### Note:  
    > `Subject Name Identifier` is case sensitive. The *User ID*, *Email*, or *Custom Authentication User Mapping* must match the values exactly. For example, if the `Subject Name Identifier` returned by your identity provider is `user@company.com` and the email you used in SAP Datasphere is `User@company.com` the mapping will fail.

    Choose one of the following options:

    -   *USER ID*: To map to the SAP Datasphere *User ID*.
    -   *Email*: To map to the SAP Datasphere *Email* address
    -   *Custom Authentication User Mapping*: To map to a custom value.

        > ### Note:  
        > If you select this option, there will be a new column named *SAML User Mapping* in *Security* \> *Users*. After switching to your SAML IdP, you must manually update this column for all existing users.


3.  \(Optional\) Enable *Dynamic User Creation*.

    When dynamic user creation is enabled, new users will be automatically created using the default role and will be able to sign into SAP Datasphere. After users are created, you can set roles using SAML attributes. For more information, see [Assign Users to a Role Using SAML Attributes](assign-users-to-a-role-using-saml-attributes-3315711.md).

    > ### Note:  
    > If this option is enabled, dynamic user creation still occurs in SAP Datasphere even when user attributes have not been set for all SAP Cloud Identity Services tenant users. To prevent a user from being automatically created, your SAP Cloud Identity Services tenant must deny the user access to SAP Datasphere.

4.  Click *Step 2*.

    The *Validate Login* page appears.

5.  \[Optional\] Do additional configuration in SAP Cloud Identity Services if you don't want to use the default settings.

    SAP Datasphere should appear in the *Bundled Applications* list on your SAP Cloud Identity Services tenant.

    For example, you can change the subject name identifier used by SAP Cloud Identity Services to match the attribute you selected in Step 2. You can also configure the tenant to forward authentication from SAP Cloud Identity Services to a corporate IdP. For more information, see [Forward All SSO Requests to Corporate IdP](https://help.sap.com/docs/cloud-identity-services/cloud-identity-services/forward-all-sso-requests-to-corporate-idp).

6.  Verify that you can sign in to your SAP Cloud Identity Services tenant: in another browser, sign in to the URL provided in the *Verify Your Account* dialog, using your SAP Cloud Identity Services tenant credentials.

    > ### Note:  
    > -   You can copy the URL by selecting \(*Copy*\).
    > -   You must use a private session to sign into the URL; for example, Guest mode in Google Chrome. This ensures that when you sign in to the dialog and select SAP Datasphere, you are prompted to sign in and do not reuse an existing browser session.

    If you can sign in successfully, the authentication setup is correct.

7.  On the *Validate Login* page, select *Validate Login*, then click *Step 3*.

    A summary page will appear with the system information.

8.  Select *Finish*.

    Disabling the bundled SAP Cloud Identity Services tenant can take up to 1 hour to complete. A progress bar will indicate your provisioning status. It will change to a success message once the provisioning is complete.

9.  Select *Close* to leave the progress dialog before it is complete, tenant provisioning will continue in the background. If you return to the *My Tenants* page, the tenant's provisioning status will appear on the tenant card. You can click the status to return to the progress bar.

You are taken to the *My Tenants* page, and the status of your tenant will be updated.



<a name="loiofac3155d77154775b919ceba36ffc325__section_xly_x14_sfc"/>

## Modify Your Authentication Setup

Once you have created your authentication bundle, you can change the configuration if needed.

1.  In the *My Tenants* page, go to the bundled tenant you want to modify, then select <span class="FPA-icons-V3"></span> ** \> *Configure Authentication*.
2.  In the *Select User Attribute Type* step, you can change the user attribute type, or enable dynamic user creation.
3.  Click *Step 2*.
4.  Go through steps 5-10 of the **Configure Authentication** procedure above.



<a name="loiofac3155d77154775b919ceba36ffc325__section_xrg_yqx_tfc"/>

## Disable Your SAP Cloud Identity Services Tenant and Revert to Default IdP

You can disable your bundled SAP Cloud Identity Services tenant and revert to using the default IdP.

> ### Note:  
> Users who sign in to SAP Datasphere will not be able to sign in to other SAP products via SSO.

1.  Sign in to the Identity Provider Administration tool \(see [Access the Identity Provider Administration Tool](access-the-identity-provider-administration-tool-df15ed8.md)\).
2.  In the *My Tenants* page, go to the bundled tenant you want to modify, then select <span class="FPA-icons-V3"></span>** \> *Disable Bundling*.
3.  Select *SAP Cloud Identity \(Default\)* and click *Step 2*.
4.  Select *Finish* to disable the bundle.

Disabling the bundled SAP Cloud Identity Services tenant can take up to 1 hour to complete. A progress bar will indicate your provisioning status. It will change to a success message once the provisioning is complete.

If you select *Close* to leave the progress dialog before it is complete, tenant provisioning will continue in the background. If you return to the *My Tenants* page, the tenant's provisioning status will appear on the tenant card. You can click the status to return to the progress bar.



<a name="loiofac3155d77154775b919ceba36ffc325__section_jtc_n4f_5fc"/>

## Disable Your SAP Cloud Identity Services Tenant and Revert to Your Custom IdP

You can disable your bundled SAP Cloud Identity Services tenant and revert to using your custom IdP only if your SAP Datasphere tenant that was provisioned before bundling with SAP Cloud Identity Services tenants was enabled.

To establish a trust relationship between your SAML IdP and your SAP Datasphere tenant, you'll need to exchange their metadata.

> ### Note:  
> Users who sign in to SAP Datasphere will not be able to sign in to other SAP products via SSO.

1.  Sign in to the Identity Provider Administration tool \(see [Access the Identity Provider Administration Tool](access-the-identity-provider-administration-tool-df15ed8.md)\).
2.  In the *My Tenants* page, go to the bundled tenant you want to disable, then select <span class="FPA-icons-V3"></span>** \> *Disable Bundling*.
3.  Select *SAML Single Sign-On \(SSO\)* and click *Step 2*.
4.  click *Download* and save the file, which contains the SAP Datasphere metadata.
5.  In your custom IdP, upload the file containing the SAP Datasphere metadata.
6.  Map your SAML IdP user attributes and roles.

    Configure your SAML IdP to map user attributes to the following case-sensitive allowlisted assertion attributes. We recommend that you map only the user attributes and roles that will be used in SAP Datasphere. Mapping additional user attributes may result in a large SAML assertion, which could produce a login error.


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
    > Map the `Groups` "sac" attribute under *Default Attributes* for your SAP Datasphere tenant. The remaining attributes should be mapped under *Assertion Attributes* for your SAP Datasphere tenant.

7.  In your custom IdP, download its SAML metadata in a file.
8.  In the Identity Provider Administration tool, click *Upload* and select the file containing the SAML metadata of your IdP.
9.  Click *Step 3*.
10. Select a *User Attribute*.

    The attribute will be used to map users from your existing user list to SAP Datasphere.

    Determine what your `Subject Name Identifier` maps to in your SAP Datasphere tenant. It should map to *User ID*, *Email* or a custom attribute. You can view your SAP Datasphere user attributes in *Security* \> *Users*.

    > ### Note:  
    > `Subject Name Identifier` is case sensitive. The *User ID*, *Email*, or *Custom Authentication User Mapping* must match the values exactly. For example, if the `Subject Name Identifier` returned by your identity provider is `user@company.com` and the email you used in SAP Datasphere is `User@company.com` the mapping will fail.

    Choose one of the following options:

    -   *USER ID*: To map to the SAP Datasphere *User ID*.
    -   *Email*: To map to the SAP Datasphere *Email* address
    -   *Custom Authentication User Mapping*: To map to a custom value.

        > ### Note:  
        > If you select this option, there will be a new column named *SAML User Mapping* in *Security* \> *Users*. After switching to your SAP Cloud Identity Services tenant, you must manually update this column for all existing users.


11. \[Optional\] Enable *Dynamic User Creation*.

    When dynamic user creation is enabled, new users will be automatically created using the default role and will be able to sign into SAP Datasphere. After users are created, you can set roles using SAML attributes. For more information, see [Assign Users to a Role Using SAML Attributes](assign-users-to-a-role-using-saml-attributes-3315711.md).

    > ### Note:  
    > If this option is enabled, dynamic user creation still occurs in SAP Datasphere even when user attributes have not been set for all SAP Cloud Identity Services tenant users. To prevent a user from being automatically created, your SAP Cloud Identity Services tenant must deny the user access to SAP Datasphere.

12. Click *Step 4*.

    The *Validate Login* page appears.

13. Verify that you can sign in to your custom IdP: in another browser, sign in to the URL provided in the *Verify Your Account* dialog, using your custom IdP credentials.

    > ### Note:  
    > -   You can copy the URL by selecting \(*Copy*\).
    > -   You must use a private session to sign into the URL; for example, Guest mode in Google Chrome. This ensures that when you sign in to the dialog and select SAP Datasphere, you are prompted to sign in and do not reuse an existing browser session.

    If you can sign in successfully, the authentication setup is correct.

14. On the *Validate Login* page, select *Validate Login*, then click *Step 5*.

    A summary page will appear with the system information.

15. Select *Finish*.

    Disabling the bundled SAP Cloud Identity Services tenant can take up to 1 hour to complete. A progress bar will indicate your provisioning status. It will change to a success message once the provisioning is complete.

16. Select *Close* to leave the progress dialog before it is complete, tenant provisioning will continue in the background. If you return to the *My Tenants* page, the tenant's provisioning status will appear on the tenant card. You can click the status to return to the progress bar.

