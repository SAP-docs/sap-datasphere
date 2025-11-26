<!-- loioef2b2238154f4cd78a08df360447c1d5 -->

# Using ABAP SQL Services for Accessing ABAP-Managed Data

The ABAP SQL service provides SQL-level access to published CDS view entities for SAP Datasphere. You can use the service to replicate data with replication flows or to federate data with remote tables.



<a name="loioef2b2238154f4cd78a08df360447c1d5__section_bnj_jd4_2hc"/>

## Introduction to ABAP SQL Services

Developers in the ABAP environment can expose CDS view entities in an ABAP system for external consumption using SQL services. An SQL service is a standardized protocol of the Application Server ABAP providing SQL-level access to ABAP-managed database objects, such as CDS view entities, for consumers outside the system, such as SAP Datasphere. Using SQL services and the open database connectivity \(ODBC\) as a standard API for accessing databases, CDS view entities exposed by SQL services in SAP S/4HANA Cloud and SAP BTP ABAP environment can be used for data replication and federation in SAP Datasphere. For both consumption scenarios using the SQL service in SAP Datasphere, data federation and data replication, privileged data access needs to be enabled for communication users in the ABAP system.

For more information, see the *ABAP Cloud* documentation for *SAP S/4HANA Cloud Public Edition* or *SAP BTP ABAP environment* \(change the version on the SAP Help Portal page to find the documentation version that applies to your ABAP system\):

