<!-- loio00d5fe633e24435f8c2b331f7e101fd6 -->

# Previewing, Filtering and Reordering Remote Tables Data

You have imported a remote table and want to preview and reorganize the data for your needs.

What you can do to preview or reorganize your data depends on the connection and the adapter.

> ### Caution:  
> Previewing data from a remote table with a large data volume may overload your source system, resulting in an out-of-memory error.


<table>
<tr>
<th valign="top">

Connection Type

</th>
<th valign="top">

Adapter

</th>
<th valign="top">

Record Counts While Previewing

</th>
<th valign="top">

Sort Data

</th>
<th valign="top">

Filter Data

</th>
</tr>
<tr>
<td valign="top">

SAP ABAP

</td>
<td valign="top">

ABAP Adapter

For more information, see [SAP ABAP Connections](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/a75c1aacf951449ba3b740c7e46da3a9.html "Use an SAP ABAP connection to access data from SAP ABAP on-premise systems through RFC or to access data from cloud source systems such as SAP S/4HANA Cloud through Web Socket RFC.") :arrow_upper_right:.

</td>
<td valign="top">

Not supported

</td>
<td valign="top">

Not supported

</td>
<td valign="top">

Filtering is supported, but with some restrictions:

-   Filters can be applied with operators if they contain, =, != , empty.
-   Filters must be separated by AND operator with Include, Exclude



</td>
</tr>
<tr>
<td valign="top">

Cloud Data Integration

</td>
<td valign="top">

Cloud Data Integration \(CDI\) Adapter

For more information, see [Prepare Connectivity for Cloud Data Integration](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/b6fd8def1c00408e9c5e34efb897aa31.html "To be able to successfully validate and use a Cloud Data Integration connection for remote tables or data flows certain preparations have to be made.") :arrow_upper_right:.

</td>
<td valign="top">

Not supported

</td>
<td valign="top">

Supported

</td>
<td valign="top">

Supported

</td>
</tr>
<tr>
<td valign="top">

SAP Success factor, Generic Odata

</td>
<td valign="top">

OData

For more information, see [Prepare Connectivity for Generic OData](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/d9c43a2dd2b340c48e4e665967c853e8.html "To be able to successfully validate and use a connection to an OData service for remote tables or data flows certain preparations have to be made.") :arrow_upper_right:.

</td>
<td valign="top">

Not supported

</td>
<td valign="top">

Supported

</td>
<td valign="top">

Supported

</td>
</tr>
<tr>
<td valign="top">

Generic JDBC

</td>
<td valign="top">

CamelJdbcAdapter

For more information, see [Prepare Connectivity for Generic JDBC](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/648fabfc94ad4da7853ef9a4d284aeac.html "To be able to successfully validate and use a Generic JDBC connection for remote tables certain preparations have to be made.") :arrow_upper_right:.

</td>
<td valign="top">

Supported

</td>
<td valign="top">

Supported

</td>
<td valign="top">

Supported

</td>
</tr>
<tr>
<td valign="top">

SAP HANA

</td>
<td valign="top">

SAP HANA smart data integration

For more information, see [Connecting SAP HANA Cloud, SAP HANA Database to Remote Data Sources](https://help.sap.com/docs/HANA_CLOUD/db19c7071e5f4101837e23f06e576495/afa3769a2ecb407695908cfb4e3a9463.html)

</td>
<td valign="top">

Supported

</td>
<td valign="top">

Supported

</td>
<td valign="top">

Supported

</td>
</tr>
</table>

> ### Note:  
> In case your remote table has been shared from another space, some actions may be not possible. Again, it depends on the connection type and the adapters used.

For more information on remote tables and adapters, see [Monitoring Remote Tables](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/4dd95d7bff1f48b399c8b55dbdd34b9e.html "In the Remote Tables monitor, you can find a remote table monitor per space. Here, you can copy data from remote tables that have been deployed in your space into SAP Datasphere, and you can monitor the replication of the data. You can copy or schedule copying the full set of data from the source, or you can set up replication of data changes in real-time via change data capturing (CDC).") :arrow_upper_right:.

For more information on which connection types support data replication \(direct or scheduled replication\) and real-time replication, see [Integrating Data via Connections](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/eb85e157ab654152bd68a8714036e463.html "Users with a space administrator or integrator role can create connections to SAP and non-SAP source systems, including cloud and on-premise systems and partner tools, and to target systems for outbound replication flows. Users with modeler roles can import data via connections for preparation and modeling in SAP Datasphere.") :arrow_upper_right:.

