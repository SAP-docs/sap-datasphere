<!-- loio5661d8813b4c4eb395158cd90e0f4b2f -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Business Data Product Connections

If your SAP Datasphere tenant is included in an SAP Business Data Cloud formation, *Business Data Product* connections are used to connect to other SAP systems included in the same formation.

*Business Data Product* connections are managed differently compared to other connections:

When your SAP Datasphere tenant is added to an SAP Business Data Cloud formation, the connections to the source systems of the formation become available in SAP Datasphere with predefined technichal and business names.

An SAP Datasphere administrator can find the systems and corresponding connections on the <span class="FPA-icons-V3"></span> \(*System*\) ** \> ** :wrench: \(*Configuration*\) ** \> *Business Data Products* page and can change the business name of a connection if required. For a system and its corresponding connection, the administrator can authorize the spaces to which data products provided by the connected system can be installed \(see [Defining Allowed Spaces for Unified Customer Landscape Connections](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/67ec785b5de842488781f20c4ab52a9f.html "For remote systems that are integrated with SAP Datasphere in the Unified Customer Landscape, connections are generated in SAP Datasphere. These generated connections are not assigned to any spaces yet. In the Configuration tool, users with an administrator role can control which spaces users with an integrator role can add the connection to. Once added to a space, space users can use the connection to replicate data with replication flows from the remote systems.") :arrow_upper_right:\).

When a data product is installed to one or more authorized target spaces, the *Business Data Product* connection is created in an SAP-managed ingestion space \(if it does not already exist\). In the ingestion space, limited functionality is available for the connection, such as validating the connection or changing its business name \(on the *Edit* dialog\). The connection does not support the standard connection features but only supports the replication flows that have been created and deployed during data product installation.

> ### Note:  
> *Business Data Product* connections do not appear in the target spaces, neither in the *Connections* app nor in the *Source Browser* panel of the *Data Builder*.

**Related Information**  


[Integrating Data from SAP Business Data Cloud](../integrating-data-from-sap-business-data-cloud-8f9c372.md "SAP Business Data Cloud is a fully managed SaaS solution that unifies and governs all SAP data and seamlessly connects with third-party data—giving line-of-business leaders context to make even more impactful decisions.")

[Evaluating and Installing SAP Business Data Cloud Data Products](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/ea7cb802cbea47b39a441888873c3a49.html "When you find an SAP Business Data Cloud data product that interests you, you can view information about it to make sure it’s the right one for your business needs. You can then install it in your SAP Datasphere space.") :arrow_upper_right:

