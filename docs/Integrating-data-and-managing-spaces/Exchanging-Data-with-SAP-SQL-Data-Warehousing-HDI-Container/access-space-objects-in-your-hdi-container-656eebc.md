<!-- loio656eebc2ced14ec09afa455224fa9a98 -->

# Access Space Objects in Your HDI Container

To access SAP Datasphere views that are exposed for consumption as sources for your calculation views and flowgraphs, you must create a database user with appropriate privileges, create a user-provided service in SAP BTP Cockpit, and configure your HDI project.



<a name="loio656eebc2ced14ec09afa455224fa9a98__context_jdt_wv2_pmb"/>

## Context

> ### Note:  
> See the blog [SAP Datasphere Integrated with SAP SQL Data Warehousing Sharing a Single DB Tenant](https://blogs.sap.com/2020/07/01/sap-data-warehouse-cloud-integrated-with-sap-sql-data-warehousing-sharing-a-single-db-tenant/) \(published in July 2021\) for a walkthrough of this process.



<a name="loio656eebc2ced14ec09afa455224fa9a98__steps_gj3_sh4_5mb"/>

## Procedure

1.  Add the HDI container to your space \(see [Add an HDI Container and Access its Objects in Your Space](add-an-hdi-container-and-access-its-objects-in-your-s-5d55da5.md)\).

2.  Create a database user with the following privileges:

    -   *Enable Read Access \(SQL\)*
    -   *Enable Write Access \(SQL, DDL, DML\)*
    -   *Enable HDI Consumption*

    See [Create a Database User](../Integrating-Data-Via-Database-Users/Open-SQL-Schema/create-a-database-user-798e3fd.md).

3.  Open the *Database User Details* dialog and copy the credentials from the *HDI Consumption* section.

4.  Go to the SAP BTP Cockpit, open *Service Instances*, and use the copied credentials to create a user-provided service instance, which will provide the connection between SAP BTP Cockpit and your SAP Datasphere tenant.

    See [Creating User-Provided Service Instances in Cloud Foundry Environment](https://help.sap.com/viewer/09cc82baadc542a688176dce601398de/Cloud/en-US/7c0125b78d744de6bed4595351fd120e.html) in the *SAP Service Manager* documentation.

5.  In your SAP Business Application Studio project, do the following:

    -   Prepare your project for building, including specifying the name of your user-provided service instance in your `mta.yaml` file \(see [Prepare Your HDI Project for Exchanging Data with Your Space](prepare-your-hdi-project-for-exchanging-data-with-you-a94e163.md)\).
    -   \[optional\] Create `hdbsynonym` and`hdbsynonymconfig` files to define synonyms for the views that you want to consume from your SAP Datasphere space, and an `hdbgrants` file to grant read access to them.

6.  Build your project.


