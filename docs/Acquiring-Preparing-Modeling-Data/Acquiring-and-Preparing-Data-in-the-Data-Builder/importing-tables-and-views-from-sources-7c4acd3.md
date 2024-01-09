<!-- loio7c4acd33e39a451e99c87f0661772443 -->

# Importing Tables and Views from Sources

Import tables and views from a connection, Open SQL schema, HDI container or other source available in your space. 

SAP Datasphere provides various methods for importing tables into your space:

-   Data Builder start page - Use the import wizards to:
    -   Import remote tables from any connection \(see [Import Remote Tables](import-remote-tables-fd04efb.md)\).
    -   Import objects from SAP Datasphere, SAP BW Bridge \(see [Importing Entities with Semantics from SAP BW∕4HANA or SAP BW Bridge](importing-entities-with-semantics-from-sap-bw-4hana-or-sap-bw-br-7bcd321.md)\).
    -   Import a table, view, or other object \(including, potentially, *Business Builder* objects\), along with all the objects it depends on from an SAP S/4HANA connection \(see [Importing Entities with Semantics from SAP S/4HANA](importing-entities-with-semantics-from-sap-s-4hana-845fedb.md)\).

-   E/R Model - Import tables into the space and add them to the E/R model diagram \(see [Import an Object from a Connection or Other Source](../import-an-object-from-a-connection-or-other-source-3e6f8f2.md) or [Import Multiple Objects from a Connection](../import-multiple-objects-from-a-connection-e720b13.md)\).
-   Graphical or SQL view - Import tables into the space and use them directly as sources in the view \(see [Add a Source](../add-a-source-1eee180.md)\).

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

Connection \(see [Integrating Data via Connections](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/eb85e157ab654152bd68a8714036e463.html "Connections provide access to data from a wide range of sources, cloud as well as on-premise sources, SAP as well as Non-SAP sources, and partner tools. They allow users assigned to a space to use objects from the connected source to acquire, prepare and access data from those sources in SAP Datasphere. In addition, you can use certain connections to define targets for replication flows.") :arrow_upper_right:\)

</td>
<td valign="top">

Remote table - Data is federated by default

Use the tools in the *Remote* section in the table editor to control replication of data \(see [Replicate Remote Table Data](replicate-remote-table-data-7e258a7.md)\).

</td>
</tr>
<tr>
<td valign="top">

Open SQL schema \(see [Integrating Data via Database Users/Open SQL Schemas](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/3de55a78a4614deda589633baea28645.html "Create a database user in your space to read and write directly to the SAP HANA Cloud database on which SAP Datasphere runs. Each database user has an Open SQL schema, which is attached to a space schema and provides a secure method for exchanging data with the space.") :arrow_upper_right:\)

HDI container \([Exchanging Data with SAP SQL Data Warehousing HDI Containers](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/1aec7ca95af24208a61c1a444b249d95.html "Use SAP SQL Data Warehousing to build calculation views and other SAP HANA Cloud HDI objects directly in your SAP Datasphere run-time database and then exchange data between your HDI containers and your SAP Datasphere spaces. SAP SQL Data Warehousing can be used to bring existing HDI objects into your SAP Datasphere environment, and to allow users familiar with the HDI tools to leverage advanced SAP HANA Cloud features.") :arrow_upper_right:\)

Partner tool \(see [Connections to Partner Tools](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/55da0faa34d448f28f47021e99e18351.html "Extend connectivity beyond SAP Datasphere standard remote connectivity and cover additional data sources that are available with partner tools.") :arrow_upper_right:\)

</td>
<td valign="top">

Local table

As these sources are already integrated into SAP Datasphere in staging tables next to your space, there is no need to replicate data.

</td>
</tr>
</table>

When you import an object through any of these methods, it is added to the repository and is available for use by any user assigned to the space in:

-   The *Data Builder* start page.
-   The *Repository* tab of the *Source Browser* from which it can be added as a source for views and other objects \(see [Add Objects from the Repository](../add-objects-from-the-repository-13fcecd.md)\).

