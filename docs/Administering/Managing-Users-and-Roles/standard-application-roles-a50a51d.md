<!-- loioa50a51d80d5746c9b805a2aacbb7e4ee -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Standard Application Roles

SAP Datasphere is delivered with several standard roles, which you can use as templates to create new roles.



You can assign standard roles directly to users or, if you have different business needs, you can use them as a template for defining new roles.

In the side navigation area, click <span class="FPA-icons"></span> \(*Security*\) ** \> ** <span class="FPA-icons"></span> \(*Roles*\). The following standard roles are available:

-   Roles providing privileges to administer the SAP Datasphere tenant:
    -   **System Owner** - Includes all user privileges to allow unrestricted access to all areas of the application. Exactly one user must be assigned to this role. 
    -   **DW Administrator** - Can create users and spaces and has full privileges across the whole of the SAP Datasphere tenant. 

-   Roles providing privileges to work in SAP Datasphere spaces:
    -   **DW Space Administrator** - Can manage all aspects of spaces of which they are a member \(except the *Storage Assignment* and *Workload Management* properties\) and can create data access controls and use the *Content Network*. 
    -   **DW Integrator** - Can create and edit connections and database users, and associate HDI containers in spaces of which they are a member. 
    -   **DW Modeler** - Can create and edit objects in the *Data Builder* and *Business Builder* and view data in all objects in spaces of which they are a member. 
    -   **DW Viewer** - Can view objects in spaces of which they are a member and view data output by views that are exposed for consumption in these spaces. 

-   Roles providing privileges to consume the data exposed by SAP Datasphere spaces:
    -   **DW Consumer** - Can consume data exposed by SAP Datasphere spaces of which they are members using SAP Analytics Cloud, and other clients, tools, and apps, but cannot log into SAP Datasphere. This role is intended for business analysts and other users who use SAP Datasphere data to drive their visualizations, but who have no need to access the modeling environment.

-   Roles providing privileges to work in the SAP Datasphere catalog:
    -   **Catalog Administrator** - Can set up and implement data governance using the catalog. This includes connecting the catalog to source systems for extracting metadata, building business glossaries, creating tags for classification, and publishing enriched catalog assets so all catalog users can find and use them. Must be used in combination with another role such as *DW Viewer* or *DW Modeler* for the user to have access to SAP Datasphere.
    -   **Catalog User** - Can search and discover data and analytics content in the catalog for consumption. These user may be modelers who want to build additional content based on official, governed assets in the catalog, or viewers who just want to view these assets. Must be used in combination with another role such as *DW Viewer* or *DW Modeler* for the user to have access to SAP Datasphere.


> ### Note:  
> Depending on their roles, users can do different actions in the spaces, provided that they are assigned as members of these spaces. See [Assign Members to Your Space](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/9d59fe511ae644d98384897443054c16.html "As a Space Administrator, you can assign users as members of your space.") :arrow_upper_right: .

> ### Note:  
> Please note for SAP Datasphere tenants that were initially provisioned prior to version 2021.03, you need the following additional roles to work with stories:
> 
> -   BI Content Creator - Creates and changes stories.
> -   BI Content Viewer - Views stories.



<a name="loioa50a51d80d5746c9b805a2aacbb7e4ee__section_wrs_gzw_wtb"/>

## Roles and Licenses

The standard application roles are grouped by the license type they consume and each user's license consumption is determined solely by the roles that they've been assigned. For example, a user who has been assigned only the *DW Administrator* standard role consumes only a *Data Warehouse Cloud* license.

Planning Professional, Planning Standard as well as Analytics Hub are SAP Analytics Cloud specific license types. For more information, see [Understand Licenses, Roles, and Permissions](https://help.sap.com/docs/SAP_ANALYTICS_CLOUD/00f68c2e08b941f081002fd3691d86a7/72ae65446c7943be80905c1d83a57a4a.html) in the *SAP Analytics Cloud* documentation.

