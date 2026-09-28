<!-- loio24bb8c280dfc4a7d98583283aa45f749 -->

# Set Up Third-Party Access with OAuth Clients Using Identity Authentication

Users with an administrator role can set up Open Authorization \(OAuth\) access using Identity Authentication OAuth Clients and provide the client parameters to users who need to connect clients, tools, or apps to SAP Datasphere.



<a name="loio24bb8c280dfc4a7d98583283aa45f749__section_dwk_5f5_3hc"/>

## Prerequisites

To set up Identity Authentication OAuth Clients to authenticate against SAP Datasphere, you must have a global role that grants you the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *System Information* \(`-RU-----`\) - To access the *System* tool.
-   *User* \(`CRUD----`\) - To create, update, and delete OAuth clients in the *Administration* area in the *System* tool.

The *DW Administrator* global role, for example, grants these privileges. For more information, see [Privileges and Permissions](../Managing-Users-and-Roles/privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](../Managing-Users-and-Roles/standard-roles-delivered-with-sap-datasphere-a50a51d.md). 

In addition, you must have an SAP Cloud Identity Services tenant and also create a dependency between the consuming application and the SAP Datasphere application \(see [Get Your Tenant](https://help.sap.com/docs/cloud-identity-services/cloud-identity-services/get-your-tenant) and [Consuming APIs from Other Applications](https://help.sap.com/docs/cloud-identity-services/cloud-identity-services/consume-apis-from-other-applications) in the *SAP Cloud Identity Services*\).



<a name="loio24bb8c280dfc4a7d98583283aa45f749__section_oss_xf5_3hc"/>

## Purposes

You can set up Identity Authentication OAuth Clients with:

-   An *API Access* purpose to provide access with tenant-wide privileges.
-   A *Technical User* purpose to provide restricted access to the tenant based on the roles you assign to it.

