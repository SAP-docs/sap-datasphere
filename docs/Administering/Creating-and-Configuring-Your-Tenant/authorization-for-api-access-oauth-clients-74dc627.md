<!-- loio74dc6275b23543d2b6aeba94eb538c64 -->

# Authorization for API access OAuth Clients

You can authorize a third party application to use public APIs.



## Context

If you selected *API Access* as the *Purpose* for the OAuth client, follow these steps to authorize a third party application to use the SAP Datasphere public APIs without a SAML assertion:



## Procedure

1.  Perform a POST HTTPS call to the following address:

    <code><i class="varname">&lt;Token URL&gt;</i>?grant_type=client_credentials</code>

    *<Token URL\>* is the *Token URL* listed in the *OAuth Clients* section of the *App Integration* page.

2.  Use basic authentication, and set the OAuth client ID as the user and the secret as the password. This call returns an access token.

3.  Access the required public API endpoint with the following headers:


    <table>
    <tr>
    <th valign="top">

    Header name


    
    </th>
    <th valign="top">

    Value


    
    </th>
    <th valign="top">

    Notes


    
    </th>
    </tr>
    <tr>
    <td valign="top">

     `Authorization` 


    
    </td>
    <td valign="top">

     <code>Bearer <i class="varname">&lt;Token&gt;</i></code> 


    
    </td>
    <td valign="top">

     *<Token\>* is the access token returned by the previous step.


    
    </td>
    </tr>
    <tr>
    <td valign="top">

     `x-sap-sac-custom-auth` 


    
    </td>
    <td valign="top">

     `True` 


    
    </td>
    <td valign="top">


    
    </td>
    </tr>
    </table>
    
    **Next Steps**

    If you use the OAuth 2.0 SAML Bearer Assertion workflow, you must also configure a trusted identity provider. For next steps, see [Add a Trusted Identity Provider](add-a-trusted-identity-provider-ea0688a.md).

    The client you added will appear in lists on the *App Integration* page. Hover over a client and select *Edit* or *Delete* to delete it.

    You may need to use the *Authorization URL* and *Token URL* listed here to complete setup on your OAuth clients.


