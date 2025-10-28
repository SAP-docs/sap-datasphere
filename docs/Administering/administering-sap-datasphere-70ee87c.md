<!-- loio70ee87c19d3b47459ac7f2c8d4fea48a -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Administering SAP Datasphere

Users with an administrator role are responsible for managing users and roles for the SAP Datasphere tenant, preparing connectivity for data integration, and creating spaces and allocating storage to them, as well as monitoring and maintaining the tenant.

This topic contains the following sections:

-   [Configure Your SAP Datasphere Tenant](administering-sap-datasphere-70ee87c.md#loio70ee87c19d3b47459ac7f2c8d4fea48a__section_configure)
-   [Create Users and Assign Roles](administering-sap-datasphere-70ee87c.md#loio70ee87c19d3b47459ac7f2c8d4fea48a__section_users_roles)
-   [Create Spaces and Allocate Storage](administering-sap-datasphere-70ee87c.md#loio70ee87c19d3b47459ac7f2c8d4fea48a__section_spaces)
-   [Prepare Connectivity](administering-sap-datasphere-70ee87c.md#loio70ee87c19d3b47459ac7f2c8d4fea48a__section_connectivity)
-   [Monitor and Maintain SAP Datasphere](administering-sap-datasphere-70ee87c.md#loio70ee87c19d3b47459ac7f2c8d4fea48a__section_monitoring)

> ### Tip:  
> The English version of this guide is open for contributions and feedback using GitHub. This allows you to get in contact with responsible authors of SAP Help Portal pages and the development team to discuss documentation-related issues. To contribute to this guide, or to provide feedback, choose the corresponding option on SAP Help Portal:
> 
> -   <span class="SAP-icons-V5"></span> Feedback ** \> *Edit page*: Contribute to a documentation page. This option opens a pull request on GitHub.
> 
> -   <span class="SAP-icons-V5"></span> Feedback ** \> *Create issue*: Provide feedback about a documentation page. This option opens an issue on GitHub.
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

-   We recommend that you link your tenant to an SAP Analytics Cloud tenant \(see [Review and Manage Links to SAP Analytics Cloud and SAP Business Data Cloud Tenants](Creating-and-Configuring-Your-Tenant/review-and-manage-links-to-sap-analytics-cloud-and-sap-business-data-cloud-t-40db567.md)\).
-   You can enable SAP HANA for SQL data warehousing on your tenant to exchange data between your HDI containers and your SAP Datasphere spaces without the need for data movement \(see [Enable SAP HANA for SQL Data Warehousing on Your SAP Datasphere Tenant](Creating-and-Configuring-Your-Tenant/enable-sap-hana-for-sql-data-warehousing-on-your-sap-datasphere-tenant-e9a2878.md)\).
-   You can enable the SAP HANA Cloud script server to access the SAP HANA Automated Predictive Library \(APL\) and SAP HANA Predictive Analysis Library \(PAL\) machine learning libraries \(see [Enable the SAP HANA Cloud Script Server on Your SAP Datasphere Tenant](Creating-and-Configuring-Your-Tenant/enable-the-sap-hana-cloud-script-server-on-your-sap-datasphere-tenant-2871942.md)\).



<a name="loio70ee87c19d3b47459ac7f2c8d4fea48a__section_users_roles"/>

## Create Users and Assign Roles

An administrator creates SAP Datasphere users manually, from a `*.csv` file, or via an identity provider \(see [Managing SAP Datasphere Users](Managing-Users-and-Roles/managing-sap-datasphere-users-4fb82cb.md)\).

You must assign one or more roles to each of your users via scoped roles and global roles \(see [Managing Roles and Privileges](Managing-Users-and-Roles/managing-roles-and-privileges-3740dac.md)\). You can create your own custom roles or use the following standard roles delivered with SAP Datasphere:

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

-   Role providing privileges to use AI features in SAP Datasphere:
    -   **DW AI Consumer** - Can use SAP Business AI features.

        > ### Note:  
        > To activate SAP Business AI features in your SAP Datasphere tenant, see [Enable SAP Business AI for SAP Datasphere](Creating-and-Configuring-Your-Tenant/enable-sap-business-ai-for-sap-datasphere-1b3fe45.md)





<a name="loio70ee87c19d3b47459ac7f2c8d4fea48a__section_spaces"/>

## Create Spaces and Allocate Storage

All data acquisition, preparation, and modeling in SAP Datasphere happens inside spaces. A space is a secure area - space data cannot be accessed outside the space unless it is shared to another space or exposed for consumption.

An administrator must create one or more spaces and allocate resources to them. See [Creating Spaces and Allocating Resources](Creating-Spaces-and-Allocating-Storage/creating-spaces-and-allocating-resources-2ace657.md).



<a name="loio70ee87c19d3b47459ac7f2c8d4fea48a__section_connectivity"/>

## Prepare Connectivity

Administrators prepare SAP Datasphere for creating connections to source systems in spaces \(see [Preparing Connectivity for Connections](Preparing-Connectivity/preparing-connectivity-for-connections-bffbd58.md)\).



<a name="loio70ee87c19d3b47459ac7f2c8d4fea48a__section_monitoring"/>

## Monitor and Maintain SAP Datasphere

Administrators have access to various monitoring logs and views and can, if necessary, create database analysis users to help troubleshoot issues \(see [Monitoring SAP Datasphere](Monitoring-SAP-Datasphere/monitoring-sap-datasphere-28910cd.md)\).

