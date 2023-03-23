<!-- loioc87d4b769d37410da697813034460a3d -->

# Importing SAP BW Queries – A Comparison of the Different Options

In SAP Datasphere, there are different ways to import SAP BW queries.

You may ask yourself, when to use which option. Here is a summary of the differences.

These are the different options to import a SAP BW query:

-   queries as InfoProviders using a SAP BW connection
-   queries as InfoProviders using a SAP ABAP connection
-   queries using a SAP BW/4HANA Model Transfer connection

In all three cases, remote tables are created.

These are the differences:

-   For both the SAP BW connection and the SAP ABAP connection, only queries as InfoProviders are supported. For this type of queries, there are some restrictions. For more information, see [Query as InfoProvider](https://help.sap.com/viewer/107a6e8a38b74ede94c833ca3b7b6f51/2021.00/en-US/4bc347cd494650e9e10000000a15822b.html).
-   The difference between the SAP BW connection and the SAP ABAP connection is, that the SAP BW connection is a subset of the SAP ABAP connection, being restricted to SAP BW as a source whereas the SAP ABAP connection is more comprehensive to other on-premise source systems.
-   When you use the SAP BW/4HANA Model Transfer connection, you can import standard analytic queries, and you don’t have to deal with the restrictions of queries as InfoProviders. But it is only available for SAP BW/4HANA, not for SAP BW.
-   For SAP BW, the SAP BW connection and the SAP ABAP connection can be used, but not the SAP BW/4HANA Model Transfer connection. This means for SAP BW, you can only import queries as InfoProviders.
-   For SAP BW/4HANA, you can use all three options: the SAP BW connection, the SAP ABAP connection, and the SAP BW/4HANA Model Transfer connection.
-   If you want to provide SAP BW/4HANA business semantics to SAP Datasphere, you can use connection type SAP BW/4HANA Model Import and import SAP BW/4HANA models based on analytic queries. During the import, the semantics of the underlying SAP BW/4HANA models are translated into native SAP Datasphere entities.

