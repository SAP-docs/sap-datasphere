<!-- loio361729b49aea4519a6e8910b035dbf6c -->

# Importing Objects with Semantics from SAP S/4HANA, SAP BW∕4HANA and SAP BW Bridge

Users with the *DW Modeler* role \(or equivalent privileges\) can use the *Import Entities* wizard to import semantically-rich objects from your SAP S/4HANA Cloud, SAP S/4HANA on-premise, SAP BW∕4HANA, and SAP BW bridge connections. The wizard creates *Business Builder* and *Data Builder* entities \(along with all the objects on which they depend\) in SAP Datasphere.



<a name="loio361729b49aea4519a6e8910b035dbf6c__section_yx1_p2t_zgc"/>

## Prerequisites

To import objects with semantics from SAP S/4HANA, SAP BW∕4HANA and SAP BW Bridge, you must have a scoped role that grants you access to a space with the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Data Warehouse Connection* \(`-R------`\) - To access remote objects.
-   *Data Warehouse Data Builder* \(`CRUD----`\) - To create, edit and delete *Data Builder* objects.
-   *Data Warehouse Business Builder* \(`CRUD----`\) - To create, edit and delete *Business Builder* objects.
-   *Data Warehouse Business Entity* \(`CRUD----`\) - To create, edit and delete *Business Builder* business entities.
-   *Data Warehouse Consumption Model* \(`CRUD----`\) - To create, edit and delete *Business Builder* consumption models.
-   *Space Files* \(`CRUD----`\) - To create, read, update, and delete objects in your spaces.

The *DW Modeler* role template, for example, grants these privileges. For more information, see [Privileges and Permissions](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/d7350c6823a14733a7a5727bad8371aa.html "A privilege represents a task or an area in SAP Datasphere and can be assigned to a specific role. The actions that can be performed in the area are determined by the permissions assigned to a privilege.") :arrow_upper_right: and [Standard Roles Delivered with SAP Datasphere](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/a50a51d80d5746c9b805a2aacbb7e4ee.html "SAP Datasphere is delivered with several standard roles. A standard role includes a predefined set of privileges and permissions.") :arrow_upper_right:. 



<a name="loio361729b49aea4519a6e8910b035dbf6c__section_f4p_n2t_zgc"/>

## Objects

Objects with the following modeling patterns can be imported:


<table>
<tr>
<th valign="top">

Modeling Pattern

</th>
<th valign="top">

Supported Connections

</th>
</tr>
<tr>
<td valign="top">

`ANALYTICAL_QUERY`

</td>
<td valign="top">

SAP BW∕4HANA, SAP BW bridge

</td>
</tr>
<tr>
<td valign="top">

`ANALYTICAL_CUBE`

</td>
<td valign="top">

SAP BW∕4HANA, SAP BW bridge

</td>
</tr>
<tr>
<td valign="top">

`ANALYTICAL_FACT`

</td>
<td valign="top">

SAP S/4HANA on-premise only

</td>
</tr>
<tr>
<td valign="top">

`ANALYTICAL_DIMENSION`

</td>
<td valign="top">

SAP BW bridge, SAP S/4HANA Cloud, SAP S/4HANA on-premise

</td>
</tr>
<tr>
<td valign="top">

`LANGUAGE_DEPENDENT_TEXT`

</td>
<td valign="top">

SAP BW bridge, SAP S/4HANA Cloud, SAP S/4HANA on-premise

</td>
</tr>
<tr>
<td valign="top">

`ANALYTICAL_PARENT_CHILD_HIERARCHY_NODE`

</td>
<td valign="top">

SAP S/4HANA Cloud, SAP S/4HANA on-premise

</td>
</tr>
</table>

