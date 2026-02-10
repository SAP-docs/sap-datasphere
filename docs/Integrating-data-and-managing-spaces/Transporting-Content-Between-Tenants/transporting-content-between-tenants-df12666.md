<!-- loiodf12666cf98e41248ef2251c564b0166 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Transporting Content Between Tenants

Users with an administrator or space administrator role can use the *Transport* app to transfer content between tenants via a private cloud storage area.

This topic contains the following sections:

-   [Introduction to Content Transport](transporting-content-between-tenants-df12666.md#loiodf12666cf98e41248ef2251c564b0166__intro)
-   [Create One-Off Manual Transport Packages](transporting-content-between-tenants-df12666.md#loiodf12666cf98e41248ef2251c564b0166__one-off)
-   [Model Transport Packages for Repeatable Export](transporting-content-between-tenants-df12666.md#loiodf12666cf98e41248ef2251c564b0166__model)
-   [Import Transport Packages](transporting-content-between-tenants-df12666.md#loiodf12666cf98e41248ef2251c564b0166__import)
-   [Automate and Schedule Package Imports with SAP Cloud Transport Management](transporting-content-between-tenants-df12666.md#loiodf12666cf98e41248ef2251c564b0166__automate)
-   [Monitor Transports](transporting-content-between-tenants-df12666.md#loiodf12666cf98e41248ef2251c564b0166__monitor)
-   [Objects and Dependencies](transporting-content-between-tenants-df12666.md#loiodf12666cf98e41248ef2251c564b0166__objects)



<a name="loiodf12666cf98e41248ef2251c564b0166__intro"/>

## Introduction to Content Transport

Organizations typically work with three tenants to safely develop, test, and deploy content:

-   Development \("Dev"\) Tenant - Where data ingestion, preparation, and exposure is modeled and tables, views, flows, analytic models, and other objects are created.
-   Test Tenant - Where the prepared content is transported to be rigorously tested.
-   Production \("Prod"\) Tenant - Where the tested content is transported to be used by the organization's data analysts and other stakeholders.

The *Transport* apps allow you to safely and securely package and move content from the `Dev` tenant to the `Test` tenant and, once a release decision has been made, on to the `Prod` tenant.

> ### Note:  
> You can also export content from and import content to your space via:
> 
> -   *Export to CSN/JSON File* buttons in selected *Data Builder* editors \(see [Importing and Exporting Objects in CSN/JSON Files](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/f8ff0628c9fc49229740ffcd4d20e9aa.html "You can use the tools in certain Data Builder editors to import objects to and export objects from your space.") :arrow_upper_right:\).
> -   The `datasphere` command line interface `objects` commands \(see [Manage Modeling Objects and Tasks via the Command Line](https://help.sap.com/viewer/d0ecd6f297ac40249072a44df0549c1a/cloud/en-US/6f5c65f209004751aa48f9682ee2ec45.html "Users with a modeler role can use the datasphere command line interface to list, create, update, and delete modeling objects.") :arrow_upper_right:\).



<a name="loiodf12666cf98e41248ef2251c564b0166__one-off"/>

## Create One-Off Manual Transport Packages

The simplest way to export content is to use the *Transport* \> *Export* editor, which allows you to add objects to a package, specify which tenants can access it, and export it to private cloud storage for future import.

For more information, see [Exporting Content for Sharing with Other Tenants](exporting-content-for-sharing-with-other-tenants-44e775c.md).



<a name="loiodf12666cf98e41248ef2251c564b0166__model"/>

## Model Transport Packages for Repeatable Export

You can model your packages and their dependencies in the *Transport* \> *Packages* editor. A package modeled in this way allows you to persist your object selections, and re-export the package at any time, allowing you to easily ensure that your target tenants always have access to the most up-to-date version of each object.

Each modeled package can contain only objects from one space and each object can belong to only one package, but you can specify dependencies to other packages \(including packages in other spaces\) to ensure that all required objects are exported together every time.

This export process requires that all dependencies are resolved before export, offers semantic versioning for major, minor, and patch releases, and supports transporting data in local tables in certain circumstances.

For more information, see [Creating Packages to Export](creating-packages-to-export-24aba84.md).



<a name="loiodf12666cf98e41248ef2251c564b0166__import"/>

## Import Transport Packages

You can import any package made available to your tenant via the *Transport* \> *Import* editor.

For more information, see [Importing Content from Another Tenant](importing-content-from-another-tenant-b607a12.md).

> ### Note:  
> For information about importing business content in the form of end-to-end business scenarios for specific industries and lines of business provided by SAP and its partners via the <span class="FPA-icons-V3"></span> \(*Semantic Onboarding*\) app, see [Importing SAP and Partner Business Content from the Content Network](../importing-sap-and-partner-business-content-from-the-content-network-400078d.md).



<a name="loiodf12666cf98e41248ef2251c564b0166__automate"/>

## Automate and Schedule Package Imports with SAP Cloud Transport Management

You can integrate your SAP Datasphere tenants to SAP Cloud Transport Management, a separate BTP service, which provides support for:

-   Scheduling imports
-   Central management of imports to all your SAP Datasphere tenants
-   Coordinated transport of related SAP Analytics Cloud and other service packages
-   Improved governance and audit trails
-   Optional integration with SAP Cloud ALM

For more information, see [Transporting Content Through SAP Cloud Transport Management](transporting-content-through-sap-cloud-transport-management-0538398.md).



<a name="loiodf12666cf98e41248ef2251c564b0166__monitor"/>

## Monitor Transports

You can use the *Transport* \> *Monitor* page to review the status and summary of all import and export jobs on your tenant.

For more information, see [Monitoring Transport Jobs](monitoring-transport-jobs-fa9015c.md).



<a name="loiodf12666cf98e41248ef2251c564b0166__objects"/>

## Objects and Dependencies

The following object types can be exported and imported via the <span class="FPA-icons-V3"></span> \(*Transport*\) app:

> ### Note:  
> With limited exceptions, object definitions only can be transported between SAP Datasphere tenants via the <span class="FPA-icons-V3"></span> \(*Transport*\) app. For information about including local table data in your package, see [Transporting Local Table Data](transporting-local-table-data-9ec1c3c.md).


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

See [Import Remote Tables](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/fd04efbac29c44fb8cfeaf2166b3d882.html "Import remote tables from a connection into your space directly from the Data Builder start page or the Repository Explorer.") :arrow_upper_right:.

</td>
<td valign="top">

The definition of a remote table contains information about its connection.

</td>
</tr>
<tr>
<td valign="top">

Local Tables

See [Creating a Local Table](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/2509fe4d86aa472b9858164b55b38077.html "Create a table and define columns to receive data.. You can add data from a flow or a CSV file, or import tables from a connection or a CSN file.") :arrow_upper_right:.

</td>
<td valign="top">

The definition of a local table without delta capture contains the structure of the table only, and does not have dependencies on any other objects. The definition of a local table with delta capture enabled contains the definition of an additional internal table with the suffix `_Delta`. When you export a table with delta capture enabled, this table is exported too.

</td>
</tr>
<tr>
<td valign="top">

Flows

See [Creating a Data Flow](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/e30fd1417e954577baae3246ea470c3f.html "Create a data flow to move and transform data in an intuitive graphical interface. You can drag and drop sources from the Source Browser, join them as appropriate, add other operators to remove or create columns, aggregate data, and do Python scripting, before writing the data to the target table.") :arrow_upper_right:, [Creating a Replication Flow](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/25e2bd7a70d44ac5b05e844f9e913471.html "Create a replication flow to copy multiple data assets from a source to a target with support for delta loads.") :arrow_upper_right:, and [Creating a Transformation Flow](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/f7161e6c20204672ac4a6d90c81762e4.html "Create a transformation flow to load data from one or more sources, apply transformations (such as a join), and output the result in a target table. You can load a full set of data from one or more sources to a target table. You can add local tables and views, Open SQL schema objects, and also remote tables located in BW Bridge spaces. You can also load delta changes (including deleted records) from one source table to a target table.") :arrow_upper_right:.

</td>
<td valign="top">

The definition of a data flow, replication flow, or transformation flow contains the definitions of all its sources and its target table. When you export a flow, these objects are exported too.

</td>
</tr>
<tr>
<td valign="top">

Views

See [Creating a Graphical View](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/27efb479c4814252964d3fbc6ca2dfc3.html "Create a view to query sources in an intuitive graphical interface. You can drag and drop sources from the Source Browser, join them as appropriate, add other operators to remove or create columns and filter or aggregate data, and specify measures and other aspects of your output structure in the output node.") :arrow_upper_right: and [Creating an SQL View](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/81920e4d583f45fd8761c662d3c8abab.html "Create a view to query sources in a powerful SQL editor. You can choose between writing a standard SQL query using SELECT statements and operators such as JOIN and UNION, or use SQLScript to produce a table function. You can drag sources from the Source Browser, and specify measures and other aspects of your output structure in the side panel.") :arrow_upper_right:.

</td>
<td valign="top">

The definition of a view contains the definitions of all its sources and any used data access controls. When you export a view, these objects are exported too.

</td>
</tr>
<tr>
<td valign="top">

Intelligent Lookups

See [Creating an Intelligent Lookup](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/8f29f801faea4d48816d0339777f9d16.html "Create an intelligent lookup to merge data from two entities even if there are problems joining them. Intelligent lookup offers a business-centric, interactive data harmonization environment for subject matter experts.") :arrow_upper_right:.

</td>
<td valign="top">

The definition of an intelligent lookup contains the definitions of its input and lookup entities. When you export an intelligent lookup, these entities are exported too.

</td>
</tr>
<tr>
<td valign="top">

Analytic Models

See [Creating an Analytic Model](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/e5fbe9e2cb93484dab8b1963145e565f.html "Create an analytic model as a basis for consumption in SAP Analytics Cloud.") :arrow_upper_right:.

</td>
<td valign="top">

The definition of an analytic model contains the definitions of its fact and dimension sources. When you export an analytic model, these entities are exported too.

</td>
</tr>
<tr>
<td valign="top">

E/R Models

See [Creating an Entity-Relationship Model](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/a91c042549fb497384e756d5f5c71fde.html "Create an E/R model to import, visualize, edit, and deploy multiple tables and views together. You can use an E/R model to better understand a subset of the entities in your space, and to communicate this information to other stakeholders.") :arrow_upper_right:.

</td>
<td valign="top">

The definition of an E/R model does not include the objects that it visualizes as dependencies. These objects must be selected manually.

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

See [Creating a Task Chain](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/d1afbc2b9ee84d44a00b0b777ac243e1.html "Group multiple tasks into a task chain and run them manually once, or periodically, through a schedule.") :arrow_upper_right:.

</td>
<td valign="top">

The definition of a task chain does not include the objects that it automates. These objects must be selected manually.

</td>
</tr>
<tr>
<td valign="top">

Business Entities / Business Entity Versions

See [Creating a Business Entity](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/c912cdc1537d4efbb24b08327ea68918.html "You use business entities to build your consumption model for analysis and reporting.") :arrow_upper_right:.

</td>
<td valign="top">

The definition of a business entity contains all its versions \(which are also listed separately\), along with the definition of its source data entity and any authorization scenarios. When you export a business entity \(or one of its versions\), these objects are exported too.

</td>
</tr>
<tr>
<td valign="top">

Fact Models

See [Creating a Fact Model](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/5bbd14a328b549b2b53fce830ea25c15.html "Fact models are reusable models you can use to streamline the creation of other models within the same business context.") :arrow_upper_right:.

</td>
<td valign="top">

The definition of a fact model contains all its versions \(which are also listed separately\), along with the definition of all its source fact models and business entities. When you export a fact model \(or one of its versions\), these objects are exported too.

</td>
</tr>
<tr>
<td valign="top">

Consumption Models

See [Creating a Consumption Model](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/337fa99de4a44700ba49e2214a1f3349.html "Consumption models are the basis to consume your data.") :arrow_upper_right:.

</td>
<td valign="top">

The definition of a consumption model contains all its perspectives \(which are also listed separately\), along with the definition of all its source fact models and business entities. When you export a consumption model \(or one of its perspectives\), these objects are exported too.

</td>
</tr>
<tr>
<td valign="top">

Authorization Scenarios

See [Creating an Authorization Scenario](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/167c05c673dc4715baba8d5d305abb1e.html "Authorization scenarios help you control data access for business entities leveraging data access controls.") :arrow_upper_right:.

</td>
<td valign="top">

The definition of an authorization scenario contains the definition of its data access control. When you export an authorization scenario, the data access control is exported too.

</td>
</tr>
</table>

