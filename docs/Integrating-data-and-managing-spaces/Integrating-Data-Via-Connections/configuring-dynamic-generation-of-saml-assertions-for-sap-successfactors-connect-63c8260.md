<!-- loio63c8260a7f574e6e8e3c386656c93b00 -->

# Configuring Dynamic Generation of SAML Assertions for SAP SuccessFactors Connections

Configure automated, dynamic generation of Security Assertion Markup Language \(SAML\) assertions for accessing SAP SuccessFactors APIs. For the generation of SAML assertions, SAP Datasphere is using the Identity Authentication service of SAP Cloud Identity Services as Identity Provider. Configuration steps are required in Identity Authentication and SAP SuccessFactors.



## Prerequisites

You require:

-   Administrator access to your SAP SuccessFactors tenant
-   Administrator access to your SAP Cloud Identity Services tenant
-   A technical user provisioned in both SAP Cloud Identity Services and SAP SuccessFactors with matching login names.



## Register an OAuth2 Client Application in SAP SuccessFactors

1.  Obtain the Identity Authentication signing certificate:
    1.  In the *Administration Console* for your SAP Cloud Identity Services tenant, navigate to *Applications & Resources* \> *Tenant Settings* \> *Single Sign-On* \> *SAML 2.0 Configuration* \> *Signing Certificates*.
    2.  In the *Action* column for the active valid certificate, click the <glass icon\> to view the certificate.
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
        
        Enter your SAP SuccessFactors tenant URL, for example `https://<sf-host>.successfactors.com/`.
        
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
        
        \[Required if you selected the *Bind to User* option\] Enter the user ID of the technical user provisioned in both SAP Cloud Identity Services and SAP SuccessFactors.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *X.509 Certificate*
        
        </td>
        <td valign="top">
        
        Enter the certificate that you have copied from SAP Cloud Identity Services in the previous step.
        
        </td>
        </tr>
        </table>
        
    3.  Click *Register*. The new application appears on the list of your OAuth2 client applications.
    4.  In the *Action* column for your application, click *View*, copy the *API Key* and keep it for later.


For more information about registering OAuth2 clients in SAP SuccessFactors, see [Registering Your OAuth2 Client Application](https://help.sap.com/viewer/d599f15995d348a1b45ba5603e2aba9b/latest/en-US/6b3c741483de47b290d075d798163bc1.html) in the *SAP SuccessFactors platform* documentation.



## Create an OpenID Connect \(OIDC\) Application in Identity Authentication

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
    
    Display Name
    
    </td>
    <td valign="top">
    
    Enter the name of the application, for example `OIDCTOKEN`. This name appears on the logon and registration pages.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Home URL
    
    </td>
    <td valign="top">
    
    not required
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Type
    
    </td>
    <td valign="top">
    
    Select *SAP SuccessFactors solution*.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Parent Application
    
    </td>
    <td valign="top">
    
    ???? Keep the default "None"???
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Organization ID
    
    </td>
    <td valign="top">
    
    ???? Keep the default "global"???
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Protocol
    
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





## Create a SAML Application in Identity Authentication

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
    
    Display Name
    
    </td>
    <td valign="top">
    
    Enter the name of the application, for example `OIDCTOKEN`. This name appears on the logon and registration pages.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Home URL
    
    </td>
    <td valign="top">
    
    not required
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Type
    
    </td>
    <td valign="top">
    
    Select *SAP SuccessFactors solution*.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Parent Application
    
    </td>
    <td valign="top">
    
    ???? Keep the default "None"???
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Organization ID
    
    </td>
    <td valign="top">
    
    ???? Keep the default "global"???
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Protocol
    
    </td>
    <td valign="top">
    
    Select *SAML 2.0*.
    
    </td>
    </tr>
    </table>
    
3.  Click *Create*. The new application appears on the list of the applications.

    For more information about creating SAML 2.0 applications, see [Create SAML 2.0 Application](https://help.sap.com/docs/cloud-identity-services/cloud-identity-services/create-saml-2-0-application?version=Cloud) in the *SAP Cloud Identity Services* documentation.

4.  Configure SAML 2.0:
5.  Configure Subject Name Identifier:
6.  Configure Attributes:
7.  Enable Principal Propagation:
8.  Add SAP SuccessFactors Dependency to OIDC Application:
9.  Add SAP SuccessFactors Login Name in Identitiy Authentication User:

