<!-- loio5d55da5514b240ff8d3a970bf7dc6705 -->

# Add an HDI Container and Access its Objects in Your Space

To access calculation views and other HDI objects as sources for your views and data flows, you must add the HDI container to your SAP Datasphere space.



<a name="loio5d55da5514b240ff8d3a970bf7dc6705__prereq_mtk_z41_t2c"/>

## Prerequisites

To add an HDI container and access its objects in your space, you must have a scoped role that grants you access to a space with the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Spaces* \(`-RU-----`\) - To read and update your spaces.
-   *Space Files* \(`-RU-----`\) - To read and update objects in your spaces.
-   *Data Warehouse Connection* \(`-RU-----`\) - To access remote objects.

The *DW Space Administrator* role template, for example, grants these privileges. For more information, see [Privileges and Permissions](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/d7350c6823a14733a7a5727bad8371aa.html "A privilege represents a task or an area in SAP Datasphere and can be assigned to a specific role. The actions that can be performed in the area are determined by the permissions assigned to a privilege.") :arrow_upper_right: and [Standard Roles Delivered with SAP Datasphere](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/a50a51d80d5746c9b805a2aacbb7e4ee.html "SAP Datasphere is delivered with several standard roles. A standard role includes a predefined set of privileges and permissions.") :arrow_upper_right:.



<a name="loio5d55da5514b240ff8d3a970bf7dc6705__context_jdt_wv2_pmb"/>

## Context

You must define the roles `DWC_CONSUMPTION_ROLE` and `DWC_CONSUMPTION_ROLE#` \(with grant option\) in the container to allow you to add it to your space and allow you to exchange data between them \(see [Prepare Your HDI Project for Exchanging Data with Your Space](prepare-your-hdi-project-for-exchanging-data-with-you-a94e163.md)\).

> ### Note:  
> See the blog [SAP Datasphere Integrated with SAP SQL Data Warehousing Sharing a Single DB Tenant](https://blogs.sap.com/2020/07/01/sap-data-warehouse-cloud-integrated-with-sap-sql-data-warehousing-sharing-a-single-db-tenant/) \(published in July 2021\) for a walkthrough of this process.



## Procedure

1.  In the side navigation area, click ![](../Integrating-Data-Via-Database-Users/Open-SQL-Schema/images/Space_Management_a868247.png) \(*Space Management*\), locate your space tile, and click *Edit* to open it.

2.  In the *HDI Container* section, click the *\+* button to open the *Add Unassigned HDI Containers* dialog.

    If the *\+* button is not available, no HDI containers have yet been built on the SAP Datasphere tenant.

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
        > See [Create a Database Analysis User to Debug Database Issues](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/c28145bcb76c4415a1ec6265dd2a4c11.html "Database analysis users are SAP HANA Cloud database users who have read-only access to all space schemas, and all their activities are recorded in audit logs. You create a database user to monitor, analyze, trace, or debug your SAP Datasphere database, and resolve a specific database issue.") :arrow_upper_right:.

    -   It may have been created before assignment was enabled or the `database_id` may need to be specified \(see [Set Up an HDI Container](https://help.sap.com/docs/HANA_SERVICE_CF/cc53ad464a57404b8d453bbadbc81ceb/93cdbb1bd50d49fe872e7b648a4d9677.html) in the *SAP HANA Service* documentation\).

4.  Deploy your space.

5.  Create a view or data flow and select one or more objects from the container as sources \(see [Import an Object from a Connection or Other Source](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/3e6f8f274e1d42759f536d3004025d24.html "Drag objects from the Sources tab of the Source Browser to add them as sources in your data flow, graphical view, or SQL view. In an E/R model, you can add objects from any connections and other sources, and prepare them for use in other editors.") :arrow_upper_right:\).


