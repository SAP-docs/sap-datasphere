<!-- loio05383980f0704c71ab9872360ce45622 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Transporting Content Through SAP Cloud Transport Management

Integrate SAP Datasphere with SAP Cloud Transport Management service to transport content packages across different landscapes.

SAP Cloud Transport Management service lets you manage software deliverables between accounts of different environments \(such as Cloud Foundry, ABAP, and Neo\), by transporting them across various runtimes.

To transport your SAP Datasphere content through SAP Cloud Transport Management, you must configure your SAP Cloud Transport Management system.

Once you’ve configured the system, you must connect it to your SAP Datasphere tenant. You can also configure user rights that will be used in the SAP Datasphere target tenant.

Then you can use the SAP Datasphere Transport app to transfer your content to SAP Cloud Transport Management.

> ### Note:  
> Users with the *DW Administrator* global role \(or users with both a scoped *DW Space Administrator* role and a global role providing the *Lifecycle* privilege\) can use the *Transport* app to export content.

Finally, you can return to SAP Cloud Transport Management to ensure the transferred content is available and ready to be imported to another SAP Datasphere tenant.



## Configure SAP Cloud Transport Management

1.  As an administrator of SAP Cloud Transport Management, set up an environment to transport packages directly in SAP Datasphere, see [Initial Setup to Transport Content Objects Directly in an Application](https://help.sap.com/docs/cloud-transport-management/sap-cloud-transport-management/set-up-environment-to-transport-content-archives-directly-in-application).
2.  Configure the landscape for your transports by creating a destination for the target tenant. See [Create Transport Destinations](https://help.sap.com/docs/cloud-transport-management/sap-cloud-transport-management/create-transport-destinations).
    1.  In the SAP Business Technology Platform Cockpit of your subaccount, choose *Connectivity* \> *Destinations*.
    2.  In the *Destinations* editor, choose *Create* \> *From Scratch* \> *Create*.
    3.  Enter or select the following values:


        <table>
        <tr>
        <th valign="top">

        Field
        
        </th>
        <th valign="top">

        Description
        
        </th>
        </tr>
        <tr>
        <td valign="top">
        
        *Name*
        
        </td>
        <td valign="top">
        
        Name of the destination.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *Type*
        
        </td>
        <td valign="top">
        
        *HTTP*
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *Proxy Type*
        
        </td>
        <td valign="top">
        
        *Internet*
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *URL*
        
        </td>
        <td valign="top">
        
        To add an SAP Datasphere tenant as a destination, you must add an endpoint URL in this format: `https://<tenant_URL>/api/v1/content/deploy/`.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *Authentication*
        
        </td>
        <td valign="top">
        
        Select *OAuth2ClientCredentials*.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *Client ID*
        
        </td>
        <td valign="top">
        
        In the SAP Dataspheretenant, go to *System*→*Administration*→*App Integration* and create the OAuth Client \(client ID and secret\) with the purpose *API Access* and the access *Analytics Content Network Interaction*. See [Create an OAuth2.0 Client with an API Access Purpose](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/98500631fdd14762b702ad97d106c663.html "Users with an administrator role can create OAuth2.0 clients with an API access purpose and provide the client parameters to users who need to connect clients, tools, or apps to SAP Datasphere.") :arrow_upper_right: for more information.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *Client Secret*
        
        </td>
        <td valign="top">
        
        Enter the Client Secret previously generated.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *Token Service URL*
        
        </td>
        <td valign="top">
        
        In the SAP Datasphere tenant, go to *System*→*Administration*→*App Integration* to find the token URL and add the extension `<Token URL>?grant_type=client_credentials`.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *Token Service URL Type*
        
        </td>
        <td valign="top">
        
        Select *Dedicated*.
        
        </td>
        </tr>
        </table>
        
        Choose *Create* to create the destination.


3.  Go to the SAP Cloud Transport Management app and create two nodes: one for the source tenant and another for the target tenant. Make sure to select the checkbox Allow Upload to Node when creating a source node. When defining a target node, the content type must be Application Content to be able to select the destination name you've created in the previous step. See [Create Transport Nodes](https://help.sap.com/docs/cloud-transport-management/sap-cloud-transport-management/create-transport-nodes).
4.  Still in the SAP Cloud Transport Management app, create a route from the transport nodes you've created. See [Create Transport Routes](https://help.sap.com/docs/cloud-transport-management/sap-cloud-transport-management/create-transport-routes).
5.  Go back to your SAP Business Technology Platform subaccount. Choose the SAP Cloud Transport Management instance of your choice. In the instance details page, select a service binding, and choose *…* → *Download* to download the SAP Cloud Transport Management instance key.



## Connect to SAP Cloud Transport Management from SAP Datasphere

1.  In the side navigation area, click *Transport* \> *Export*.
2.  Navigate to *My Content* and click *Settings* from the menu bar.
3.  In the *Settings* dialog box, click the *Upload JSON* button to upload the instance key you previously downloaded from SAP Cloud Transport Management \(See step 5 in the previous section\).
4.  The connection of your SAP Datasphere tenant with SAP Cloud Transport Management is now live: click *OK*.



## Configure User Rights in SAP Datasphere

To ensure the content import from SAP Cloud Transport Management uses an existing user in the target tenant, you can assign your user, whose rights will be used to deploy the content.

1.  In the side navigation area of the target tenant, click *Transport* \> *Import*.
2.  Click *Settings* from the menu bar.
3.  In the *Settings* dialog box, under **User Authorization to Import from SAP Cloud Transport Management**, select a user whose rights will be used to import content. Click *OK*.

All users in this tenant will now use your configured user rights and privileges when importing content from SAP Cloud Transport Management.

If no user has been defined in the target tenant beforehand, the user must consent to use their rights during the upload to SAP Cloud Transport Management, provided that they have the necessary privileges and access to the required spaces in the target tenant \(See step 4 in [Export Packages from SAP Datasphere to SAP Cloud Transport Management](transporting-content-through-sap-cloud-transport-management-0538398.md#loio05383980f0704c71ab9872360ce45622__section_using)\).

> ### Note:  
> Only the system owner, along with the user who assigned his rights, can edit the permission. If the user has been deleted, then you can reset the permission and assign your user instead.



<a name="loio05383980f0704c71ab9872360ce45622__section_using"/>

## Export Packages from SAP Datasphere to SAP Cloud Transport Management

1.  In the side navigation area, click *Transport* \> *Export* and select the package you want to export.
2.  Click <span class="SAP-icons-V5"></span> *Upload to SAP Cloud Transport Management Node* from the menu bar: in the dialog box, you can see the list of selected packages.
3.  In the *Export Node* dropdown, choose the source node of SAP Cloud Transport Management to which you want to export your packages. For more information on source and target nodes, see [Create Transport Nodes](https://help.sap.com/docs/cloud-transport-management/sap-cloud-transport-management/create-transport-nodes).
4.  Select the checkbox to agree to use your user rights \(based on user email ID\) to import the package in the target tenant.
5.  Click *Upload*.



## Import Packages from SAP Cloud Transport Management to SAP Datasphere

1.  Log into your SAP Cloud Transport Management tenant: in the *Transport Nodes* panel, select the target node where you have uploaded the SAP Datasphere package.
2.  In the *Target Node Details* page, you can see your packages that are ready for import: select the package and click *Import Selected*.

Once the import is completed, you see the content of the package available in its corresponding destination in your SAP Datasphere account.

> ### Note:  
> The user who uploaded the package must be a member of the target tenant with the *Lifecycle* privilege.
> 
> The authentication method \(defined by the tenant owner\) must be the same on the source and on the target tenant. If the selected method is single sign-on \(SSO\), make sure to define the same user attribute for the source and the target tenant. For more information on authentication methods, see [Managing User Identity and Authentication](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/48b5c8b637a54fa491594272941855b9.html "The system owner can choose how to manage user identity and authentication for its SAP Datasphere tenant.") :arrow_upper_right:.

> ### Note:  
> The deployment after import does not support packages that contain objects from one or more spaces where objects are shared from one space to another \(see [Sharing Entities and Task Chains to Other Spaces](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/64b318f8afd74bb78467cf56eb44294f.html "Share a table or view to another space to allow users assigned to that space to use it as a source for their objects. Share a task chain to another space to allow it to be added to and controlled by another task chain in the space that you share it to.") :arrow_upper_right:. In this case, you should manually deploy the objects from the source space and then deploy the objects from the target space.



## Schedule Imports in SAP Cloud Transport Management

You can schedule imports of all transport requests in a transport node to run at regular intervals. For more information, see [Schedule Imports](https://help.sap.com/docs/cloud-transport-management/sap-cloud-transport-management/schedule-imports?version=Cloud).



## Enable Automatic Imports in SAP Cloud Transport Management

Activate the automatic import in the import queue of a transport node to enable immediate imports of transport requests as soon as they enter a new queue. For more information, see [Enable Automatic Import](https://help.sap.com/docs/cloud-transport-management/sap-cloud-transport-management/enable-automatic-import?version=Cloud).



## View SAP Cloud Transport Management Logs

In case of import failure, you can access the logs to investigate the error by adding this endpoint to the target tenant URL in your browser:

`{TenantURL}/contentmanager/v4/jobs/{ContentReferenceID}?brief=false` 

> ### Note:  
> The Content Reference ID is retrieved from the SAP Cloud Transport Management import logs.

