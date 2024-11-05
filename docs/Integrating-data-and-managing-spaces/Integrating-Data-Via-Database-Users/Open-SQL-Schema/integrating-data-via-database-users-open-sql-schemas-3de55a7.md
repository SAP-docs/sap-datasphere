<!-- loio3de55a78a4614deda589633baea28645 -->

# Integrating Data via Database Users/Open SQL Schemas

Create a database user in your space to read and write directly to the SAP HANA Cloud database on which SAP Datasphere runs. Each database user has an Open SQL schema, which is attached to a space schema and provides a secure method for exchanging data with the space.

Depending on the privileges they are granted, a database user can use their Open SQL schema to:

-   Create tables and views and write data to them \(see [Connect to Your Open SQL Schema](connect-to-your-open-sql-schema-b78ad20.md)\). Users assigned to a space can use these objects as sources when creating views and data flows \(see [Using the Source Browser](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/7d2b21d974e44bdc9d548cf7532b5a43.html "You use the Source Browser to add objects as sources for your data flow, graphical view, SQL view, or intelligent lookup. In an E/R model you add objects to visualize them together in a diagram, including importing objects from connections and other sources, and prepare them for use in other editors.") :arrow_upper_right:\).

    ![Open SQL Schema Objects are Sources for Space](images/Open_SQL_as_Source_6401fe8.png)

    > ### Note:  
    > Views with parameters cannot be imported to SAP Datasphere through an Open SQL schema.

-   Access the space schema and read data from the space.

    ![Open SQL Schema Reads View Exposed for Consumption](images/Open_SQL_Read_Exposed_View_a9a83fe.png)

    > ### Note:  
    > Database users can only read data from views that are created in the space with which they are associated if the view has the *Expose for Consumption* property enabled \(see [Exposing Data For Consumption](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/40ec77ec24f244279a81448969a7e769.html "Data can only be accessed outside of your SAP Datasphere space if it is exposed for consumption.") :arrow_upper_right:\).

-   Create a table to act as a target to receive data written from a data flow \(see [Allow the Space to Access the Open SQL Schema](allow-the-space-to-access-the-open-sql-schema-7eaa370.md)\).

    ![Space Data Flow Writes to Open SQL Schema Table](images/Open_SQL_Write_from_Space_1a84b15.png)


A database user is required in order to:

-   Connect an analytics client or other tool to SAP Datasphere \(see [Consume Data in Power BI and Other Clients, Tools, and Apps via an OData Service](https://help.sap.com/viewer/43509d67b8b84e66a30851e832f66911/cloud/en-US/add771abf6f54c9d8de4c7e470a0e6f0.html "You can consume data exposed as views in Microsoft Power BI and other third-party clients, tools, and apps via the OData API.") :arrow_upper_right:\).
-   Consume space data in an SAP SQL Data Warehousing HDI container \(see [Consume Space Objects in Your HDI Container](../../Exchanging-Data-with-SAP-SQL-Data-Warehousing-HDI-Container/consume-space-objects-in-your-hdi-container-656eebc.md)\).
-   Work with SAP HANA Cloud, data lake \(see [Integrating Data to and From SAP HANA Cloud Data Lake](../../Integrating-Data-to-and-From-HANA-Cloud/integrating-data-to-and-from-sap-hana-cloud-data-lake-e84545b.md)\).

> ### Note:  
> Users with the DW Administrator role can create database user groups, which are similar to database users, but which are not assigned to a single space and can allow multiple spaces to read from and write to their schemas \(see [Creating a Database User Group](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/1097a470be40432e89f91288bdc14378.html "Users with the DW Administrator role can create database user groups in SAP Datasphere to allow users to work in a sandboxed area in the underlying SAP HANA Cloud database, unattached to any space. These users can transfer an existing data warehouse implementation into the SAP Datasphere database or do any other work in SAP HANA Cloud and then make it available to one or more spaces as appropriate.") :arrow_upper_right:\).

