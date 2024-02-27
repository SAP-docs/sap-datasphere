<!-- loiof8ff0628c9fc49229740ffcd4d20e9aa -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Importing and Exporting Objects in CSN/JSON Files

You can use the tools in certain *Data Builder* editors to import objects to and export objects from your space.

The following object types can be exported and imported via CSN files:


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

The definition of a remote table contains information about its connection.

> ### Note:  
> Remote tables exported from one space can be imported into another only if they were originally imported from a connection created in v2021.19 or later.



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

Flows

</td>
<td valign="top">

The definition of a data flow, replication flow, or transformation flow contains the definitions of all its sources and its target table. When you export a flow, these objects are exported too.

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

The definitions of all the tables and views in the model are exported. The model itself is not exported.

</td>
</tr>
</table>

> ### Note:  
> You can also export content from and import content to your space via:
> 
> -   The <span class="FPA-icons-V3"></span> \(*Transport*\) app \(see [Transporting Content Between Tenants](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/df12666cf98e41248ef2251c564b0166.html "Users with the DW Administrator global role (or users with both a scoped DW Space Administrator role and a global role providing the Lifecycle privilege), can use the Transport app to transfer content between tenants via a private cloud storage area.") :arrow_upper_right:\).
> -   The `datasphere` command line interface `objects` commands \(see [Manage Modeling Objects via the Command Line](https://help.sap.com/viewer/9b8363ae47c347de9a027c0e5567a37a/DEV_CURRENT/en-US/6f5c65f209004751aa48f9682ee2ec45.html "Users with a DW Modeler role (or equivalent privileges) can list, create, update, and delete modeling objects via the command line.") :arrow_upper_right:\).

