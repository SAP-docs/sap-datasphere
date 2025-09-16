<!-- loio88b13468fc3c4ebd972bcb8faa6cafbf -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Create an OAuth2.0 Client with a Technical User Purpose

Users with an administrator role can create OAuth2.0 clients with a technical user purpose and provide the client parameters to users, giving them limited privileges and permissions when connecting clients, tools, or apps to SAP Datasphere.



## Context

An OAuth client with a *Technical User* purpose provides restricted access to the tenant based on the roles you assign to it. You can assign one or more:

-   Global roles - To provide global privileges.
-   Scoped roles - To give access to one or more spaces and provide privileges in those spaces.

You create an OAuth2.0 Client with a *Technical User* purpose:

-   To use the SCIM 2.0 API \(see [Create Users and Assign Them to Roles via the SCIM 2.0 API](../Managing-Users-and-Roles/create-users-and-assign-them-to-roles-via-the-scim-2-0-api-1ca8c4a.md)\).
-   To transport content \(see [Transporting Your Content through SAP Cloud Transport Management](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/05383980f0704c71ab9872360ce45622.html "Integrate SAP Datasphere with SAP Cloud Transport Management service to transport content packages across different landscapes.") :arrow_upper_right: and [api/v1/content](https://help.sap.com/docs/SAP_ANALYTICS_CLOUD/14cac91febef464dbb1efce20e3f1613/eeace13cc37b4eed96064a7c5d8ee493.html) in the *SAP Analytics Cloud REST API Guide*\).
-   To export a log of user activities to a CSV file \(see [api/v1/audit/activities/exportActivities](https://help.sap.com/docs/SAP_ANALYTICS_CLOUD/14cac91febef464dbb1efce20e3f1613/ca45363ac1de4d669ad4a18115401d5a.html) in the *SAP Analytics Cloud REST API Guide*\).
-   To allow SAP Signavio to connect securely to SAP systems such as SAP S/4HANA \(see [SAP Signavio Connections](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/4c367de075a44ad7b7a6db576a4a9c82.html "Use the connection to securely integrate SAP systems such as SAP S/4HANA on-premise with SAP Signavio using replication flows for efficient and scalable data replication to SAP Signavio Process Intelligence.") :arrow_upper_right:.\)
-   To use the `datasphere` command line interface \(`marketplace` commands only\). See [Manage the Data Marketplace via the Command Line](https://help.sap.com/viewer/9b8363ae47c347de9a027c0e5567a37a/DEV_CURRENT/en-US/5a815f6c21e9468eb96d0be95b9d2def.html "Users with a modeler role can use the datasphere command line interface to manage the Data Marketplace.") :arrow_upper_right:.
-   To consume data via the OData API \(see [Consume Data via the OData API](https://help.sap.com/viewer/43509d67b8b84e66a30851e832f66911/cloud/en-US/7a453609c8694b029493e7d87e0de60a.html "You can connect to the OData API and consume data exposed as views or analytic models in SAP Analytics Cloud and other clients, tools, and apps that are capable of accessing an OData service and authenticating via an OAuth client.") :arrow_upper_right:\).



## Procedure

1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(*System*\) ** \> ** <span class="Belize-icons"></span> \(*Administration*\) ** \> *App Integration*.

2.  Under *Configured Clients*, select *Add a New OAuth Client*.

3.  In the dialog, enter or review the following properties as appropriate:


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
    
    Enter a name to identify the OAuth client.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    OAuth Client ID
    
    </td>
    <td valign="top">
    
    \[read-only\] Displays the ID once the client is created.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Purpose
    
    </td>
    <td valign="top">
    
    Select *Technical User*.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    User ID
    
    </td>
    <td valign="top">
    
    Enter an ID for the technical user associated with the OAuth client. The ID must be unique just like for any user. It can only contain uppercase letters, numbers, and underscores and its maximum length is 20 characters.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Roles
    
    </td>
    <td valign="top">
    
    Assign one or more roles \(global or scoped\) to the user. To do so, click *Select Roles*, then select one or more roles and click *OK*. See [Managing Roles and Privileges](../Managing-Users-and-Roles/managing-roles-and-privileges-3740dac.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Authorization Grant
    
    </td>
    <td valign="top">
    
    \[read-only\] *Client Credentials* is automatically selected and cannot be changed.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Secret
    
    </td>
    <td valign="top">
    
    \[read-only\] Allows the secret to be copied immediately after the client is created. 

    > ### Note:  
    > Once you close the dialog, the secret is no longer available.

    > ### Note:  
    > Clients created before v2024.08 have a *Show Secret* button, which allows you to display and copy the secret at any time after the client is created.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Expiry Date
    
    </td>
    <td valign="top">
    
    Choose when the OAuth client will expire, from a minimum of 7 days to a maximum of 20 years.

    Default: 3 months
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Token Lifetime
    
    </td>
    <td valign="top">
    
    Choose a lifetime for the access token from a minimum of one hour to a maximum of one day.

    Default: one day
    
    </td>
    </tr>
    </table>
    
4.  Click *Add* to create the client and generate the ID and secret.

    > ### Note:  
    > As long as the OAuth client has not expired, you can modify its name, assign different roles to its user, and extend its expiry date.

5.  Copy the secret, save it securely, and then close the dialog.

    > ### Note:  
    > You won't be able to copy the secret again. If you lose it, you will need to create a new client.

6.  Provide the following information to users who will use the client:


    <table>
    <tr>
    <th valign="top">

    Standard OAuth2 Authorization Flow
    
    </th>
    <th valign="top">

    OAuth2SAMLBearer Principal Propagation Flow
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    -   *Client ID*
    -   *Secret*
    -   *Token URL*


    
    </td>
    <td valign="top">
    
    -   *Client ID*
    -   *Secret*
    -   *OAuth2SAML Token URL*
    -   *OAuth2SAML Audience*


    
    </td>
    </tr>
    </table>
    



<a name="loio88b13468fc3c4ebd972bcb8faa6cafbf__postreq_mhq_bmb_y2c"/>

## Next Steps

Once the OAuth client has expired, a red exclamation mark icon is displayed in the *App Integration* page. To use the OAuth client once it has expired, you can extend its expiry date and click *Save*. A new secret is generated, which you must copy and save securely before you close the dialog.

> ### Note:  
> You won't be able to copy the secret again. If you lose it, you will need to create a new client.

