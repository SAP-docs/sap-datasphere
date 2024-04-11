<!-- loioea0688aef2f94b35ae34d930b3cb0c10 -->

# Add a Trusted Identity Provider

If you use the OAuth 2.0 SAML Bearer Assertion workflow, you must add a trusted identity provider to SAP Datasphere.



<a name="loioea0688aef2f94b35ae34d930b3cb0c10__context_ygg_5r5_bpb"/>

## Context

The OAuth 2.0 SAML Bearer Assertion workflow allows third-party applications to access protected resources without prompting users to log into SAP Datasphere when there is an existing SAML assertion from the third-party application identity provider.

> ### Note:  
> Both SAP Datasphere and the third-party application must be configured with the same identity provider. The identity provider must have a user attibute `Groups` set to the static value `sac`.



<a name="loioea0688aef2f94b35ae34d930b3cb0c10__steps_zgg_5r5_bpb"/>

## Procedure

1.  Go to *System* \> *Administration* \> *App Integration*.

2.  In the *Trusted Identity Providers* section, click *Add a Trusted Identity Provider*.

3.  In the dialog, enter the following properties:


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
    
    Name
    
    </td>
    <td valign="top">
    
    Enter a unique name, which will appear in the list of trusted identity providers.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Provider Name
    
    </td>
    <td valign="top">
    
    Enter a unique name for the provide. This name can contain only alphabet characters \(a-z & A-Z\), numbers \(0-9\), underscore \(\_\), dot \(.\), hyphen \(-\), and cannot exceed 36 characters.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Signing Certificate
    
    </td>
    <td valign="top">
    
    Enter the signing certificate information for the third-party application server in X.509 Base64 encoded format.
    
    </td>
    </tr>
    </table>
    
4.  Click *Add*.

    The identity provider is added to the list. Hover over it and select *Edit* to update it or *Delete* to delete it.

    You may need to use the *Authorization URL* and *Token URL* listed here to complete setup on your OAuth clients.


