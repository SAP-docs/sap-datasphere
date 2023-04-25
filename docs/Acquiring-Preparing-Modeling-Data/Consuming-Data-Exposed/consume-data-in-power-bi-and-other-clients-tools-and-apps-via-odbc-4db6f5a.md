<!-- loio4db6f5a329af44509ae422ad707877b2 -->

# Consume Data in Power BI and Other Clients, Tools, and Apps via ODBC

You can consume data exposed as views in Microsoft Power BI and other third-party clients, tools, and apps via an Open SQL schema and ODBC.

You can connect Power BI to SAP Datasphere via an Open SQL schema, and consume perspectives and views that are exposed for consumption.

![](images/Consumption_-_Other_-_Open_SQL_Schema_2711e02.png)

You must:

-   Request a space administrator or integrator to provide you with access to a database user/Open SQL schema associated with the SAP Datasphere space exposing the data \(see [Create a Database User](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/798e3fd6707940c3bd2219b2d1ebaac2.html "Users with the DW Space Administrator or DW Integrator role (space administrators and integrators) can create database users, granting them privileges to read from and/or write to an Open SQL schema with restricted access to the space schema.") :arrow_upper_right:\).
-   Request an administrator to add the IP address of your tool to the IP allowlist \(see [Add IP address to IP Allowlist](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/a3c214514ef94e899459f68f4c1e2a23.html "Clients in your local network need an entry in the appropriate IP allowlist in SAP Datasphere. Cloud Connectors in your local network only require an entry if you want to use them for federation and replication from on-premise systems.") :arrow_upper_right:\).
-   Install the SAP HANA CLIENT 2.0 \(see [Download and Install the SAP HANA Client](https://help.sap.com/docs/HANA_CLOUD/db19c7071e5f4101837e23f06e576495/16155c86453943a5b62236535ecc7429.html) in the *SAP HANA Cloud* documentation\).
-   Create an ODBC connection to SAP Datasphere using your database user credentials \(see [Connect to SAP HANA Cloud via ODBC](https://help.sap.com/viewer/db19c7071e5f4101837e23f06e576495/cloud/en-US/9c0c101e368a4102a7eaeef542970741.html) in the *SAP HANA Cloud* documentation\).

See the blog [How to Consume SAP Data Warehouse Cloud in Power BI](https://blogs.sap.com/2022/02/23/how-to-consume-sap-data-warehouse-cloud-in-power-bi/) for more information.

