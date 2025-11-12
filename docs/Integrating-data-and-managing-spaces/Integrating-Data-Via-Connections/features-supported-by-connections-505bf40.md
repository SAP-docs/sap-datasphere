<!-- loio505bf400544846148cf51e5b6d731a8b -->

# Features Supported by Connections

Each connection type supports a defined set of features: remote tables, replication flows, data flows, and model import.

Depending on the connection type and the connection configuration, a connection can be used for one or more features:


<table>
<tr>
<th valign="top">

Feature

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Remote Tables 

</td>
<td valign="top">

Allows modelers to import tables from a source. During the import, the tables are deployed as remote tables. Depending on the connection type, you can use remote tables to:

-   directly access data in the source \(remote access\)

-   copy the full set of data \(snapshot or scheduled replication\)

-   copy data changes in real-time \(real-time replication\)


For more information, see:

-   [Importing Tables and Views from Sources](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/7c4acd33e39a451e99c87f0661772443.html "Import tables and views from a connection, Open SQL schema, HDI container or other source available in your space.") :arrow_upper_right:
-   [Monitoring Remote Tables](../Data-Integration-Monitor/monitoring-remote-tables-4dd95d7.md)
-   [Adapters, Data Access, and Replication](../Data-Integration-Monitor/monitoring-remote-tables-4dd95d7.md#loio4dd95d7bff1f48b399c8b55dbdd34b9e__section_ggc_fm2_vkb) 



</td>
</tr>
<tr>
<td valign="top">

Data Flows 

</td>
<td valign="top">

Allows modelers to use objects from a connected source when creating data flows to extract, transform and load data.

For more information, see [Creating a Data Flow](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/e30fd1417e954577baae3246ea470c3f.html "Create a data flow to move and transform data in an intuitive graphical interface. You can drag and drop sources from the Source Browser, join them as appropriate, add other operators to remove or create columns, aggregate data, and do Python scripting, before writing the data to the target table.") :arrow_upper_right:.

</td>
</tr>
<tr>
<td valign="top">

Model Import 

</td>
<td valign="top">

Allows modelers to import objects from any supporting SAP system with rich metadata and, if supported, with their dependencies. This way, you can leverage your existing investment in your customer system landscape without having to rebuild the objects manually.

For more information, see [Importing SAP BW∕4HANA Models](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/a3d4a2f91bea4810ba8839ff73577dac.html "You can import existing analytic queries from SAP BW∕4HANA into SAP Datasphere in order to build new models on top of them or enhance them.") :arrow_upper_right:.

</td>
</tr>
<tr>
<td valign="top">

Replication Flows 

</td>
<td valign="top">

Allows modelers to replicate data from multiple source objects from a connected source to a target including simple projection and mapping capabilities.

You can enable a single initial load or request initial and delta loads to load changes at regular intervals. It depends on the connection type if you can use the connection as source or target connection.

For more information, see [Creating a Replication Flow](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/25e2bd7a70d44ac5b05e844f9e913471.html "Create a replication flow to copy multiple data assets from a source to a target with support for delta loads.") :arrow_upper_right:.

</td>
</tr>
<tr>
<td valign="top">

API Tasks

</td>
<td valign="top">

Allows modelers to add API tasks to task chains. This feature is only available with *Generic HTTP* connections.

For more information, see:

-   [Run API Tasks in a Task Chain](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/9a8489ed7443436197fbd8b8ffba61ab.html "Run tasks in a task chain that use a REST-based API to access external systems.") :arrow_upper_right:
-   [Generic HTTP Connections](generic-http-connections-b79b865.md)



</td>
</tr>
</table>

> ### Note:  
> Some connection types, such as SAP S/4HANA Cloud and on-premise or SAP ABAP, support replication with both remote tables via Data Provisioning Agent \(SAP HANA Smart Data Integration\) and replication flows \(for on-premise systems via Cloud Connector\). Generally, for replication scenarios, we recommend to use replication flows.



<a name="loio505bf400544846148cf51e5b6d731a8b__section_dtx_v1p_tfc"/>

## Enabling Features in a Connection

To allow space users using a feature, the feature must be enabled in the connection configuration.

For information about which features are supported by which connection type and what prerequisites and connection properties are required to enable \(or disable\) a feature, see [Connection Types](connection-types-9456242.md).

