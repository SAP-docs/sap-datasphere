<!-- loio5d55da5514b240ff8d3a970bf7dc6705 -->

# Add an HDI Container and Access its Objects in Your Space

To access calculation views and other HDI objects as sources for your views and data flows, you must add the HDI container to your SAP Datasphere space.



<a name="loio5d55da5514b240ff8d3a970bf7dc6705__context_jdt_wv2_pmb"/>

## Context

You must define the roles `DWC_CONSUMPTION_ROLE` and `DWC_CONSUMPTION_ROLE#` \(with grant option\) in the container to allow you to add it to your space and allow you to exchange data between them \(see [Prepare Your HDI Project for Exchanging Data with Your Space](prepare-your-hdi-project-for-exchanging-data-with-you-a94e163.md)\).

> ### Note:  
> See the blog [SAP Datasphere Integrated with SAP SQL Data Warehousing Sharing a Single DB Tenant](https://blogs.sap.com/2020/07/01/sap-data-warehouse-cloud-integrated-with-sap-sql-data-warehousing-sharing-a-single-db-tenant/) \(published in July 2021\) for a walkthrough of this process.



## Procedure

1.  In the side navigation area, click ![](../Integrating-Data-Via-Database-Users/Open-SQL-Schema/images/Space_Management_a868247.png) \(*Space Management*\), locate your space tile, and click *Edit* to open it.

2.  In the *HDI Container* section, click the *\+* button to open the *Add Unassigned HDI Containers* dialog.

    If the *\+* button is not available, then you need to raise a ticket \(see [Exchanging Data with SAP SQL Data Warehousing HDI Containers](exchanging-data-with-sap-sql-data-warehousing-hdi-con-1aec7ca.md)\) or no HDI containers have yet been built on the SAP Datasphere tenant.

3.  Select one or more HDI containers and then click *Add* to add them to your space.

    If your HDI container is not available:

    -   It may already be assigned to another space.

        > ### Note:  
        > Each HDI container can only be added to one SAP Datasphere space. A database analysis user can review the assignment of HDI assignments using the following query:
        > 
        > ```
        > select * from DWC_TENANT_OWNER.SPACE_SCHEMAS where SCHEMA_TYPE = 'hdi_owned';
        > ```
        > 
        > See [Create a Database Analysis User to Debug Database Issues](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/c28145bcb76c4415a1ec6265dd2a4c11.html "A database analysis user is an SAP HANA Cloud database user with wide-ranging privileges. It can be used to support monitoring, analyzing, tracing, and debugging of your SAP Datasphere run-time database.") :arrow_upper_right:.

    -   It may have been created before assignment was enabled or the `database_id` may need to be specified \(see [Set Up an HDI Container](https://help.sap.com/docs/HANA_SERVICE_CF/cc53ad464a57404b8d453bbadbc81ceb/93cdbb1bd50d49fe872e7b648a4d9677.html) in the *SAP HANA Service* documentation\).

4.  Deploy your space.

5.  Create a view or data flow and select one or more objects from the container as sources \(see [Import an Object from a Connection or Other Source](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/3e6f8f274e1d42759f536d3004025d24.html "Drag objects from the Sources tab of the Source Browser to add them as sources in your data flow, graphical view, or SQL view. In an E/R model, you can add objects from any connections and other sources, and prepare them for use in other editors.") :arrow_upper_right:\).


