<!-- loioef2b2238154f4cd78a08df360447c1d5 -->

# Using ABAP SQL Services for Accessing Data from SAP S/4HANA Cloud

The ABAP SQL service provides SQL-level access to published CDS view entities for SAP Datasphere. You can use the service to replicate data with replication flows or to federate data with remote tables.

> ### Note:  
> This feature requires developer extensibility in SAP S/4HANA Cloud \(including ABAP development tools\), which is only available in a 3-system landscape. For more information, see the *SAP S/4HANA Cloud* documentation:
> 
> -   [Developer Extensibility](https://help.sap.com/docs/SAP_S4HANA_CLOUD/6aa39f1ac05441e5a23f484f31e477e7/e1059ff581854a699f15734049f14293.html)
> -   [System Landscapes in SAP S/4HANA Cloud](https://help.sap.com/docs/SAP_S4HANA_CLOUD/a630d57fc5004c6383e7a81efee7a8bb/aa60b129af7b4ce8ae052618c8315d29.html)

For both consumption scenarios using the SQL service, data federation and data replication, privileged data access needs to be enabled for communication users in SAP S/4HANA Cloud.

For more information about the consumption scenarios and privileged access, see [Data Integration Patterns](https://help.sap.com/docs/SAP_S4HANA_CLOUD/6aa39f1ac05441e5a23f484f31e477e7/96368bd086ff4f79933b078a6cf7feaa.html) in the *SAP S/4HANA Cloud* documentation.



<a name="loioef2b2238154f4cd78a08df360447c1d5__section_y5d_b5q_bcc"/>

## Data Federation With Remote Tables

In SAP S/4HANA Cloud, a business user and administrator must perform the following steps to prepare data federation with remote tables:

1.  There are some prerequisites and constraints that must be considered before using the SQL service.

    For more information, see [Prerequisites and Constraints](https://help.sap.com/docs/SAP_S4HANA_CLOUD/6aa39f1ac05441e5a23f484f31e477e7/5e8488149308423b9f8b2f2c8ef9c761.html) in the *SAP S/4HANA Cloud* documentation. Note that the information about the ODBC driver is not relevant for SAP Datasphere as a consumer of an exposed SQL service.

2.  To expose CDS view entities using the SQL service, an SAP S/4HANA Cloud business user has created a service definition and a corresponding service binding of type SQL1 in the ABAP Development Tools. The service definition lists the set of CDS view entities that shall be exposed, and a service binding of type SQL for that service definition enables their exposure via the ABAP SQL Service.

    In the *Enabled Operations* area of the service binding, the business user must select access type *SELECT* to enable federated access.

    For more information, see [Creating a Service Definition and an SQL-Typed Service Binding](https://help.sap.com/docs/SAP_S4HANA_CLOUD/6aa39f1ac05441e5a23f484f31e477e7/c1cf6c9796ad4fecb893672fd91e660d.html) in the *SAP S/4HANA Cloud* documentation.

3.  To expose the SQL service to get privileged access to the CDS view entities with a communication user, a communication arrangement is required. This involves the following steps:

    1.  An SAP S/4HANA Cloud business user has created a custom communication scenario in the ABAP Development Tools.

        When filling out the authorizations for authorization object `S_SQL_VIEW` in the communication scenario, note the following:

        -   On the *Sources* tab of the Data Builder view editors in SAP Datasphere, the service binding name from the *SQL\_SCHEMA* authorization field is visible as \(virtual\) schema.

        -   In the SQL\_VIEWOP authorization field, select the option *SELECT* to grant federated access.


    2.  An administrator has created a communication system and user in the SAP Fiori launchpad of the ABAP environment.

    3.  An administrator has created a communication arrangement for exposing the SQL service in the SAP Fiori launchpad of the ABAP environment.


    For more information about the above steps, see [Exposing the SQL Service for Data Federation and Replication with Privileged Access](https://help.sap.com/docs/SAP_S4HANA_CLOUD/6aa39f1ac05441e5a23f484f31e477e7/70b2fc2a9e37475b993d4e6fd6d3eb07.html) in the *SAP S/4HANA Cloud* documentation.




<a name="loioef2b2238154f4cd78a08df360447c1d5__section_qql_jmb_ccc"/>

## Data Replication With Replication Flows

In SAP S/4HANA Cloud, a business user and administrator must perform the following steps to prepare data replication with replication flows:

1.  There are some prerequisites and constraints that must be considered before using the SQL service.

    For more information, see [Prerequisites and Constraints](https://help.sap.com/docs/SAP_S4HANA_CLOUD/6aa39f1ac05441e5a23f484f31e477e7/5e8488149308423b9f8b2f2c8ef9c761.html) in the *SAP S/4HANA Cloud* documentation. Note that the information about the ODBC driver is not relevant for SAP Datasphere as a consumer of an exposed SQL service.

2.  To expose CDS view entities using the SQL service, an SAP S/4HANA Cloud business user has created a service definition and a corresponding service binding of type SQL1 in the ABAP Development Tools. The service definition lists the set of CDS view entities that shall be exposed, and a service binding of type SQL for that service definition enables their exposure via the ABAP SQL Service.

    In the *Enabled Operations* area of the service binding, the business user must select access type *REPLICATE* to enable data replication.

    For more information, see [Creating a Service Definition and an SQL-Typed Service Binding](https://help.sap.com/docs/SAP_S4HANA_CLOUD/6aa39f1ac05441e5a23f484f31e477e7/c1cf6c9796ad4fecb893672fd91e660d.html) in the *SAP S/4HANA Cloud* documentation.

3.  To expose the SQL service to get privileged access to the CDS view entities with a communication user, a communication arrangement is required. This involves the following steps:

    1.  An SAP S/4HANA Cloud business user has created a custom communication scenario in the ABAP Development Tools.

        When filling out the authorizations for authorization object `S_SQL_VIEW` in the communication scenario, note the following:

        -   In the SQL\_VIEWOP authorization field, select the option *REPLICATE* to allow replication on the specified views.


    2.  An administrator has created a communication system and user in the SAP Fiori launchpad of the ABAP environment.

    3.  An administrator has created a communication arrangement for exposing the SQL service in the SAP Fiori launchpad of the ABAP environment.


    For more information about the above steps, see [Exposing the SQL Service for Data Federation and Replication with Privileged Access](https://help.sap.com/docs/SAP_S4HANA_CLOUD/6aa39f1ac05441e5a23f484f31e477e7/70b2fc2a9e37475b993d4e6fd6d3eb07.html) in the *SAP S/4HANA Cloud* documentation.

4.  An administrator has created a communication arrangement for communication scenario SAP\_COM\_0532 in the SAP Fiori launchpad of the ABAP environment.

    For more information, see [Creating a Communication Arrangement to Enable Replication Flows in SAP Datasphere](https://help.sap.com/docs/SAP_S4HANA_CLOUD/6aa39f1ac05441e5a23f484f31e477e7/96368bd086ff4f79933b078a6cf7feaa.html) in the *SAP S/4HANA Cloud* documentation.


> ### Note:  
> Note that the same communication user must be added to all communication arrangements.

For more information about using SQL services to replicate ABAP-managed data to SAP Datasphere, see [Data Consumption Using SAP Datasphere](https://help.sap.com/docs/SAP_S4HANA_CLOUD/6aa39f1ac05441e5a23f484f31e477e7/ec312dd3e39f401b84681c53adc08ad8.html) in the *SAP S/4HANA Cloud* documentation.

