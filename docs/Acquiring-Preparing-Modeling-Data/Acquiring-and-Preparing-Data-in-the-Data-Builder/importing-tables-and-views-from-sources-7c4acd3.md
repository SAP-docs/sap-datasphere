<!-- loio7c4acd33e39a451e99c87f0661772443 -->

# Importing Tables and Views from Sources

Import tables and views from a connection, Open SQL schema, HDI container or other source available in your space. 

SAP Datasphere provides various methods for importing data into your space:

-   *Repository Explorer* / *Data Builder* start page - Use the import wizards to:
    -   Import semantically-rich objects \(along with the objects they depend on\) from SAP S/4HANA, SAP BW∕4HANA, and SAP Datasphere, SAP BW Bridge connections \(see [Importing Entities with Semantics from SAP S/4HANA](importing-entities-with-semantics-from-sap-s-4hana-845fedb.md)\).
    -   Import remote tables from any connection \(see [Import Remote Tables](import-remote-tables-fd04efb.md)\).

-   E/R Model - Import tables into the space and add them to the E/R model diagram \(see [Import an Object from a Connection or Other Source](../import-an-object-from-a-connection-or-other-source-3e6f8f2.md) or [Import Multiple Objects from a Connection](../import-multiple-objects-from-a-connection-e720b13.md)\).
-   Graphical or SQL view - Import tables into the space and use them directly as sources in the view \(see [Add a Source to a Graphical View](../add-a-source-to-a-graphical-view-1eee180.md)\).

Imported tables are created as remote tables or local tables depending on the type of source:


<table>
<tr>
<th valign="top">

Source Type

</th>
<th valign="top">

Table Type

</th>
</tr>
<tr>
<td valign="top">

Connection \(see [Integrating Data via Connections](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/eb85e157ab654152bd68a8714036e463.html "Users with a space administrator or integrator role can create connections to SAP and non-SAP source systems, including cloud and on-premise systems and partner tools, and to target systems for outbound replication flows. Users with modeler roles can import data via connections for preparation and modeling in SAP Datasphere.") :arrow_upper_right:\)

</td>
<td valign="top">

Remote table - Data is federated by default

Use the tools in the *Remote* section in the table editor to control replication of data \(see [Replicate Remote Table Data](replicate-remote-table-data-7e258a7.md)\).

</td>
</tr>
<tr>
<td valign="top">

Open SQL schema \(see [Integrating Data via Database Users/Open SQL Schemas](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/3de55a78a4614deda589633baea28645.html "Users with a space administrator role can create database users to read data exposed by the space and to write data to Open SQL schemas attached to space, providing a secure method for exchanging data with the space via ODBC access to the run-time SAP HANA Cloud database.") :arrow_upper_right:\)

HDI container \([Exchanging Data with SAP HANA for SQL data warehousing HDI Containers](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/1aec7ca95af24208a61c1a444b249d95.html "Users with a space administrator role can use SAP HANA for SQL data warehousing to build calculation views and other SAP HANA Cloud HDI objects directly in the run-time SAP HANA Cloud database and then exchange data between HDI containers and SAP Datasphere spaces. SAP HANA for SQL data warehousing can be used to bring existing HDI objects into your SAP Datasphere environment, and to allow users familiar with the HDI tools to leverage advanced SAP HANA Cloud features.") :arrow_upper_right:\)

Partner tool \(see [Connections to Partner Tools](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/55da0faa34d448f28f47021e99e18351.html "Extend connectivity beyond SAP Datasphere standard remote connectivity and cover additional data sources that are available with partner tools.") :arrow_upper_right:\)

</td>
<td valign="top">

Local table

As these sources are already integrated into SAP Datasphere in staging tables next to your space, there is no need to replicate data.

</td>
</tr>
</table>

In addition to working with tables in the editor, you can also:

-   List, create, read, update, and delete them using the `datasphere` command line interface \(see [Manage Modeling Objects via the Command Line](https://help.sap.com/viewer/9b8363ae47c347de9a027c0e5567a37a/DEV_CURRENT/en-US/6f5c65f209004751aa48f9682ee2ec45.html "Users with a modeler role can use the datasphere command line interface to list, create, update, and delete modeling objects.") :arrow_upper_right:\).
-   Export and import them via the secure *Transport* app \(see [Transporting Content Between Tenants](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/df12666cf98e41248ef2251c564b0166.html "Users with an administrator or space administrator role can use the Transport app to transfer content between tenants via a private cloud storage area.") :arrow_upper_right:\).
-   Export and import them via CSN files \(see [Importing and Exporting Objects in CSN/JSON Files](../Creating-Finding-Sharing-Objects/importing-and-exporting-objects-in-csn-json-files-f8ff062.md)\).

> ### Note:  
> For connection types that allow to enable remote tables, two SAP HANA Cloud features are used today:
> 
> -   SAP HANA smart data integration \(SDI\), which is used in connections with *Data Provisioning* option *Data Provisioning Agent*
> 
> -   SAP HANA smart data access \(SDA\), which is used in connections with no *Data Provisioning* option or *Data Provisioning* option = *Cloud Connection*.
> 
> 
> For more information on these adapters, see [Connecting SAP HANA Cloud, SAP HANA Database to Remote Data Sources](https://help.sap.com/docs/HANA_CLOUD/db19c7071e5f4101837e23f06e576495/afa3769a2ecb407695908cfb4e3a9463.html)

When you import an object through any of these methods, it is added to the repository and is available for use by any user assigned to the space in:

-   The *Data Builder* start page.
-   The *Repository* tab of the *Source Browser* from which it can be added as a source for views and other objects \(see [Add Objects from the Repository](../add-objects-from-the-repository-13fcecd.md)\).

