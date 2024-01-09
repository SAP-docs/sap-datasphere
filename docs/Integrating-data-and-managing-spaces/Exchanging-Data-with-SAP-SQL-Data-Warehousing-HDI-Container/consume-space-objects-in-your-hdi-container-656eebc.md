<!-- loio656eebc2ced14ec09afa455224fa9a98 -->

# Consume Space Objects in Your HDI Container

To consume SAP Datasphere views that are exposed for consumption as sources for your calculation views and flowgraphs, you must create a database user with appropriate privileges, create a user-provided service in SAP BTP Cockpit, and configure your HDI project.



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
    -   Create an `hdbgrants` file to grant read access to the views that you want to consume from your SAP Datasphere space.

        You can, optionally, grant access to the Application Function Library by including the following code in `hdbgrants`:

        ```
                	"global_roles" : [
                    	{
                        	"roles" : [ "AFL__SYS_AFL_AFLPAL_EXECUTE_WITH_GRANT_OPTION"]
                    	}
                	]			
        
        ```

        > ### Note:  
        > The SAP HANA Cloud Script Server must be enabled to allow this grant \(see [Enable the SAP HANA Cloud Script Server on Your SAP Datasphere Tenant](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/287194276a7d4d778ec98fdde5f61335.html "You can enable the SAP HANA Cloud script server on your SAP Datasphere tenant to access the SAP HANA Automated Predictive Library (APL) and SAP HANA Predictive Analysis Library (PAL) machine learning libraries.") :arrow_upper_right:\).

    -   Create `hdbsynonym` and `hdbsynonymconfig` files to define synonyms for the consumable views.

6.  Build your project.


