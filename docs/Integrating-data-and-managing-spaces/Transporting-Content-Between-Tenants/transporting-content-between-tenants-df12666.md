<!-- loiodf12666cf98e41248ef2251c564b0166 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Transporting Content Between Tenants

Users with the *DW Administrator* or *DW Space Administrator* role can use the *Transport* app to transfer content between tenants via a private cloud storage area.

The following object types can be exported and imported via the <span class="FPA-icons"></span> \(*Transport*\) app:


<table>
<tr>
<th valign="top">

Object Type

</th>
<th valign="top">

Details

</th>
</tr>
<tr>
<td valign="top">

Connections

See [Create a Connection](../Integrating-Data-Via-Connections/create-a-connection-c216584.md).

</td>
<td valign="top">

The definition of a connection does not have dependencies on any other objects.

</td>
</tr>
<tr>
<td valign="top">

Remote Tables

See [Import Remote Tables](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/fd04efbac29c44fb8cfeaf2166b3d882.html "Import remote tables from a connection into your space directly from the Data Builder start page or the Repository Explorer.") :arrow_upper_right:.

</td>
<td valign="top">

The definition of a remote table contains information about its connection.

</td>
</tr>
<tr>
<td valign="top">

Local Tables

See [Creating a Local Table](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/2509fe4d86aa472b9858164b55b38077.html "Create a table to contain data by defining its column structure. Tables created in SAP Datasphere can be filled with data from a CSV file or via a data flow. You can also import tables from a connection or a CSN file.") :arrow_upper_right:.

</td>
<td valign="top">

The definition of a local table contains the structure of the table only, and does not have dependencies on any other objects.

</td>
</tr>
<tr>
<td valign="top">

Flows

See [Creating a Data Flow](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/e30fd1417e954577baae3246ea470c3f.html "Create a data flow to move and transform data in an intuitive graphical interface. You can drag and drop sources from the Source Browser, join them as appropriate, add other operators to remove or create columns, aggregate data, and do Python scripting, before writing the data to the target table.") :arrow_upper_right:, [Creating a Replication Flow](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/25e2bd7a70d44ac5b05e844f9e913471.html "Create a replication flow if you want to copy multiple data assets from the same source to the same target in a fast and easy way and do not require complex projections.") :arrow_upper_right:, and [Creating a Transformation Flow](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/f7161e6c20204672ac4a6d90c81762e4.html "Create a transformation flow to load data from one or more source tables, apply transformations (such as a join), and output the result in a target table. You can load a full set of data from one or more source tables to a target table. You can also load delta changes (including deleted records) from one source table to a target table.") :arrow_upper_right:.

</td>
<td valign="top">

The definition of a data flow, replication flow, or transformation flow contains the definitions of all its sources and its target table. When you export a flow, these objects are exported too.

</td>
</tr>
<tr>
<td valign="top">

Views

See [Creating a Graphical View](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/27efb479c4814252964d3fbc6ca2dfc3.html "Create a view to query sources in an intuitive graphical interface. You can drag and drop sources from the Source Browser, join them as appropriate, add other operators to remove or create columns and filter or aggregate data, and specify measures and other aspects of your output structure in the output node.") :arrow_upper_right: and [Creating an SQL View](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/81920e4d583f45fd8761c662d3c8abab.html "Create a view to query sources in a powerful SQL editor. You can choose between writing a standard SQL query using SELECT statements and operators such as JOIN and UNION, or use SQLScript to produce a table function. You can drag sources from the Source Browser, and specify measures and other aspects of your output structure in the side panel.") :arrow_upper_right:.

</td>
<td valign="top">

The definition of a view contains the definitions of all its sources and any used data access controls. When you export a view, these objects are exported too.

</td>
</tr>
<tr>
<td valign="top">

Intelligent Lookups

See [Creating an Intelligent Lookup](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/8f29f801faea4d48816d0339777f9d16.html "Create an intelligent lookup to merge data from two entities even if there are problems joining them. Intelligent lookup offers a business-centric, interactive data harmonization environment for subject matter experts.") :arrow_upper_right:.

</td>
<td valign="top">

The definition of an intelligent lookup contains the definitions of its input and lookup entities. When you export an intelligent lookup, these entities are exported too.

</td>
</tr>
<tr>
<td valign="top">

Analytic Models

See [Creating an Analytic Model](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/e5fbe9e2cb93484dab8b1963145e565f.html "Create an analytic model as a basis for consumption in SAP Analytics Cloud.") :arrow_upper_right:.

</td>
<td valign="top">

The definition of an analytic model contains the definitions of its fact and dimension sources. When you export an analytic model, these entities are exported too.

</td>
</tr>
<tr>
<td valign="top">

E/R Models

