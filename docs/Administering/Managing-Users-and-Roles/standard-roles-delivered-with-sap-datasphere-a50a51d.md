<!-- loioa50a51d80d5746c9b805a2aacbb7e4ee -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Standard Roles Delivered with SAP Datasphere

SAP Datasphere is delivered with several standard roles. A standard role includes a predefined set of privileges and permissions.



A DW Administrator can use standard roles as templates for creating custom roles with a different set of privileges \(see [Create a Custom Role](create-a-custom-role-862b88e.md)\). You can also use the standard roles that include scoped privileges as templates for creating scoped roles \(see [Create a Scoped Role to Assign Privileges to Users in Spaces](create-a-scoped-role-to-assign-privileges-to-users-in-spaces-b5c4e0b.md)\). You can assign the standard roles that contain global privileges \(DW Administrator, Catalog Administrator and Catalog User\) directly to users.

> ### Note:  
> You cannot delete nor edit standard roles.

In the side navigation area, click <span class="FPA-icons-V3"></span> \(*Security*\) ** \> ** <span class="FPA-icons-V3"></span> \(*Roles*\). The following standard roles are available:

-   Roles providing privileges to administer the SAP Datasphere tenant:
    -   **System Owner** - Includes all user privileges to allow unrestricted access to all areas of the application. Exactly one user must be assigned to this role. 
    -   **DW Administrator** - Can create users, roles and spaces and has other administration privileges across the SAP Datasphere tenant. Cannot access any of the apps \(such as the *Data Builder*\). 

-   Roles providing privileges to work in SAP Datasphere spaces:
    -   **DW Space Administrator** \(template\) - Can manage all aspects of the spaces users are assigned to \(except the *Space Storage* and *Workload Management* properties\) and can create data access controls.
        -   *DW Scoped Space Administrator* - This predefined scoped role is based on the DW Space Administrator role and inherits its privileges and permissions.

            > ### Note:  
            > Users who are space administrators primarily need scoped permissions to work with spaces, but they also need some global permissions \(such as Lifecycle when transporting content packages\). To provide such users with the full set of permissions they need, they must be assigned to a scoped role \(such as the *DW Scoped Space Administrator*\) to receive the necessary scoped privileges, but they also need to be assigned directly to the *DW Space Administrator* role \(or a custom role that is based on the *DW Space Administrator* role\) in order to receive the additional global privileges.


    -   *DW Integrator* \(template\) - Can integrate data via connections and can manage and monitor data integration in a space.
        -   *DW Scoped Integrator* - This predefined scoped role is based on the DW Integrator role and inherits its privileges and permissions.


    -   **DW Modeler** \(template\) - Can create and edit objects in the *Data Builder* and *Business Builder* and view data in objects.
        -   *DW Scoped Modeler* - This predefined scoped role is based on the DW Modeler role and inherits its privileges and permissions.


    -   **DW Viewer** \(template\) - Can view objects and view data output by views that are exposed for consumption in spaces.
        -   *DW Scoped Viewer* - This predefined scoped role is based on the DW Viewer role and inherits its privileges and permissions.



-   Roles providing privileges to consume the data exposed by SAP Datasphere spaces:
    -   **DW Consumer** \(template\) - Can consume data exposed by SAP Datasphere spaces, using SAP Analytics Cloud, and other clients, tools, and apps. Users with this role cannot log into SAP Datasphere. It is intended for business analysts and other users who use SAP Datasphere data to drive their visualizations, but who have no need to access the modeling environment.
        -   *DW Scoped Consumer* - This predefined scoped role is based on the DW Consumer role and inherits its privileges and permissions.



-   Roles providing privileges to work in the SAP Datasphere catalog:
    -   **Catalog Administrator** - Can set up and implement data governance using the catalog. This includes connecting the catalog to source systems for extracting metadata, building business glossaries, creating tags for classification, and publishing enriched catalog assets so all catalog users can find and use them. Must be used in combination with another role such as *DW Viewer* or *DW Modeler* for the user to have access to SAP Datasphere.
    -   **Catalog User** - Can search and discover data and analytics content in the catalog for consumption. These users may be modelers who want to build additional content based on official, governed assets in the catalog, or viewers who just want to view these assets. Must be used in combination with another role such as *DW Viewer* or *DW Modeler* for the user to have access to SAP Datasphere.


> ### Note:  
> Please do not use the roles *DW Support User* and *DW Scoped Support User* as they are reserved for SAP Support.

Users are assigned roles in particular spaces via scoped roles. One user may have different roles in different spaces depending on the scoped role they're assigned to. See [Create a Scoped Role to Assign Privileges to Users in Spaces](create-a-scoped-role-to-assign-privileges-to-users-in-spaces-b5c4e0b.md).

> ### Note:  
> Please note for SAP Datasphere tenants that were initially provisioned prior to version 2021.03, you need the following additional roles to work with stories:
> 
> -   BI Content Creator - Creates and changes stories.
> -   BI Content Viewer - Views stories.



<a name="loioa50a51d80d5746c9b805a2aacbb7e4ee__section_wrs_gzw_wtb"/>

## Roles and Licenses

The standard roles are grouped by the license type they consume and each user's license consumption is determined solely by the roles that they've been assigned. For example, a user who has been assigned only the *DW Administrator* standard role consumes only a *SAP Datasphere* license.

Planning Professional, Planning Standard as well as Analytics Hub are SAP Analytics Cloud specific license types. For more information, see [Understand Licenses, Roles, and Permissions](https://help.sap.com/docs/SAP_ANALYTICS_CLOUD/00f68c2e08b941f081002fd3691d86a7/72ae65446c7943be80905c1d83a57a4a.html) in the *SAP Analytics Cloud* documentation.

