<!-- loio7c4acd33e39a451e99c87f0661772443 -->

# Importing Tables and Views from Sources

Import tables and views from a connection, Open SQL schema, HDI container or other source available in your space. 

SAP Datasphere provides various methods for importing tables into your space:

-   Data Builder start page - Use the import wizards to:
    -   Import remote tables from any connection \(see [Import Remote Tables](import-remote-tables-fd04efb.md)\).
    -   Import objects from SAP Datasphere, SAP BW Bridge \(see [Using SAP Datasphere, SAP BW Bridge in SAP Datasphere](https://help.sap.com/viewer/07fda46007d24ff7b8af36b26f9b9634/cloud/en-US/b2a2df3c588849a494295aff0aa698a0.html "SAP Datasphere, SAP BW bridge enables you to use SAP BW functionality in the public cloud, to convert SAP BW∕4HANA and SAP BW models into SAP BW bridge models, and to import SAP BW bridge models into SAP Datasphere.") :arrow_upper_right:\).
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

Connection \(see [Integrating Data via Connections](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/eb85e157ab654152bd68a8714036e463.html "Connections provide access to data from a wide range of sources, cloud as well as on-premise sources, SAP as well as Non-SAP sources, and partner tools. They allow space members to use objects from the connected source to acquire, prepare and access data from those sources in SAP Datasphere. To connect to different sources, SAP Datasphere provides different connection types.") :arrow_upper_right:\)



</td>
<td valign="top">

Remote table - Data is federated by default

Use the tools in the *Remote* section in the table editor to control replication of data \(see [Replicate Remote Table Data](replicate-remote-table-data-7e258a7.md)\).



</td>
</tr>
<tr>
<td valign="top">

Open SQL schema \(see [Integrating Data via Database Users/Open SQL Schemas](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/3de55a78a4614deda589633baea28645.html "Create a database user in your space to read and write directly to the SAP HANA Cloud database on which SAP Datasphere runs. Each database user has an Open SQL schema, which is attached to a space schema and provides a secure method for exchanging data with the space.") :arrow_upper_right:\)

HDI container \([Exchanging Data with SAP SQL Data Warehousing HDI Containers](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/1aec7ca95af24208a61c1a444b249d95.html "You can enable SAP SQL Data Warehousing on your SAP Datasphere tenant to exchange data between your HDI containers and your SAP Datasphere spaces without the need for data movement.") :arrow_upper_right:\)

Partner tool \(see [Connections to Partner Tools](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/55da0faa34d448f28f47021e99e18351.html "Extend connectivity beyond SAP Datasphere standard remote connectivity and cover additional data sources that are available with partner tools.") :arrow_upper_right:\)



</td>
<td valign="top">

Local table

As these sources are already integrated into SAP Datasphere in staging tables next to your space, there is no need to replicate data.



</td>
</tr>
</table>

When you import an object through any of these methods, it is added to the repository and is available for use by any space member in:

-   The *Data Builder* start page.
-   The *Repository* tab of the *Source Browser* from which it can be added as a source for views and other objects \(see [Add Objects from the Repository](../add-objects-from-the-repository-13fcecd.md)\).

