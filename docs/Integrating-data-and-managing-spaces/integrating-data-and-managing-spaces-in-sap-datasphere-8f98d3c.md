<!-- loio8f98d3c917f94452bafe288055b60b35 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Integrating Data and Managing Spaces in SAP Datasphere

Users with the *DW Space Administrator* or *DW Integrator* role can create connections to source systems and databases and use other methods to bring data into their space. They can schedule and monitor data replication and other data integration tasks. Space administrators are responsible for maintaining the list of space members and monitoring and managing the space. They can create data access controls to secure data, and can transport content between tenants.

This topic contains the following sections:

-   [Prepare and Manage Your Space](integrating-data-and-managing-spaces-in-sap-datasphere-8f98d3c.md#loio8f98d3c917f94452bafe288055b60b35__section_prepare_space)
-   [Integrate Data Sources](integrating-data-and-managing-spaces-in-sap-datasphere-8f98d3c.md#loio8f98d3c917f94452bafe288055b60b35__section_integrate_sources)
-   [Prepare Row-Level Security for Data](integrating-data-and-managing-spaces-in-sap-datasphere-8f98d3c.md#loio8f98d3c917f94452bafe288055b60b35__section_dacs)
-   [Manage and Monitor Data Integration Tasks](integrating-data-and-managing-spaces-in-sap-datasphere-8f98d3c.md#loio8f98d3c917f94452bafe288055b60b35__section_monitor)



<a name="loio8f98d3c917f94452bafe288055b60b35__section_prepare_space"/>

## Prepare and Manage Your Space

An administrator will assign you the DW Space Administrator role, create your space, and add you to it as a member. Once this is done, you can prepare your space as follows:

-   Add SAP Datasphere users as members of your space \(see [Assign Members to Your Space](assign-members-to-your-space-9d59fe5.md)\).
-   Optionally import SAP and partner business content to support end-to-end business scenarios for various industries and lines of business \(see [Importing SAP and Partner Business Content from the Content Network](importing-sap-and-partner-business-content-from-the-content-network-400078d.md)\).
-   Transport objects securely to and from your space \(see [Transporting Content Between Tenants](Transporting-Content-Between-Tenants/transporting-content-between-tenants-df12666.md)\).
-   Use various monitoring and logging tools to manage your space \(see [Managing Your Space](managing-your-space-268ea7e.md)\).



<a name="loio8f98d3c917f94452bafe288055b60b35__section_integrate_sources"/>

## Integrate Data Sources

Space administrators and integrators create connections and other data sources in the space:

-   Create connections to source systems to allow space members to acquire data from those systems \(see [Integrating Data via Connections](Integrating-Data-Via-Connections/integrating-data-via-connections-eb85e15.md)\).
-   Create database users to allow external tools to connect to the space and write data to Open SQL schemas associated with the space \(see [Integrating Data via Database Users/Open SQL Schemas](Integrating-Data-Via-Database-Users/Open-SQL-Schema/integrating-data-via-database-users-open-sql-schemas-3de55a7.md)\).
-   If your space has access to the SAP HANA Cloud, data lake, you can access it via an Open SQL schema \(see [Integrating Data to and From SAP HANA Cloud Data Lake](Integrating-Data-to-and-From-HANA-Cloud/integrating-data-to-and-from-sap-hana-cloud-data-lake-e84545b.md)\).

-   Add SAP HDI containers to your space \(see [Exchanging Data with SAP SQL Data Warehousing HDI Containers](Exchanging-Data-with-SAP-SQL-Data-Warehousing-HDI-Container/exchanging-data-with-sap-sql-data-warehousing-hdi-con-1aec7ca.md)\)
-   Generate a time table and associated time dimension views for use in the space \(see [Create Time Data and Dimensions](create-time-data-and-dimensions-c5cfce4.md)\).



<a name="loio8f98d3c917f94452bafe288055b60b35__section_dacs"/>

## Prepare Row-Level Security for Data

We recommend that you create data access controls, which can be applied to views to provide row-level filtering of your space data \(see [Securing Data with Data Access Controls](Data-Access-Control/securing-data-with-data-access-controls-a032e51.md)\).



<a name="loio8f98d3c917f94452bafe288055b60b35__section_monitor"/>

## Manage and Monitor Data Integration Tasks

You can enable, run, schedule, and monitor data replication tasks in the <span class="FPA-icons"></span> \(*Data Integration Monitor*\) \(see [Managing and Monitoring Data Integration](Data-Integration-Monitor/managing-and-monitoring-data-integration-4cbf7c7.md)\).

