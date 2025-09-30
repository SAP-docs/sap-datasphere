<!-- loio5661d8813b4c4eb395158cd90e0f4b2f -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Business Data Product Connections

If your SAP Datasphere tenant is included in an SAP Business Data Cloud formation, *Business Data Product* connections are used to connect to other SAP systems included in the same formation.

*Business Data Product* connections are managed differently compared to other connections:

When your SAP Datasphere tenant is added to an SAP Business Data Cloud formation, the connections to the source systems of the formation become available in SAP Datasphere with predefined technichal and business names.

An SAP Datasphere administrator can find the systems and corresponding connections on the <span class="FPA-icons-V3"></span> \(*System*\) ** \> ** :wrench: \(*Configuration*\) ** \> *Business Data Products* page and can change the business name of a connection if required. For a system and its corresponding connection, the administrator can authorize the spaces to which data products provided by the connected system can be installed \(see [Authorize Spaces to Install SAP Business Data Cloud Data Products](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/67ec785b5de842488781f20c4ab52a9f.html "An SAP Datasphere administrator must choose the spaces to which SAP Business Data Cloud data products from an activated data package can be installed.") :arrow_upper_right:\).

When a data product is installed to one or more authorized target spaces, the *Business Data Product* connection is created in an SAP-managed ingestion space \(if it does not already exist\). In the ingestion space, limited functionality is available for the connection, such as validating the connection or changing its business name \(on the *Edit* dialog\). The connection does not support the standard connection features but only supports the replication flows that have been created and deployed during data product installation.

> ### Note:  
> *Business Data Product* connections do not appear in the target spaces, neither in the *Connections* app nor in the *Source Browser* panel of the *Data Builder*.

**Related Information**  


[Integrating Data from SAP Business Data Cloud](../integrating-data-from-sap-business-data-cloud-8f9c372.md "Users with an SAP Business Data Cloud administrator role can install intelligent applications to SAP Datasphere and activate data packages to allow modelers to work with data products.")

[Installing Data Products](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/ea7cb802cbea47b39a441888873c3a49.html "Use the catalog Data Product collection to view data products for use in your modeling and other projects. You can see detailed metadata for each data product and if you have the appropriate permissions, install it to an SAP Datasphere space.") :arrow_upper_right:

