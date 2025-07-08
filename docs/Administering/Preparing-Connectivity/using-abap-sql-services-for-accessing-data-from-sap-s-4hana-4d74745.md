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
> -   Data federation with remote tables using the ABAP SQL service is supported for SAP Logon connection type *Application Server* and basic authentication with *User Name and Password*.
> 
> -   When a connection is configured for using the ABAP SQL service for data federation with remote tables, you can't use the same connection for model import.



Perform the following steps to prepare data federation with remote tables:

-   Configure Cloud Connector to use the ABAP SQL service \(see [Configure Cloud Connector](configure-cloud-connector-f289920.md)\), paying particular attention to the following configuration steps:

    1.  When adding the system mapping to the SAP S/4HANA system, select *HTTPS* protocol.

        > ### Note:  
        > When you want to use a connection for both data or replication flows and remote tables, you need to create two system mapping entries in the Cloud Connector considering the following:
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
        > Host
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
        > <td valign="top" rowspan="2">
        > 
        > Enter the same host for both system mapping entries.
        > 
        > </td>
        > <td valign="top" rowspan="2">
        > 
        > Enter the same virtual host for both system mapping entries.
        > 
        > Also, the virtual host must be the same in the Cloud Connector system mapping and in the connection's Cloud Connector properties.
        > 
        > </td>
        > <td valign="top">
        > 
        > The virtual port is derived from the instance number \(system number\) entered in the system mapping: ***sapgw*<system number\>****.
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
        > HTTPS
        > 
        > </td>
        > <td valign="top">
        > 
        > Enter the same virtual port in the Cloud Connector system mapping and in the connection's Cloud Connector properties.
        > 
        > </td>
        > </tr>
        > </table>
        > 
        > In the SAP Datasphere *Connections* app, you must enter the virtual port for the HTTPS protocol and the virtual host in separate fields. Deriving virtual host and port is not supported in the *Connections* app because of the different virtual ports used in the two system mappings.

    2.  When adding resources, specify the URL path:
        1.  Enter the service path of the SQL service endpoint on the SAP S/4HANA system. For example:`/sap/bc/sql/sql1/sap/s_privileged`.

        2.  Select the *Upgrade Allowed* option.

            > ### Note:  
            > In older Cloud Connector versions, the option might appear as *WebSocket* or *WebSocket Upgrade*.



    For more information, see:

    -   [Configure Cloud Connector](configure-cloud-connector-f289920.md)
    -   [Configure Access Control \(HTTP\)](https://help.sap.com/docs/connectivity/sap-btp-connectivity-cf/configure-access-control-http) in the *SAP BTP Connectivity* documentation

    .

-   In SAP S/4HANA, a business user and administrator must perform the following steps to prepare data federation with remote tables:

    1.  Consider the prerequisites and constraints that must be considered before using the SQL service.

        For more information, see [Prerequisites](https://help.sap.com/docs/ABAP_PLATFORM_NEW/b5670aaaa2364a29935f40b16499972d/d71ed17fe0294eceb5e5327585cdfac1.html) and [Constraints](https://help.sap.com/docs/ABAP_PLATFORM_NEW/b5670aaaa2364a29935f40b16499972d/e5e007357a794a3dad1925ef6acfb6f1.html) in the *ABAP Platform* documentation for your SAP S/4HANA system.

    2.  To expose CDS view entities using the SQL service, an SAP S/4HANA business user has created a service definition and a corresponding service binding of type SQL1 in the ABAP Development Tools. The service definition lists the set of CDS view entities that shall be exposed, and a service binding of type SQL for that service definition enables their exposure via the ABAP SQL Service.

        For more information, see [Creating a Service Definition and an SQL-Typed Service Binding](https://help.sap.com/docs/ABAP_PLATFORM_NEW/b5670aaaa2364a29935f40b16499972d/c1cf6c9796ad4fecb893672fd91e660d.html) in the *ABAP Platform* documentation for your SAP S/4HANA system.

    3.  To expose the SQL service to get privileged access to the CDS view entities with a communication user, a role is required.

        For more information, see [Creating a Role for Privileged Access](https://help.sap.com/docs/ABAP_PLATFORM_NEW/b5670aaaa2364a29935f40b16499972d/f3945f142ca24afdb68896584257e428.html) in the *ABAP Platform* documentation for your SAP S/4HANA system.



