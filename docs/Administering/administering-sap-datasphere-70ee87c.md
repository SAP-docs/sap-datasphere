<!-- loio70ee87c19d3b47459ac7f2c8d4fea48a -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Administering SAP Datasphere

Users with the *DW Administrator* role can configure, manage, and monitor the SAP Datasphere tenant to support the work of acquiring, preparing, and modeling data for analytics. They manage users, create spaces, and allocate storage to them. They prepare and monitor connectivity for data integration and perform ongoing monitoring and maintainance of the tenant.

This topic contains the following sections:

-   [Configure Your SAP Datasphere Tenant](administering-sap-datasphere-70ee87c.md#loio70ee87c19d3b47459ac7f2c8d4fea48a__section_configure)
-   [Create Users and Assign Roles](administering-sap-datasphere-70ee87c.md#loio70ee87c19d3b47459ac7f2c8d4fea48a__section_users_roles)
-   [Create Spaces and Allocate Storage to Them](administering-sap-datasphere-70ee87c.md#loio70ee87c19d3b47459ac7f2c8d4fea48a__section_spaces)
-   [Prepare Connectivity](administering-sap-datasphere-70ee87c.md#loio70ee87c19d3b47459ac7f2c8d4fea48a__section_connectivity)
-   [Monitor and Maintain SAP Datasphere](administering-sap-datasphere-70ee87c.md#loio70ee87c19d3b47459ac7f2c8d4fea48a__section_monitoring)

> ### Tip:  
> The English version of this guide is open for contributions and feedback using GitHub. This allows you to get in contact with responsible authors of SAP Help Portal pages and the development team to discuss documentation-related issues. To contribute to this guide, or to provide feedback, choose the corresponding option on SAP Help Portal:
> 
> -   :pencil2:: Contribute to a documentation page. This option opens a pull request on GitHub.
> 
> -   <span class="SAP-icons"></span> Feedback: Provide feedback about a documentation page. This option opens an issue on GitHub.
> 
> 
> You need a GitHub account to use these options.
> 
> More information:
> 
> -   [Contribution Guidelines](https://help.sap.com/docs/open-documentation-initiative/contribution-guidelines/readme.html)
> 
> -   [Introduction Video: Open Documentation Initiative](https://www.youtube.com/watch?v=WJ0oarMlVW4)
> 
> -   [Blog Post: Introducing the Open Documentation Initiative](https://blogs.sap.com/2021/05/20/introducing-the-open-documentation-initiative/)



<a name="loio70ee87c19d3b47459ac7f2c8d4fea48a__section_configure"/>

## Configure Your SAP Datasphere Tenant

Either SAP will provision your tenant or you can create an instance in SAP BTP \(see [Creating and Configuring Your SAP Datasphere Tenant](Creating-and-Configuring-Your-Tenant/creating-and-configuring-your-sap-datasphere-tenant-2f80b57.md)\).

-   We recommend that you link your tenant to an SAP Analytics Cloud tenant \(see [Enable the Product Switch to Access an SAP Analytics Cloud Tenant](Creating-and-Configuring-Your-Tenant/enable-the-product-switch-to-access-an-sap-analytics-cloud-tenant-40db567.md)\).
-   You can enable SAP SQL data warehousing on your tenant to exchange data between your HDI containers and your SAP Datasphere spaces without the need for data movement \(see [Enable SAP SQL Data Warehousing on Your SAP Datasphere Tenant](Creating-and-Configuring-Your-Tenant/enable-sap-sql-data-warehousing-on-your-sap-datasphere-tenant-e9a2878.md)\).
-   You can enable the SAP HANA Cloud script server to access the SAP HANA Automated Predictive Library \(APL\) and SAP HANA Predictive Analysis Library \(PAL\) machine learning libraries \(see [Enable the SAP HANA Cloud Script Server on Your SAP Datasphere Tenant](Creating-and-Configuring-Your-Tenant/enable-the-sap-hana-cloud-script-server-on-your-sap-datasphere-tenant-2871942.md)\).



<a name="loio70ee87c19d3b47459ac7f2c8d4fea48a__section_users_roles"/>

## Create Users and Assign Roles

An administrator creates SAP Datasphere users manually, from a `*.csv` file, or via an identity provider \(see [Managing SAP Datasphere Users](Managing-Users-and-Roles/managing-sap-datasphere-users-4fb82cb.md)\).

You must assign one or more roles to each of your users \(see [Managing Roles and Privileges](Managing-Users-and-Roles/managing-roles-and-privileges-3740dac.md)\). The following standard roles are available:

-   Roles providing privileges to administer the SAP Datasphere tenant:
    -   **System Owner** - Includes all user privileges to allow unrestricted access to all areas of the application. Exactly one user must be assigned to this role. 
    -   **DW Administrator** - Can create users and spaces and has full privileges across the whole of the SAP Datasphere tenant. 

-   Roles providing privileges to work in SAP Datasphere spaces:
    -   **DW Space Administrator** - Can manage all aspects of a space \(except the *Storage Assignment* and *Workload Management* properties\) and can create data access controls and use the *Content Network*.
    -   *DW Integrator* - Can integrate data via connections and can manage and monitor data integration in spaces of which they are a member.
    -   **DW Modeler** - Can create and edit objects in the *Data Builder* and *Business Builder* and view data in all objects in spaces of which they are a member.
    -   **DW Viewer** - Can view objects in spaces of which they are a member and view data output by views that are exposed for consumption in these spaces.

-   Roles providing privileges to consume the data exposed by SAP Datasphere spaces:
    -   **DW Consumer** - Can consume data exposed by SAP Datasphere spaces of which they are members using SAP Analytics Cloud, and other clients, tools, and apps, but cannot log into SAP Datasphere. This role is intended for business analysts and other users who use SAP Datasphere data to drive their visualizations, but who have no need to access the modeling environment.

-   Roles providing privileges to work in the SAP Datasphere catalog:
    -   **Catalog Administrator** - Can set up and implement data governance using the catalog. This includes connecting the catalog to source systems for extracting metadata, building business glossaries, creating tags for classification, and publishing enriched catalog assets so all catalog users can find and use them. Must be used in combination with another role such as *DW Viewer* or *DW Modeler* for the user to have access to SAP Datasphere.
    -   **Catalog User** - Can search and discover data and analytics content in the catalog for consumption. These users may be modelers who want to build additional content based on official, governed assets in the catalog, or viewers who just want to view these assets. Must be used in combination with another role such as *DW Viewer* or *DW Modeler* for the user to have access to SAP Datasphere.




<a name="loio70ee87c19d3b47459ac7f2c8d4fea48a__section_spaces"/>

## Create Spaces and Allocate Storage to Them

All data acquisition, preparation, and modeling happens inside spaces. A space is a secure area - space data cannot be accessed outside the space unless it is shared to another space or exposed for consumption.

An administrator must create one or more spaces. They allocate disk and in-memory storage to the space, set its priority, and can limit how much memory and how many threads its statements can consume. See [Creating Spaces and Allocating Storage](Creating-Spaces-and-Allocating-Storage/creating-spaces-and-allocating-storage-2ace657.md).



<a name="loio70ee87c19d3b47459ac7f2c8d4fea48a__section_connectivity"/>

## Prepare Connectivity

Administrators prepare SAP Datasphere for creating connections to source systems in spaces \(see [Preparing Connectivity for Connections](Preparing-Connectivity/preparing-connectivity-for-connections-bffbd58.md)\).



<a name="loio70ee87c19d3b47459ac7f2c8d4fea48a__section_monitoring"/>

## Monitor and Maintain SAP Datasphere

Administrators have access to various monitoring logs and views and can, if necessary, create database analysis users to help troubleshoot issues \(see [Monitoring SAP Datasphere](Monitoring-SAP-Datasphere/monitoring-sap-datasphere-28910cd.md)\).

