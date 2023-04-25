<!-- loioadd771abf6f54c9d8de4c7e470a0e6f0 -->

# Consume Data in Power BI and Other Clients, Tools, and Apps via an OData Service

You can consume data exposed as views in Microsoft Power BI and other third-party clients, tools, and apps via the OData API.

You can connect Power BI to SAP Datasphere via an OData service by way of a custom connector or a blank query and consume views that are exposed for consumption.

![](images/Consumption_-_Other_-_ODATA_6d41d64.png)

You must:

-   Be a SAP Datasphere user with any of the standard roles. If you do not need to connect to SAP Datasphere itself, and only consume data, then an administrator can grant you the *DW Consumer* role \(see [Standard Application Roles](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/a50a51d80d5746c9b805a2aacbb7e4ee.html "SAP Datasphere is delivered with several standard roles.") :arrow_upper_right:\).

    If data access controls have been applied, then the data you can consume will be filtered based on your user id \(see [Securing Data with Data Access Controls](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/a032e51c730147c7a1fcac125b4cfe14.html "Data access controls allow you to apply row-level security to your objects. When a data access control is applied to a data layer view or a business layer object, any user viewing its data will see only the rows for which they are authorized, based on the specified criteria.") :arrow_upper_right:\).

-   Be a member of the SAP Datasphere space exposing the data \(see [Assign Members to Your Space](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/9d59fe511ae644d98384897443054c16.html "As a Space Administrator, you can assign users as members of your space.") :arrow_upper_right:\).
-   Obtain the following parameters for an OAuth client defined in your SAP Datasphere tenant:
    -   Client ID
    -   Secret
    -   Token URL
    -   Authorization URL


See the following blogs for more information:

-   [SAP Data Warehouse Cloud: OData Connector for Power BI](https://blogs.sap.com/2022/10/14/sap-data-warehouse-cloud-odata-connector-for-powerbi/) \(published October 2022\)
-   [Connecting SAP Data Warehouse Cloud OData API with Power BI via a Blank Query](https://blogs.sap.com/2022/09/23/connecting-sap-data-warehouse-cloud-odata-api-with-powerbi-via-a-blank-query-2/) \(published September 2022\)

