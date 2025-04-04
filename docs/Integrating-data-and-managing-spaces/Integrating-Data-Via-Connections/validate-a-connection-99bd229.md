<!-- loio99bd2294c3724d478c41555e186ce0ef -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Validate a Connection

Select a connection and open the validation message to get detailed status information.



<a name="loio99bd2294c3724d478c41555e186ce0ef__section_dbh_j41_q2c"/>

## Prerequisites

To create, edit, validate, or delete a connection, you must have a scoped role that grants you access to a space with the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Data Warehouse Connection* \(`CRUD----`\) - To create, edit, validate, or delete a connection.
-   *Spaces Files* \(`CRUD----`\) - To create, read, update, and delete objects in your spaces.

The *DW Space Administrator* and *DW Integrator* role templates, for example, grant these privileges. For more information, see [Privileges and Permissions](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/d7350c6823a14733a7a5727bad8371aa.html "A privilege represents a task or an area in SAP Datasphere and can be assigned to a specific role. The actions that can be performed in the area are determined by the permissions assigned to a privilege.") :arrow_upper_right: and [Standard Roles Delivered with SAP Datasphere](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/a50a51d80d5746c9b805a2aacbb7e4ee.html "SAP Datasphere is delivered with several standard roles. A standard role includes a predefined set of privileges and permissions.") :arrow_upper_right:. 



<a name="loio99bd2294c3724d478c41555e186ce0ef__section_xxm_k41_q2c"/>

## Procedure

1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(*Connections*\) and select a space if necessary.

2.  Select the relevant connection and click *Validate*.

    The message informs you about the availability of supported features and provides details in case of errors in the connection.


