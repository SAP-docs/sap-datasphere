<!-- loiob78ad208f8c4494489aabf97284679b6 -->

<link rel="stylesheet" type="text/css" href="../../css/sap-icons.css"/>

# Connect to Your Open SQL Schema

When you have created a database user, you can connect to your Open SQL schema with the SAP HANA database explorer or with other tools.



<a name="loiob78ad208f8c4494489aabf97284679b6__section_a51_yq1_q2c"/>

## Prerequisites

To connect to an Open SQL schema or to allow the space to access the open SQL schema, you must have a database user and a password \(see [Create a Database User](create-a-database-user-798e3fd.md)\).



<a name="loiob78ad208f8c4494489aabf97284679b6__section_efv_nx1_btb"/>

## Obtaining Your Open SQL Schema Connection Information

To obtain the host name, port, and user name required to connect to your Open SQL schema, click the <span class="FPA-icons-V3"></span> button for your user in the *Database Users* list.

For security reasons, the password is not displayed in this dialog. If you have forgotten your password, you can generate a new one by clicking *Request New Password*.



<a name="loiob78ad208f8c4494489aabf97284679b6__section_qqg_nx1_btb"/>

## Connecting with SAP HANA Database Explorer

To open your Open SQL schema directly in the SAP HANA database explorer from your space page, select your user in the *Database Users* list, and then click *Open Database Explorer*. You will need to enter your password in order to add your schema to the list of databases.

To browse the objects in your schema, expand its node, expand *Catalog*, and click on an object category. To browse the space schema, click *Choose Schema* and select the space schema in the list.

To import or export data, open the SQL console, or perform other actions on your schema, right-click it in the list of databases and select the appropriate command.

For detailed information about working with the SAP HANA database explorer, see the [SAP HANA Database Explorer](https://help.sap.com/docs/SAP_HANA_COCKPIT/e8d0ddfb84094942a9f90288cd6c05d3/7fa981c8f1b44196b243faeb4afb5793.html) guide in the *SAP HANA Cockpit* documentation.



<a name="loiob78ad208f8c4494489aabf97284679b6__section_tpz_px1_btb"/>

## Connecting with Third-Party Tools

You can connect to your Open SQL schema with third-party ETL or analytics tools, via ODBC or JDBC. You will need to download and install the SAP HANA client or the JDBC driver and provide your connection information.

For more information, see [Connecting to SAP HANA Cloud](https://help.sap.com/viewer/db19c7071e5f4101837e23f06e576495/latest/en-US/fc071cc431624642bfc09450fd84ca7e.html) in the *SAP HANA Cloud, SAP HANA Database* documentation.



<a name="loiob78ad208f8c4494489aabf97284679b6__section_kyr_k4p_btb"/>

## Working with Your Open SQL Schema

For information about importing data from cloud storage services, see [Importing and Exporting Data](https://help.sap.com/viewer/f9c5015e72e04fffa14d7d4f7267d897/latest/en-US/261937915fa5438ca545b8278b2979b7.html) in the *SAP HANA Cloud, SAP HANA Database* documentation.

If the SAP HANA Cloud script server is enabled \(see [Enable the SAP HANA Cloud Script Server on Your SAP Datasphere Tenant](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/287194276a7d4d778ec98fdde5f61335.html "You can enable the SAP HANA Cloud script server on your SAP Datasphere tenant to access the SAP HANA Automated Predictive Library (APL) and SAP HANA Predictive Analysis Library (PAL) machine learning libraries.") :arrow_upper_right: and your database user has the *Enable Automated Predictive Library and Predictive Analysis Library* option enabled, you can work with the SAP HANA Automated Predictive Library \(APL\) and SAP HANA Predictive Analysis Library \(PAL\) machine learning libraries.

For detailed information about using the machine learning libraries, see:

-   [SAP HANA Automated Predictive Library Developer Guide](https://help.sap.com/viewer/7223667230cb471ea916200712a9c682/2101/en-US)
-   [SAP HANA Cloud Predictive Analysis Library \(PAL\)](https://help.sap.com/viewer/319d36de4fd64ac3afbf91b1fb3ce8de/2020_03_QRC/en-US/c9eeed704f3f4ec39441434db8a874ad.html)

To list the privileges granted to your user, run the following statement in the SQL console:

```
select * from effective_privileges where user_name = current_user;
```

