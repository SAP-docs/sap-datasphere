<!-- loio4d2536a71c57477195ced274ecfd225d -->

# Enable IdP-Initiated Single Sign On \(SAP Data Center Only\)

By default, IdP-initiated SSO is not supported if SAP Datasphere is running on an SAP Data Center. To support IdP initiated SSO on an SAP Data Center, you must add a new assertion consumer service endpoint to your identity provider.



<a name="loio4d2536a71c57477195ced274ecfd225d__prereq_e2k_1qz_hjb"/>

## Prerequisites

SAP Datasphere can be hosted either on SAP data centers or on non-SAP data centers. Determine which environment SAP Datasphere is hosted in by inspecting your URL:

-   A single-digit number, for example us1 or jp1, indicates an SAP data center.

-   A two-digit number, for example eu10 or us30, indicates a non-SAP data center.




## Procedure

1.  Navigate to your IdP and find the page where you configure SAML 2.0 Single Sign On.

2.  Find and copy your FQDN.

    For example, mysystem.wdf.sap-ag.de

3.  Add a new assertion consumer service \(ACS\) endpoint that follows this pattern:

    ```
    https:// <FQDN>/
    ```

    For example, https://mysystem.wdf.sap-ag.de/

4.  If you are using SAP Cloud Identity Authentication Service as your identity provider, the link to log onto SAP Datasphere through your identity provider will follow this pattern:

    ```
    https://<tenant_ID>.accounts.ondemand.com/saml2/idp/sso?sp=<sp_name>&index=<index_number>
    ```

    For example, https://testsystem.accounts999.ondemand.com/saml2/idp/sso?sp=mysystem.wdf.sap-ag.de.cloud&index=1

    > ### Note:  
    > The pattern will vary depending on the identity provider you use.

    The following table lists the URL parameters you can use for IdP-initiated SSO.


    <table>
    <tr>
    <th valign="top">

    Parameter
    
    </th>
    <th valign="top">

    Mandatory
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    sp
    
    </td>
    <td valign="top">
    
    Yes
    
    </td>
    <td valign="top">
    
    -   This is the name of the SAML 2 service provider for which SSO is performed.

    -   The sp\_name value of the parameter equals the Entity ID of the service provider.

    -   This parameter is needed for Identity Authentication to know which service provider to redirect the user to after successful authentication.



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    index
    
    </td>
    <td valign="top">
    
    > ### Note:  
    > You can choose by the index the correct ACS endpoint for unsolicited SAML response processing. Provide the index parameter when the default ACS endpoint that has been configured via the administration console cannot process unsolicited SAML responses.


    
    </td>
    <td valign="top">
    
    -   Enter the index number of the endpoint of the assertion consumer service of the service provider as the target of the SAML response. Otherwise, the identity provider uses the default endpoint configured for the trusted service provider.

    -   If your IdP doesn't support indexing, you must choose between IdP-initiated SSO or SP-initiated SSO. You can either replace the default ACS endpoint to initiate an IdP SSO or continue using the default endpoint to initiate an SP SSO.

    -   A non-digit value or a value for an index entry that is not configured returns an error message.



    
    </td>
    </tr>
    </table>
    



<a name="loio4d2536a71c57477195ced274ecfd225d__result_lzy_srn_3jb"/>

## Results

Users will be able to use SAML SSO to log onto SAP Datasphere through their identity provider.

