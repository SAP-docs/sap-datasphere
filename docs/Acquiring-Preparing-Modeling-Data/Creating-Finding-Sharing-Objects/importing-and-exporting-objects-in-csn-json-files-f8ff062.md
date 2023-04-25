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

The definition of a remote table contains information about its connection. Before importing a remote table, you must create the relevant connection with an identical technical name in the receiving space.

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

The definitions of all the tables and views in the model are exported. The model itself is not exported.



</td>
</tr>
</table>

> ### Note:  
> You can also export content from and import content to your space via:
> 
> -   The <span class="FPA-icons"></span> \(*Transport*\) app \(see [Transporting Content Between Tenants](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/df12666cf98e41248ef2251c564b0166.html "Users with the Administrator or Space Administrator role can use the Transport app to transfer content between tenants via a private cloud storage area.") :arrow_upper_right:\).
> -   The `dwc` command line \(see [Importing and Exporting Objects via the Command Line](importing-and-exporting-objects-via-the-command-line-6494657.md)\).

