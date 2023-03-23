<!-- loiodf12666cf98e41248ef2251c564b0166 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Transporting Content Between Tenants

Users with the Administrator or Space Administrator role can use the *Transport* app to transfer content between tenants via a private cloud storage area.

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

Local Tables



</td>
<td valign="top">

The definition of a local table contains the structure of the table only, and does not have dependencies on any other objects.



</td>
</tr>
<tr>
<td valign="top">

Remote Tables



</td>
<td valign="top">

The definition of a remote table contains information about its connection. Before importing a remote table, you must create the relevant connection with an identical technical name in the receiving space.



</td>
</tr>
<tr>
<td valign="top">

Views



</td>
<td valign="top">

The definition of a view contains the definitions of all its sources and any used data access controls. When you export a view, these objects are exported too.



</td>
</tr>
<tr>
<td valign="top">

Data Flows



</td>
<td valign="top">

The definition of a data flow contains the definitions of all its sources and its target table. When you export a data flow, these objects are exported too.



</td>
</tr>
<tr>
<td valign="top">

Intelligent Lookups



</td>
<td valign="top">

The definition of an intelligent lookup contains the definitions of its input and lookup entities. When you export an intelligent lookup, these entities are exported too.



</td>
</tr>
<tr>
<td valign="top">

Analytic Models



</td>
<td valign="top">

The definition of an analytic model contains the definitions of its fact and dimension sources. When you export an analytic model, these entities are exported too.



</td>
</tr>
<tr>
<td valign="top">

E/R Models



</td>
<td valign="top">

The definition of an E/R model does not include the objects that it visualizes as dependencies. These visualized objects must be selected manually.



</td>
</tr>
<tr>
<td valign="top">

Data Access Controls



</td>
<td valign="top">

The definition of a data access control contains the definition of its permissions entity. When you export a data access control, the permissions entity is exported too.



</td>
</tr>
<tr>
<td valign="top">

Task Chains



</td>
<td valign="top">

The definition of a task chain contains the definition of all the objects that it automates. When you export a task chain, these objects are exported too.



</td>
</tr>
</table>

> ### Note:  
> Only local and remote tables, views, data flows, and E/R models can be selected for exporting in SAP Datasphere tenants provisioned prior to version 2021.03. While objects created in SAP Datasphere tenants provisioned prior to version 2021.03 can be transported to tenants provisioned after that date, transport of objects in the other direction is not possible.

> ### Note:  
> You can also export certain content from and import content to your space via:
> 
> -   *Export to CSN/JSON File* buttons in selected *Data Builder* editors \(see [Importing and Exporting Objects in CSN/JSON Files](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/internal/en-US/f8ff0628c9fc49229740ffcd4d20e9aa.html "You can use the tools in certain Data Builder editors to import objects to and export objects from your space.") :arrow_upper_right:\).
> -   The `dwc` command line \(see [Importing and Exporting Objects via the Command Line](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/internal/en-US/649465700ff14cd3ab7aebd72f370115.html "You can use the SAP Datasphere command line interface, dwc, to import objects to and export objects from your space.") :arrow_upper_right:\).

For information about importing business content in the form of end-to-end business scenarios for specific industries and lines of business provided by SAP and its partners via the <span class="FPA-icons"></span> \(*Content Network*\) app, see [Importing SAP and Partner Business Content from the Content Network](../importing-sap-and-partner-business-content-from-the-content-network-400078d.md).

