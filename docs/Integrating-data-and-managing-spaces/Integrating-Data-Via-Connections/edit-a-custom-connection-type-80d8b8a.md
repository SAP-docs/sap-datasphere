<!-- loio80d8b8a70b24449dac0fa76f10c3727b -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Edit a Custom Connection Type

You can change the configuration of a custom connection type after it has been created. However, existing connections created from it are not updated when you edit the connection type. These updates apply only to new connections you create from this connection type. If you want a replication to use a new connection created from the modified connection type, you also need to update the corresponding replication flow.



## Prerequisites

To create, edit, and delete custom connection types, you must have a scoped role that grants you access to a space with the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Data Warehouse Connection* \(`CRUD----`\) - To create, edit, or delete custom connection types.
-   *Space Files* \(`CRUD----`\) - To create, read, update, and delete objects in your spaces.

The *DW Space Administrator* and *DW Integrator* role templates, for example, grant these privileges. For more information, see [Privileges and Permissions](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/d7350c6823a14733a7a5727bad8371aa.html "A privilege represents a task or an area in SAP Datasphere and can be assigned to a specific role. The actions that can be performed in the area are determined by the permissions assigned to a privilege.") :arrow_upper_right: and [Standard Roles Delivered with SAP Datasphere](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/a50a51d80d5746c9b805a2aacbb7e4ee.html "SAP Datasphere is delivered with several standard roles. A standard role includes a predefined set of privileges and permissions.") :arrow_upper_right:. 



## Context

Custom connection types are completely separate artifacts from the connections that were created based on them. This means that when a custom connection type is changed, any existing connections created from it do not automatically inherit the changes. There is also no impact on the existing replication flows using those connections.



## Procedure

1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(*Connections*\) and select a space if necessary.

2.  Select the relevant custom connection type, click *Edit*, make the necessary amendments to the configuration and save them.

3.  If you wish the changes to be reflected in a connection, you need to create a new connection based on the modified custom connection type, as described in [Create a Connection from a Custom Connection Type](create-a-connection-from-a-custom-connection-type-d0653d3.md).

4.  Update any dependent objects as follows:

    -   Edit any existing replication flows to point to the new connection.
    -   Create any future replication flows using the new connection.