See [Creating an Entity-Relationship Model](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/a91c042549fb497384e756d5f5c71fde.html "Create an E/R model to import, visualize, edit, and deploy multiple data entities (tables and views) together. You can use an E/R model to better understand a subset of the entities in your space, and to communicate this information to other stakeholders.") :arrow_upper_right:.

</td>
<td valign="top">

The definition of an E/R model does not include the objects that it visualizes as dependencies. These visualized objects must be selected manually.

</td>
</tr>
<tr>
<td valign="top">

Data Access Controls

See [Securing Data with Data Access Controls](../Data-Access-Control/securing-data-with-data-access-controls-a032e51.md).

</td>
<td valign="top">

The definition of a data access control contains the definition of its permissions entity. When you export a data access control, the permissions entity is exported too.

</td>
</tr>
<tr>
<td valign="top">

Task Chains

See [Creating a Task Chain](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/d1afbc2b9ee84d44a00b0b777ac243e1.html "Group multiple tasks into a task chain and run them manually once, or periodically, through a schedule. You can create linear task chains in which one task is run after another. Or, you can create task chains in which individual tasks are run in parallel and successful continuation of the entire task chain run depends on whether ANY or ALL parallel tasks are completed successfully. In addition, when creating or editing a task chain, you can also set up email notification for deployed task chains to notify selected users of task chain completion.") :arrow_upper_right:.

</td>
<td valign="top">

The definition of a task chain contains the definition of all the objects that it automates. When you export a task chain, these objects are exported too.

</td>
</tr>
<tr>
<td valign="top">

Business Entities / Business Entity Versions

See [Creating a Business Entity](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/c912cdc1537d4efbb24b08327ea68918.html "You use business entities to build your consumption model for analysis and reporting.") :arrow_upper_right:.

</td>
<td valign="top">

The definition of a business entity contains all its versions \(which are also listed separately\), along with the definition of its source data entity and any authorization scenarios. When you export a business entity \(or one of its versions\), these objects are exported too.

</td>
</tr>
<tr>
<td valign="top">

Fact Models

See [Creating a Fact Model](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/5bbd14a328b549b2b53fce830ea25c15.html "Fact models are reusable models you can use to streamline the creation of other models within the same business context.") :arrow_upper_right:.

</td>
<td valign="top">

The definition of a fact model contains all its versions \(which are also listed separately\), along with the definition of all its source fact models and business entities. When you export a fact model \(or one of its versions\), these objects are exported too.

</td>
</tr>
<tr>
<td valign="top">

Consumption Models

See [Creating a Consumption Model](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/337fa99de4a44700ba49e2214a1f3349.html "Consumption models are the basis to consume your data.") :arrow_upper_right:.

</td>
<td valign="top">

The definition of a consumption model contains all its perspectives \(which are also listed separately\), along with the definition of all its source fact models and business entities. When you export a consumption model \(or one of its perspectives\), these objects are exported too.

You can deselect individual perspectives to exclude them from export. When overwriting a consumption model during an import, any perspectives excluded from the package will be deleted.

</td>
</tr>
<tr>
<td valign="top">

Authorization Scenarios

See [Creating an Authorization Scenario](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/167c05c673dc4715baba8d5d305abb1e.html "Authorization scenarios help you control data access for business entities leveraging data access controls.") :arrow_upper_right:.

</td>
<td valign="top">

The definition of an authorization scenario contains the definition of its data access control. When you export an authorization scenario, the data access control is exported too.

</td>
</tr>
</table>

> ### Note:  
> Only local and remote tables, views, data flows, and E/R models can be selected for exporting in SAP Datasphere tenants provisioned prior to version 2021.03. While objects created in SAP Datasphere tenants provisioned prior to version 2021.03 can be transported to tenants provisioned after that date, transport of objects in the other direction is not possible.

> ### Note:  
> You can also export certain content from and import content to your space via:
> 
> -   *Export to CSN/JSON File* buttons in selected *Data Builder* editors \(see [Importing and Exporting Objects in CSN/JSON Files](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/f8ff0628c9fc49229740ffcd4d20e9aa.html "You can use the tools in certain Data Builder editors to import objects to and export objects from your space.") :arrow_upper_right:\).
> -   The `datasphere` command line interface \(see [Importing and Exporting Objects via the Command Line](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/649465700ff14cd3ab7aebd72f370115.html "You can use the SAP Datasphere command line interface, datasphere, to import objects to and export objects from your space.") :arrow_upper_right:\).

For information about importing business content in the form of end-to-end business scenarios for specific industries and lines of business provided by SAP and its partners via the <span class="FPA-icons"></span> \(*Content Network*\) app, see [Importing SAP and Partner Business Content from the Content Network](../importing-sap-and-partner-business-content-from-the-content-network-400078d.md).

