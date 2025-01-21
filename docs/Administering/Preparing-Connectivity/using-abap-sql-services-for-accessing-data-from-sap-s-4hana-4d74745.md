<!-- loio4d7474595a5b41bb986616262ff44a3a -->

# Using ABAP SQL Services for Accessing Data from SAP S/4HANA

The ABAP SQL service provides SQL-level access to published CDS view entities for SAP Datasphere. You can use the service to federate data with remote tables. Using the service requires Cloud Connector.

> ### Note:  
> -   This feature requires developer extensibility in SAP S/4HANA \(including ABAP development tools\). For more information, see [Developer Extensibility](https://help.sap.com/docs/ABAP_PLATFORM_NEW/b5670aaaa2364a29935f40b16499972d/155909e3569941e08831c78cf4c2d495.html) in the *ABAP Platform* documentation for your SAP S/4HANA system.
> 
> -   For data federation using the SQL service, privileged data access needs to be enabled for communication users in SAP S/4HANA. For more information, see [Access Scenarios](https://help.sap.com/docs/ABAP_PLATFORM_NEW/b5670aaaa2364a29935f40b16499972d/96368bd086ff4f79933b078a6cf7feaa.html) in the *ABAP Platform* documentation for your SAP S/4HANA system.
> 
> -   Make sure the SAP S/4HANA system you want to connect is based on the ABAP platform 2021 FPS01 or higher where the ABAP SQL service is available.
> 
> -   When a connection is configured for using the ABAP SQL service for data federation with remote tables, you can't use the same connection for model import.



Perform the following steps to prepare data federation with remote tables:

-   Set up Cloud Connector for using the ABAP SQL service, which involves the following Cloud Connector configuration:

    1.  When adding the system mapping to the SAP S/4HANA system, select HTTP or HTTPS protocol.

        > ### Note:  
        > When a connection uses both data or replication flow and remote table features, you need two system mappings:
        > 
        > 
        > <table>
        > <tr>
        > <th valign="top">
        > 
        > Feature
        > 
        > </th>
        > <th valign="top">
        > 
        > Protocol
        > 
        > </th>
        > <th valign="top">
        > 
        > Virtual Host
        > 
        > </th>
        > <th valign="top">
        > 
        > Virtual Port
        > 
        > </th>
        > </tr>
        > <tr>
        > <td valign="top">
        > 
        > Data flow and replication flow
        > 
        > </td>
        > <td valign="top">
        > 
        > RFC
        > 
        > </td>
        > <td valign="top">
        > 
        > Enter the same virtual host in Cloud Connector system mapping and in the connection \(virtual host in the connections' Cloud Connector properties must be manually entered\).
        > 
        > </td>
        > <td valign="top">
        > 
        > Make sure that the virtual port defined in the Cloud Connector configuration matches the virtual port entered in the connections' Cloud Connector properties: ***sapgw*<system number\>****.
        > 
        > </td>
        > </tr>
        > <tr>
        > <td valign="top">
        > 
        > Remote tables
        > 
        > </td>
        > <td valign="top">
        > 
        > HTTP or HTTPS
        > 
        > </td>
        > <td valign="top">
        > 
        > Enter the same virtual host in Cloud Connector and in the connection \(virtual host in the connections' Cloud Connector properties must be manually entered\).
        > 
        > </td>
        > <td valign="top">
        > 
        > Enter the same virtual port in Cloud Connector and in the connection \(virtual port in the connections' Cloud Connector properties must be manually entered\).
        > 
        > </td>
        > </tr>
        > </table>
        > 
        > In the connection, you must enter virtual host and port in separate fields. Deriving virtual host and port is not supported in the connection because of the different virtual ports used in the two system mappings.

    2.  You need to specify the URL path \(*Resources*\):
        1.  Enter the service path of the SQL service endpoint on the SAP S/4HANA system. For example:`/sap/bc/sql/sql1/sap/s_privileged`.

        2.  Select the *WebSocket* option.



    For more information, see [Configure Cloud Connector](configure-cloud-connector-f289920.md).

-   In SAP S/4HANA, a business user and administrator must perform the following steps to prepare data federation with remote tables:

    1.  Consider the prerequisites and constraints that must be considered before using the SQL service.

        For more information, see [Prerequisites](https://help.sap.com/docs/ABAP_PLATFORM_NEW/b5670aaaa2364a29935f40b16499972d/d71ed17fe0294eceb5e5327585cdfac1.html) and [Constraints](https://help.sap.com/docs/ABAP_PLATFORM_NEW/b5670aaaa2364a29935f40b16499972d/e5e007357a794a3dad1925ef6acfb6f1.html) in the *ABAP Platform* documentation for your SAP S/4HANA system.

    2.  To expose CDS view entities using the SQL service, an SAP S/4HANA business user has created a service definition and a corresponding service binding of type SQL1 in the ABAP Development Tools. The service definition lists the set of CDS view entities that shall be exposed, and a service binding of type SQL for that service definition enables their exposure via the ABAP SQL Service.

        For more information, see [Creating a Service Definition and an SQL-Typed Service Binding](https://help.sap.com/docs/ABAP_PLATFORM_NEW/b5670aaaa2364a29935f40b16499972d/c1cf6c9796ad4fecb893672fd91e660d.html) in the *ABAP Platform* documentation for your SAP S/4HANA system.

    3.  To expose the SQL service to get privileged access to the CDS view entities with a communication user, a role is required.

        For more information, see [Creating a Role for Privileged Access](https://help.sap.com/docs/ABAP_PLATFORM_NEW/b5670aaaa2364a29935f40b16499972d/f3945f142ca24afdb68896584257e428.html) in the *ABAP Platform* documentation for your SAP S/4HANA system.



