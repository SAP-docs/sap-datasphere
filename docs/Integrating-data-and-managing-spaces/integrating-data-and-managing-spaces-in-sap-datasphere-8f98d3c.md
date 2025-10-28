<!-- loio8f98d3c917f94452bafe288055b60b35 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Integrating Data and Managing Spaces in SAP Datasphere

Users with a space administrator or integrator role can create connections to source systems and databases and can schedule and monitor data replication and other data integration tasks. Space administrators are, additionally, responsible for controlling user access to their space, creating data access controls to secure data, enabling other forms of data integration, transporting content between tenants, and monitoring and otherwise managing the space.

This topic contains the following sections:

-   [Prepare and Manage Your Space](integrating-data-and-managing-spaces-in-sap-datasphere-8f98d3c.md#loio8f98d3c917f94452bafe288055b60b35__section_prepare_space)
-   [Create Connections to Source Systems](integrating-data-and-managing-spaces-in-sap-datasphere-8f98d3c.md#loio8f98d3c917f94452bafe288055b60b35__section_integrate_sources)
-   [Integrate Other Data Sources](integrating-data-and-managing-spaces-in-sap-datasphere-8f98d3c.md#loio8f98d3c917f94452bafe288055b60b35__section_integrate_other)
-   [Import Business and Sample Content](integrating-data-and-managing-spaces-in-sap-datasphere-8f98d3c.md#loio8f98d3c917f94452bafe288055b60b35__section_content)
-   [Prepare Row-Level Security for Data](integrating-data-and-managing-spaces-in-sap-datasphere-8f98d3c.md#loio8f98d3c917f94452bafe288055b60b35__section_dacs)
-   [Manage and Monitor Data Integration Tasks](integrating-data-and-managing-spaces-in-sap-datasphere-8f98d3c.md#loio8f98d3c917f94452bafe288055b60b35__section_monitor)

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



<a name="loio8f98d3c917f94452bafe288055b60b35__section_prepare_space"/>

## Prepare and Manage Your Space

An administrator will assign you the DW Space Administrator role, create your space, and assign you to it. Once this is done, you can prepare your space as follows:

-   Assign SAP Datasphere users to your space \(see [Control User Access to Your Space](control-user-access-to-your-space-9d59fe5.md)\).
-   Transport objects securely to and from your space \(see [Transporting Content Between Tenants](Transporting-Content-Between-Tenants/transporting-content-between-tenants-df12666.md)\).
-   Use various monitoring and logging tools to manage your space \(see [Managing Your Space](managing-your-space-268ea7e.md)\).



<a name="loio8f98d3c917f94452bafe288055b60b35__section_integrate_sources"/>

## Create Connections to Source Systems

Space administrators and integrators can create connections to source systems to allow space users to acquire data from those systems \(see [Integrating Data via Connections](Integrating-Data-Via-Connections/integrating-data-via-connections-eb85e15.md)\).



<a name="loio8f98d3c917f94452bafe288055b60b35__section_integrate_other"/>

## Integrate Other Data Sources

Space administrators can integrate data from other sources:

-   Create database users to allow external tools to connect to the space and write data to Open SQL schemas associated with the space \(see [Integrating Data via Database Users/Open SQL Schemas](Integrating-Data-Via-Database-Users/Open-SQL-Schema/integrating-data-via-database-users-open-sql-schemas-3de55a7.md)\).
-   If your space has access to the SAP HANA Cloud, data lake, you can access it via an Open SQL schema \(see [Integrating Data to and From SAP HANA Cloud Data Lake](Integrating-Data-to-and-From-HANA-Cloud/integrating-data-to-and-from-sap-hana-cloud-data-lake-e84545b.md)\).

-   Add SAP HDI containers to your space \(see [Exchanging Data with SAP HANA for SQL Data Warehousing HDI Containers](Exchanging-Data-with-SAP-SQL-Data-Warehousing-HDI-Container/exchanging-data-with-sap-hana-for-sql-data-warehousin-1aec7ca.md)\)
-   Generate a time table and associated time dimension views for use in the space \(see [Create Time Data and Dimensions](create-time-data-and-dimensions-c5cfce4.md)\).



<a name="loio8f98d3c917f94452bafe288055b60b35__section_content"/>

## Import Business and Sample Content

SAP and our partners provide business content to support end-to-end business scenarios for various industries and lines of business via the Content Network and our [Community Content](https://github.com/SAP-samples/analytics-cloud-datasphere-community-content) site \(see [Importing SAP and Partner Business Content from the Content Network](importing-sap-and-partner-business-content-from-the-content-network-400078d.md)\).

You can move your own content from tenant to tenant via the *Transport* app \(see [Transporting Content Between Tenants](Transporting-Content-Between-Tenants/transporting-content-between-tenants-df12666.md)\).

We also support direct import and export of many objects via CSN file \(see [Importing and Exporting Objects in CSN/JSON Files](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/f8ff0628c9fc49229740ffcd4d20e9aa.html "You can use the tools in certain Data Builder editors to import objects to and export objects from your space.") :arrow_upper_right:\).



<a name="loio8f98d3c917f94452bafe288055b60b35__section_dacs"/>

## Prepare Row-Level Security for Data

We recommend that you create data access controls, which can be applied to views to provide row-level filtering of your space data \(see [Securing Data with Data Access Controls](Data-Access-Control/securing-data-with-data-access-controls-a032e51.md)\).



<a name="loio8f98d3c917f94452bafe288055b60b35__section_monitor"/>

## Manage and Monitor Data Integration Tasks

You can enable, run, schedule, and monitor data replication tasks in the <span class="FPA-icons-V3"></span> \(*Data Integration Monitor*\) \(see [Managing and Monitoring Data Integration](Data-Integration-Monitor/managing-and-monitoring-data-integration-4cbf7c7.md)\).

