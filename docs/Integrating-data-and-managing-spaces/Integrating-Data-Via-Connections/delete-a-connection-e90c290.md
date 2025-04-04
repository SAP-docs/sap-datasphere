<!-- loioe90c290260a04dfa94062e1d2824113e -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Delete a Connection

Select one or more connections and delete them if they are not used.



<a name="loioe90c290260a04dfa94062e1d2824113e__section_rmy_v41_q2c"/>

## Prerequisites

To create, edit, validate, or delete a connection, you must have a scoped role that grants you access to a space with the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Data Warehouse Connection* \(`CRUD----`\) - To create, edit, validate, or delete a connection.
-   *Spaces Files* \(`CRUD----`\) - To create, read, update, and delete objects in your spaces.

The *DW Space Administrator* and *DW Integrator* role templates, for example, grant these privileges. For more information, see [Privileges and Permissions](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/d7350c6823a14733a7a5727bad8371aa.html "A privilege represents a task or an area in SAP Datasphere and can be assigned to a specific role. The actions that can be performed in the area are determined by the permissions assigned to a privilege.") :arrow_upper_right: and [Standard Roles Delivered with SAP Datasphere](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/a50a51d80d5746c9b805a2aacbb7e4ee.html "SAP Datasphere is delivered with several standard roles. A standard role includes a predefined set of privileges and permissions.") :arrow_upper_right:. 



<a name="loioe90c290260a04dfa94062e1d2824113e__section_jgm_541_q2c"/>

## Procedure

1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(*Connections*\) and select a space if necessary.

2.  Select one or more connections and click *Delete*.


If the connection is still used for accessing data via remote tables, for importing models, or for data flows or replication flows, you cannot delete it. A message informs you of any dependent objects.

