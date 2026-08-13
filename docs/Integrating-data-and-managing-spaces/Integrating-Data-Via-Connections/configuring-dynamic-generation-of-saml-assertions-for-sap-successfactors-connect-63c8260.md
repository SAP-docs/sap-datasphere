<!-- loio63c8260a7f574e6e8e3c386656c93b00 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Configuring Dynamic Generation of SAML Assertions for SAP SuccessFactors Connections

Configure automated, dynamic generation and rotation of Security Assertion Markup Language \(SAML\) assertions for accessing SAP SuccessFactors APIs. For the generation of SAML assertions, SAP Datasphere is using the Identity Authentication service of SAP Cloud Identity Services as identity provider. Configuration steps are required in Identity Authentication and SAP SuccessFactors.

This topic contains the following sections:

-   [Prerequisites](configuring-dynamic-generation-of-saml-assertions-for-sap-successfactors-connect-63c8260.md#loio63c8260a7f574e6e8e3c386656c93b00__prerequisites)
-   [Context](configuring-dynamic-generation-of-saml-assertions-for-sap-successfactors-connect-63c8260.md#loio63c8260a7f574e6e8e3c386656c93b00__context)
-   [Step 1: Register Identity Authentication as OAuth2 Client Application in SAP SuccessFactors](configuring-dynamic-generation-of-saml-assertions-for-sap-successfactors-connect-63c8260.md#loio63c8260a7f574e6e8e3c386656c93b00__register_client_in_SAPSF)
-   [Step 2: Create and configure an OpenID Connect \(OIDC\) Application in Identity Authentication](configuring-dynamic-generation-of-saml-assertions-for-sap-successfactors-connect-63c8260.md#loio63c8260a7f574e6e8e3c386656c93b00__OICS_application)
-   [Step 3: Create and Configure a SAML 2.0 Application in Identity Authentication](configuring-dynamic-generation-of-saml-assertions-for-sap-successfactors-connect-63c8260.md#loio63c8260a7f574e6e8e3c386656c93b00__SAML_application)
-   [Results](configuring-dynamic-generation-of-saml-assertions-for-sap-successfactors-connect-63c8260.md#loio63c8260a7f574e6e8e3c386656c93b00__results)



<a name="loio63c8260a7f574e6e8e3c386656c93b00__prerequisites"/>

## Prerequisites

You require:

-   Administrator access to your SAP SuccessFactors tenant
-   Administrator access to your SAP Cloud Identity Services tenant
-   A user provisioned in both SAP Cloud Identity Services and SAP SuccessFactors where the *Login Name* configured in the user details in SAP Cloud Identity Services user management matches the user name entered in the USERNAME field for the SAP SuccessFactors user.

    To add the SAP SuccessFactors user name to the *Login Name* field in the SAP Cloud Identity Services user details, perform the following steps:

    1.  In the *Administration Console* for your SAP Cloud Identity Services tenant, navigate to *Users & Authorizations* \> *User Management*.
    2.  Search for the user in Identity Authentication that you want to use for the dynamic SAML assertion generation workflow.

        > ### Note:  
        > This user does not require any permissions and can be a freshly created user.

    3.  Click the user to open the *Details* section.
    4.  In the *Details* section, under *Login Name*, enter the SAP SuccessFactors user name \(the name in the USERNAME field which is used to log into SAP SuccessFactors\) and save your changes.

        > ### Note:  
        > Because of your subject name identifier configuration in the SAML 2.0 application, Identity Authentication sends the user's login name to the application as NameID in SAML 2.0 assertions \(within a SAML assertion NameID is used to uniquely identify the authenticated user\). Therefore, the login name, you enter here, must match the SAP SuccessFactors user name \(USERNAME field\).





<a name="loio63c8260a7f574e6e8e3c386656c93b00__context"/>

## Context

The required configuration steps involve:

-   Registering Identity Authentication as OAuth2 Client application in SAP SuccessFactors
-   Configurations in Identity Authentication - this technically requires creating two applications for SAP SuccessFactors which then need to be integrated via defining a dependency: an OpenID Connect \(OIDC\) application and a SAML 2.0 application.



<a name="loio63c8260a7f574e6e8e3c386656c93b00__register_client_in_SAPSF"/>

## Step 1: Register Identity Authentication as OAuth2 Client Application in SAP SuccessFactors

1.  Obtain the Identity Authentication signing certificate:
    1.  In the *Administration Console* for your SAP Cloud Identity Services tenant, navigate to *Applications & Resources* \> *Tenant Settings* \> *Single Sign-On* \> *SAML 2.0 Configuration* \> *Signing Certificates*.
    2.  In the *Action* column for the active valid certificate, click <span class="SAP-icons-V5"></span> \(View Certificate Details\) to view the certificate.
    3.  Copy the *Certificate Information* and keep it for later.

2.  Register your OAuth2 client application in SAP SuccessFactors.
    1.  In the *Admin Center* of your SAP SuccessFactors tenant, use the search on the *Tools* tile to navigate to *Manage OAuth2 Client Applications* \> *Register Client Application*.
    2.  Complete the following properties:


        <table>
        <tr>
        <th valign="top">

        Property
        
        </th>
        <th valign="top">

        Description
        
        </th>
        </tr>
        <tr>
        <td valign="top">
        
        *Company*
        
        </td>
        <td valign="top">
        
        Enter your SAP SuccessFactors company ID. This value is prefilled based on the instance of the company currently logged in.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *Application Name*
        
        </td>
        <td valign="top">
        
        Enter a unique name of your OAuth client, for example `DSP_SAML`
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *Application URL*
        
        </td>
        <td valign="top">
        
        Enter your SAP SuccessFactors tenant URL, for example <code>https://<i class="varname">&lt;sf-host&gt;</i>.successfactors.com/</code>.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *Bind to Users*
        
        </td>
        <td valign="top">
        
        Select this option if you want to restrict the access of the application to specific users.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *User IDs*
        
        </td>
        <td valign="top">
        
        \[Required if you selected the *Bind to User* option\] Enter the user that has been provisioned in both SAP Cloud Identity Services and SAP SuccessFactors.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *X.509 Certificate*
        
        </td>
        <td valign="top">
        
        Enter the certificate that you have copied from SAP Cloud Identity Services in step 1.1.c.
        
        </td>
        </tr>
        </table>
        
    3.  Click *Register*. The new application appears on the list of your OAuth2 client applications.
    4.  In the *Action* column for your application, click *View*, copy the *API Key* and keep it for later.


For more information, see [Registering Your OAuth2 Client Application](https://help.sap.com/viewer/d599f15995d348a1b45ba5603e2aba9b/latest/en-US/6b3c741483de47b290d075d798163bc1.html) in the *SAP SuccessFactors Platform* documentation.



<a name="loio63c8260a7f574e6e8e3c386656c93b00__OICS_application"/>

## Step 2: Create and configure an OpenID Connect \(OIDC\) Application in Identity Authentication

1.  In the *Administration Console* for your SAP Cloud Identity Services tenant, navigate to *Applications & Resources* \> *Applications* and click *Create*.
2.  In the *Create Application* dialog, complete the following properties:


    <table>
    <tr>
    <th valign="top">

    Property
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Display Name*
    
    </td>
    <td valign="top">
    
    Enter the name of the application, for example `OIDCTOKEN`. This name appears on the logon and registration pages.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Home URL*
    
    </td>
    <td valign="top">
    
    not required
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Type*
    
    </td>
    <td valign="top">
    
    Select *SAP SuccessFactors solution*.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Parent Application*
    
    </td>
    <td valign="top">
    
    Keep the default \(*None*\).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Organization ID*
    
    </td>
    <td valign="top">
    
    Keep the default \(*global*\).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Protocol*
    
    </td>
    <td valign="top">
    
    Select *OpenID Connect*.
    
    </td>
    </tr>
    </table>
    
3.  Click *Create*. The new application appears on the list of the applications.

    For more information about creating OIDC applications, see [Create OpenID Connect \(OIDC\) Application](https://help.sap.com/docs/cloud-identity-services/cloud-identity-services/create-openid-connect-application?version=Cloud) in the *SAP Cloud Identity Services* documentation.

4.  Configure the grant types for your application:

    1.  Select your application from the list.
    2.  On the *Trust* tab, under *Single Sign-On*, click *OpenID Connect Configuration*.
    3.  In the *OpenID Connect Configuration* section, select the following grant types:
        -   *Password* \(Resource Owner Password Credentials Flow\)
        -   *JWT Bearer*
        -   *Refresh*
        -   *Client Credentials*
        -   *Token Exchange \(RFC 8693\)*

    4.  Save your selection.

    For more information, see [Configure Grant Types](https://help.sap.com/docs/cloud-identity-services/cloud-identity-services/configure-grant-types?version=Cloud) in the *SAP Cloud Identity Services* documentation.

5.  Create a client secret:
    1.  On the *Trust* tab of your application, under *Application APIs*, click *Client Authentication*.
    2.  In the *Client Authentication* section, go to *Secrets* and click *Add*.
    3.  In the dialog, complete the following properties:


        <table>
        <tr>
        <th valign="top">

        Property
        
        </th>
        <th valign="top">

        Description
        
        </th>
        </tr>
        <tr>
        <td valign="top">
        
        *Description*
        
        </td>
        <td valign="top">
        
        Enter a description.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *Expire in*
        
        </td>
        <td valign="top">
        
        Select the expiry according to your policy.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *API Access*
        
        </td>
        <td valign="top">
        
        Select *Open ID*.
        
        </td>
        </tr>
        </table>
        
    4.  Click *Save* and make sure to copy the *Client ID* and *Client Secret* from the following dialog.

        > ### Note:  
        > Once you close the dialog, client ID and secret are no longer available.





<a name="loio63c8260a7f574e6e8e3c386656c93b00__SAML_application"/>

## Step 3: Create and Configure a SAML 2.0 Application in Identity Authentication

> ### Note:  
> Do not reuse the existing bundled SAP SuccessFactors application. Instead, create a separate application with specific settings

1.  In the *Administration Console* for your SAP Cloud Identity Services tenant, navigate to *Applications & Resources* \> *Applications* and click *Create*.
2.  In the *Create Application* dialog, complete the following properties:


    <table>
    <tr>
    <th valign="top">

    Property
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Display Name*
    
    </td>
    <td valign="top">
    
    Enter the name of the application, for example `SF_SAML`. This name appears on the logon and registration pages.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Home URL*
    
    </td>
    <td valign="top">
    
    not required
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Type*
    
    </td>
    <td valign="top">
    
    Select *SAP SuccessFactors solution*.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Parent Application*
    
    </td>
    <td valign="top">
    
    Keep the default \(*None*\).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Organization ID*
    
    </td>
    <td valign="top">
    
    Keep the default \(*global*\).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Protocol*
    
    </td>
    <td valign="top">
    
    Select *SAML 2.0*.
    
    </td>
    </tr>
    </table>
    
3.  Click *Create*. The new application appears on the list of the applications.

    For more information about creating SAML 2.0 applications, see [Create SAML 2.0 Application](https://help.sap.com/docs/cloud-identity-services/cloud-identity-services/create-saml-2-0-application?version=Cloud) in the *SAP Cloud Identity Services* documentation.

4.  Configure SAML 2.0 for the application:

    1.  Select your application from the list.
    2.  On the *Trust* tab, under *Single Sign-On*, click *SAML 2.0 Configuration*.
    3.  In the *SAML 2.0 Configuration*, click *Configure Manually* to create a new trust configuration.
    4.  In the following dialog, enter any value in the *Entity ID* field and click *Add*.
    5.  In the *SAML 2.0 Configuration* section, under *Endpoints* \> *Single Sign-On* click *Create*, enter the token endpoint in the format <code>https://<i class="varname">&lt;SAP SuccessFactors API endpoint&gt;</i>/oauth/token</code> and save your configuration.

        For more information, see [List of SAP SuccessFactors API Servers](https://help.sap.com/docs/successfactors-platform/sap-successfactors-api-reference-guide-odata-v2/list-of-sap-successfactors-api-servers) in the *SAP SuccessFactors Platform* documentation.


    For more information, see [Make a New Trust Configuration](https://help.sap.com/docs/cloud-identity-services/cloud-identity-services/configure-saml-2-0-service-provider-7cecbdf34f7f4ed5ba294d80bb0be075?version=Cloud) in the *SAP Cloud Identity Services* documentation.

5.  Configure the subject name identifier which is used by the application to uniquely identify the user during logon \(Identity Authentication sends the attribute to the application as name ID in SAML 2.0 assertions\):

    1.  On the *Trust* tab of your application, under *Single Sign-On*, click *Subject Name Identifier*.
    2.  In the *Subject Name Identifier* section, complete the following properties and save your configuration:


        <table>
        <tr>
        <th valign="top">

        Property
        
        </th>
        <th valign="top">

        Description
        
        </th>
        </tr>
        <tr>
        <td valign="top">
        
        *Primary Attribute* \> *Source*
        
        </td>
        <td valign="top">
        
        Select *Identity Directory*.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *Primary Attribute* \> *Value*
        
        </td>
        <td valign="top">
        
        Select *Login Name*.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *Fallback Attribute* \> *Source*
        
        </td>
        <td valign="top">
        
        Displays *Identity Directory*.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *Fallback Attribute* \> *Value*
        
        </td>
        <td valign="top">
        
        Select *None*.
        
        </td>
        </tr>
        </table>
        

    For more information, see [Configure the Subject Name Identifier Sent to the Application](https://help.sap.com/docs/cloud-identity-services/cloud-identity-services/configure-subject-name-identifier-sent-to-application?version=Cloud) in the *SAP Cloud Identity Services* documentation.

6.  Configure the user attributes needed by the application:

    1.  On the *Trust* tab of your application, under *Single Sign-On*, click *Attributes*.
    2.  In the *Attributes* section, under *Self-defined Attributes*, configure the attributes and save your configuration:
        1.  Delete the `user_uuid` attribute.
        2.  Add a new `api_key` attribute with:
            -   *Source*: *Expression*
            -   *Value*: The API key that you have copied when registering the OAuth2 client application in SAP SuccessFactors in step 1.2.d.



    For more information, see [Configuring Attributes Based on Flexible Expressions](https://help.sap.com/docs/cloud-identity-services/cloud-identity-services/configure-default-attributes-sent-to-application?version=Cloud) in the *SAP Cloud Identity Services* documentation.

7.  Enable principal propagation:
    1.  On the *Trust* tab of your application, under *Application APIs*, click *Provided APIs*.
    2.  In the *Provided APIs* section, under *API Permission Groups*, select *Allow all APIs for principal propagation* and save your configuration.

8.  Add a dependency to the API of the SAP SuccessFactors application in the OIDC Application:
    1.  In the *Administration Console* for your SAP Cloud Identity Services tenant, navigate to *Applications & Resources* \> *Applications* and select the OIDC application that you have created before.
    2.  On the *Trust* tab of your application, under *Application APIs*, click *Dependencies*.
    3.  In the *Dependencies* section, under APIs, click *Add*, complete the following properties and save your dependency:


        <table>
        <tr>
        <th valign="top">

        Property
        
        </th>
        <th valign="top">

        Description
        
        </th>
        </tr>
        <tr>
        <td valign="top">
        
        *Dependency Name*
        
        </td>
        <td valign="top">
        
        Enter a name for the dependency, for example `SFSAML`.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *Application*
        
        </td>
        <td valign="top">
        
        Select the SAML 2.0 application \(with the API to consume\) that you have created in step 3.3.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *API*
        
        </td>
        <td valign="top">
        
        The system displays the *All APIs* entry as you have configured it in the previous steps when enabling principal propagation.
        
        </td>
        </tr>
        </table>
        
        For more information, see [Configure Integration Between Applications](https://help.sap.com/docs/cloud-identity-services/cloud-identity-services/communicate-between-applications?version=Cloud) in the *SAP Cloud Identity Services* documentation.





<a name="loio63c8260a7f574e6e8e3c386656c93b00__results"/>

## Results

You have completed the initial configuration required to dynamically generate SAML assertions for accessing your SAP SuccessFactors API server via an SAP SuccessFactors connection. You can now create connections using the dynamic generation. For more information, see [SAP SuccessFactors Connections](sap-successfactors-connections-39df020.md).