-   [Accessing ABAP-Managed Data from System-External Consumers](https://help.sap.com/docs/SAP_S4HANA_CLOUD/6aa39f1ac05441e5a23f484f31e477e7/4082fe1b66164eeb8aa41192166526af.html)
-   [Accessing ABAP-Managed Data from SAP Datasphere](https://help.sap.com/docs/abap-cloud/abap-integration-connectivity/data-replication?version=s4hana_cloud)
-   [Data Integration Patterns](https://help.sap.com/docs/abap-cloud/abap-integration-connectivity/data-integration-patterns?version=s4hana_cloud) \(for more information about the consumption scenarios and privileged access\)

> ### Note:  
> For SAP S/4HANA Cloud, this feature requires developer extensibility \(including ABAP development tools\), which is only available in a 3-system landscape. For more information, see the *SAP S/4HANA Cloud Public Edition* documentation:
> 
> -   [Developer Extensibility](https://help.sap.com/docs/SAP_S4HANA_CLOUD/6aa39f1ac05441e5a23f484f31e477e7/e1059ff581854a699f15734049f14293.html)
> -   [System Landscapes in SAP S/4HANA Cloud Public Edition](https://help.sap.com/docs/SAP_S4HANA_CLOUD/a630d57fc5004c6383e7a81efee7a8bb/aa60b129af7b4ce8ae052618c8315d29.html)



<a name="loioef2b2238154f4cd78a08df360447c1d5__section_qql_jmb_ccc"/>

## Data Replication With Replication Flows

In SAP S/4HANA Cloud, a business user and administrator must perform the following steps to prepare data replication with replication flows:

-   Check the prerequisites and constraints that must be considered before using the SQL service.

    For more information, see [Prerequisites and Constraints](https://help.sap.com/docs/abap-cloud/abap-integration-connectivity/prerequisites-and-constraints?version=s4hana_cloud) in the *ABAP Cloud* documentation. Note that for SAP Datasphere the ODBC driver installation is not required \(the driver is pre-installed on the SAP HANA database\).

-   To expose CDS view entities using the SQL service, an SAP S/4HANA Cloud business user has created a service definition and a corresponding service binding of type SQL1 in the ABAP Development Tools. The service definition lists the set of CDS view entities that shall be exposed, and a service binding of type SQL for that service definition enables their exposure via the ABAP SQL Service.

    In the *Enabled Operations* area of the service binding, the business user must select access type *REPLICATE* to enable data replication.

    For more information, see [Creating an SQL Service](https://help.sap.com/docs/abap-cloud/abap-integration-connectivity/creating-service-definition-and-sql-typed-service-binding?version=s4hana_cloud) in the *ABAP Cloud* documentation.

-   To expose the SQL service to get privileged access to the CDS view entities with a communication user, a communication arrangement is required. This involves the following steps:

    1.  An SAP S/4HANA Cloud business user has created a custom communication scenario in the ABAP Development Tools.

        When filling out the authorizations for authorization object `S_SQL_VIEW` in the communication scenario, note the following:

        -   In the SQL\_VIEWOP authorization field, select the option *REPLICATE* to allow replication on the specified views.


    2.  An administrator has created a communication system and user in the SAP Fiori launchpad of the ABAP environment.

        > ### Note:  
        > The same communication user must be added to all communication arrangements you're using for the connection.

    3.  An administrator has created a communication arrangement for exposing the SQL service in the SAP Fiori launchpad of the ABAP environment.


    For more information, see [Exposing the SQL Service with Privileged Access](https://help.sap.com/docs/abap-cloud/abap-integration-connectivity/exposing-sql-service-for-data-federation-and-replication-with-privileged-access?version=s4hana_cloud) in the *ABAP Cloud* documentation.

-   An administrator has created a communication arrangement for communication scenario SAP\_COM\_0532 in the SAP Fiori launchpad of the ABAP environment.

    For more information, see [Replication Flows](prepare-connectivity-to-sap-s-4hana-cloud-abb159e.md#loioabb159e027184c98a54fc1b2a88dd3f5__section_prereq_rf).


You can now create a connection to consume the ABAP SQL service for data replication with replication flows using the ABAP Pipeline Engine.



<a name="loioef2b2238154f4cd78a08df360447c1d5__section_y5d_b5q_bcc"/>

## Data Federation With Remote Tables

In SAP S/4HANA Cloud or SAP BTP, ABAP environment, a business user and administrator must perform the following steps to prepare data federation with remote tables:

1.  Check the prerequisites and constraints that must be considered before using the SQL service.

    For more information, see [Prerequisites and Constraints](https://help.sap.com/docs/abap-cloud/abap-integration-connectivity/prerequisites-and-constraints?version=s4hana_cloud) in the *ABAP Cloud* documentation. Note that for SAP Datasphere the ODBC driver installation is not required \(the driver is pre-installed on the SAP HANA database\).

2.  To expose CDS view entities using the SQL service, a business user must create a service definition and a corresponding service binding of type SQL1 in the ABAP Development Tools. The service definition lists the set of CDS view entities that shall be exposed, and a service binding of type SQL for that service definition enables their exposure via the ABAP SQL service.

    To enable federated access, the business user must select access type *SELECT* in the *Enabled Operations* area of the service binding.

    For more information, see [Creating an SQL Service](https://help.sap.com/docs/abap-cloud/abap-integration-connectivity/creating-service-definition-and-sql-typed-service-binding?version=s4hana_cloud) in the *ABAP Cloud* documentation.

3.  To expose the SQL service to get privileged access to the CDS view entities with a communication user, a communication arrangement is required. This involves the following steps:

    1.  An SAP S/4HANA Cloud business user has created a custom communication scenario in the ABAP Development Tools.

        When filling out the authorizations for authorization object `S_SQL_VIEW` in the communication scenario, note the following:

        -   On the *Sources* tab of the Data Builder view editors in SAP Datasphere, the service binding name from the *SQL\_SCHEMA* authorization field is visible as \(virtual\) schema.

        -   In the SQL\_VIEWOP authorization field, select the option *SELECT* to grant federated access.


    2.  An administrator has created a communication system and user in the SAP Fiori launchpad of the ABAP environment.

        > ### Note:  
        > The same communication user must be added to all communication arrangements you're using for the connection.

    3.  An administrator has created a communication arrangement for exposing the SQL service in the SAP Fiori launchpad of the ABAP environment.


    For more information, see [Exposing the SQL Service with Privileged Access](https://help.sap.com/docs/abap-cloud/abap-integration-connectivity/exposing-sql-service-for-data-federation-and-replication-with-privileged-access?version=s4hana_cloud) in the *ABAP Cloud* documentation.


You can now create a connection to consume the ABAP SQL service for data federation with remote tables using the ABAP SDA adapter in SAP HANA.

