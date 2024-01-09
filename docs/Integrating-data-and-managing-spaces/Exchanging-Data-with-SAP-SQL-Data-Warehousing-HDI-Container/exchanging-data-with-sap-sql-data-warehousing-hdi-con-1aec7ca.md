<!-- loio1aec7ca95af24208a61c1a444b249d95 -->

# Exchanging Data with SAP SQL Data Warehousing HDI Containers

Use SAP SQL Data Warehousing to build calculation views and other SAP HANA Cloud HDI objects directly in your SAP Datasphere run-time database and then exchange data between your HDI containers and your SAP Datasphere spaces. SAP SQL Data Warehousing can be used to bring existing HDI objects into your SAP Datasphere environment, and to allow users familiar with the HDI tools to leverage advanced SAP HANA Cloud features.



## Context

To enable SAP SQL Data Warehousing on your SAP Datasphere tenant, an S-user must create an SAP ticket to connect your SAP BTP account \(see [Enable SAP SQL Data Warehousing on Your SAP Datasphere Tenant](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/e9a287849ccf41bb8a132d12dd3fdc8f.html "Use SAP SQL Data Warehousing to build calculation views and other SAP HANA Cloud HDI objects directly in your SAP Datasphere run-time database and then exchange data between your HDI containers and your SAP Datasphere spaces. SAP SQL Data Warehousing can be used to bring existing HDI objects into your SAP Datasphere environment, and to allow users familiar with the HDI tools to leverage advanced SAP HANA Cloud features.") :arrow_upper_right:\).

> ### Note:  
> See the blog [SAP SQL Data Warehousing with HANA](https://blogs.sap.com/2017/12/19/sap-sql-data-warehousing-with-hana/) \(published in December 2017\) for an introduction to SAP SQL Data Warehousing.
> 
> See the blog [SAP BTP Showcase – Access the SAP HANA Cloud Database Underneath SAP Datasphere](https://blogs.sap.com/2021/01/31/sap-btp-showcase-access-the-sap-hana-cloud-database-underneath-sap-data-warehouse-cloud/) \(published in January 2021\) for an overview of the Integrated SAP SQL Data Warehousing approach.
> 
> See the blog [SAP Datasphere – Hybrid Access to SAP HANA for SQL Data Warehousing](https://blogs.sap.com/2020/06/19/sap-data-warehouse-cloud-hybrid-access-to-sap-hana-for-sql-data-warehousing/) \(published in June 2021\) for information about accessing your HDI objects on another server through a standard SAP HANA connection.

The integrated SAP SQL data warehousing approach allows you to add HDI containers to your space and exchange data between them:

-   Bring data from calculation views and other objects built in your HDI container into your SAP Datasphere space via local tables and data flows \(see [Add an HDI Container and Access its Objects in Your Space](add-an-hdi-container-and-access-its-objects-in-your-s-5d55da5.md)\).

    ![HDI Container Objects are Sources for Space](images/HDI_as_Source_201d2a8.png)

-   Use data exposed from your SAP Datasphere space as a source for calculation views and flowgraphs built in your HDI container \(see [Consume Space Objects in Your HDI Container](consume-space-objects-in-your-hdi-container-656eebc.md)\).

    ![HDI Container Reads View Exposed for Consumption](images/HDI_Read_Exposed_View_f8edd97.png)

-   Select tables in your HDI container as targets for your SAP Datasphere data flows \(see [Allow Your Space to Write to Your HDI Container](allow-your-space-to-write-to-your-hdi-container-aa3627f.md)\).

    ![Space Data Flow Writes to HDI Container Table](images/HDI_Write_from_Space_ccf514b.png)


