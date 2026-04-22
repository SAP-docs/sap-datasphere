<!-- loiob37282c4c0d142e3bca256a46cd40278 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Importing Entities with Semantics from SAP HANA Cloud

You can use the *Import Entities* wizard to import semantically-rich objects using your SAP HANA Cloud connection. The wizard creates *Data Builder* entities in SAP Datasphere.



## Prerequisites

To import entities with semantics from SAP HANA, you must have a scoped role that grants you access to a space with the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Data Warehouse Connection* \(`-R------`\) - To access remote objects.
-   *Data Warehouse Data Builder* \(`CRUD----`\) - To create, edit and delete *Data Builder* objects.
-   *Space Files* \(`CRUD----`\) - To create, read, update, and delete objects in your spaces.

The *DW Modeler* role template, for example, grants these privileges. For more information, see [Privileges and Permissions](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/d7350c6823a14733a7a5727bad8371aa.html "A privilege represents a task or an area in SAP Datasphere and can be assigned to a specific role. The actions that can be performed in the area are determined by the permissions assigned to a privilege.") :arrow_upper_right: and [Standard Application RolesStandard Roles Delivered with SAP Datasphere](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/a50a51d80d5746c9b805a2aacbb7e4ee.html "SAP Datasphere is delivered with several standard roles. A standard role includes a predefined set of privileges and permissions.") :arrow_upper_right:. 



## Context

You can import entities from SAP HANA Cloud \(see [SAP HANA Connections](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/e6b63f176d3640609adcf06297fb37e9.html#loioe6b63f176d3640609adcf06297fb37e9 "Use an SAP HANA connection to access data from a remote SAP HANA database (on-premise or cloud).") :arrow_upper_right:\).

> ### Note:  
> All the connectivity preparations for model import \(connection capability “model transfer”\) must be completed, including setting up the certificates for communication, and setting up a communication user with data access privileges to all HANA Schemas where your calculation views are deployed on your SAP HANA Cloud system \(see [Prepare Connectivity to SAP HANA](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/d7f22cffa3d443669fec3003971e7638.html "To be able to successfully validate and use a connection to SAP HANA Cloud or SAP HANA (on-premise) for remote tables or data flows certain preparations have to be made.") :arrow_upper_right:\).

Calculation views and dimensions can only be imported as remote tables with the *Import Entities* wizard. Currently, you can import input parameters, currency and unit conversion, labels, and shared hierarchies. To ensure that your calculation view can be imported, deploy the calculation view in the source system with **SAP Business Data Cloud Integration Mode** set to **Flat View** or **Construction Kit** \(see [Preparing Calculation Views for SAP Business Data Cloud](https://help.sap.com/docs/HANA_CLOUD_DATABASE/d625b46ef0b445abb2c2fd9ba008c265/148eff49bb35415b899e3e5d684ae3d5.html) and [Set the Business Data Cloud Integration Mode for a Calculation View](https://help.sap.com/docs/HANA_CLOUD_DATABASE/d625b46ef0b445abb2c2fd9ba008c265/c3f7422ddf484af1b5dd5b0827bdea5b.html) in the *SAP HANA Cloud, SAP HANA Database Modeling Guide for SAP Business Application Studio* documentation\).

> ### Note:  
> You must have SAP HANA Cloud version QRC 1/2026 or higher and SAP Datasphere database version 2025.50 or higher.



## Procedure

1.  Open the wizard from the *Repository Explorer*, *Semantic Onboarding*, or the *Data Builder*:

    -   In the side navigation area, click <span class="SAP-icons-V5"></span> \(*Repository Explorer*\), and click *Import* \> *Import Entities*.
    -   In the side navigation area, click <span class="FPA-icons-V3"></span> \(*Semantic Onboarding*\), and then click the appropriate tile.
    -   In the side navigation area, click <span class="FPA-icons-V3"></span> \(*Data Builder*\), select a space if necessary, and click *Import* \> *Import Entities*.

2.  Select your connection and target space:


    <table>
    <tr>
    <th valign="top">

    *Semantic Onboarding*
    
    </th>
    <th valign="top">

    *Repository Explorer*/ *Data Builder*
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Select the connection to the source you want to import from the list, and then click *Next Step*.

    You can use the *Filter By* pane on the left to filter the connections by space.
    
    </td>
    <td valign="top">
    
    1.  Select the *SAP HANA* connection type, and then click *Next Step*.
    2.  Select the connection/target space that you want to import the entities from/into, and click *Next Step*. 

        If you opened the wizard from the <span class="FPA-icons-V3"></span> \(*Data Builder*\), only connections in your current space can be selected.



    
    </td>
    </tr>
    </table>
    
3.  On the *Select Entities* page, select the entities that you want to import from the *Results* list, and click *Next Step*.

    Use the *Search* field to search by label. You can filter by:

    -   View Type
    -   Schema Name

4.  On the *Review Entities* page, review the entities that you will import.

    The left pane lists the entities you have selected for import and the right pane has two tabs listing all the entities that will be created in the SAP Datasphere *Data Builder* during the import of the selected entity.

    The following entities are created when you import entities with the most common modeling patterns:


    <table>
    <tr>
    <th valign="top">

    Source Modeling Pattern
    
    </th>
    <th valign="top">

    Data Builder Objects Created
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    `CUBE`
    
    </td>
    <td valign="top">
    
    -   Selected entity:
        -   One view \(*Fact*\)
        -   One remote table \(*Relational Dataset*\)



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `Dimension`
    
    </td>
    <td valign="top">
    
    -   Selected entity:
        -   One view \(*Dimension*\)
        -   One remote table \(*Relational Dataset*\)



    
    </td>
    </tr>
    </table>
    
    Each object has the following read-only properties:


    <table>
    <tr>
    <th valign="top">

    Property
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Business Name
    
    </td>
    <td valign="top">
    
    Generated from the *Label* value.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Technical Name
    
    </td>
    <td valign="top">
    
    Generated from the *ID* value as: <code>remote.<i class="varname">&lt;connection_name&gt;</i>.<i class="varname">&lt;ID&gt;</i></code>.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Import Status
    
    </td>
    <td valign="top">
    
    Specifies whether the object needs to be created in SAP Datasphere during the import:

    -   *Ready for Import* - The object will be created.
    -   *Already Imported* - The object has already been created during a previous import. If the structure or semantics of the object have subsequently changed in the source system, the object will be automatically updated and redeployed.


    
    </td>
    </tr>
    </table>
    
5.  Click *Import and Deploy*.

    A notification is sent immediately, and this notification will update as the import process continues. When the import is complete:

    -   You have two notifications:
        -   Click the first notification to see the imported entities listed in the <span class="SAP-icons-V5"></span> \(*Repository Explorer*\).
        -   Click the second notification to view the import log messages.

            If any entity could not be created, an error is given.


    -   The imported entities are available for use in the <span class="FPA-icons-V3"></span> \(*Data Builder*\).


6.  From the side navigation, choose *Data Builder* and create an analytic model from the *Fact* view \(see [Create an Analytic Model Directly From a View or Table](../Modeling-Data-in-the-Data-Builder/create-an-analytic-model-directly-from-a-view-or-table-1c674aa.md)\).

7.  \[optional\] By default, data is only federated to your remote tables. To replicate the data, open the *Data Integration Monitor* \(see [Monitoring Remote Tables](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/4dd95d7bff1f48b399c8b55dbdd34b9e.html "In the Remote Tables monitor, you can find a remote table monitor per space. Here, you can copy data from remote tables that have been deployed in your space into SAP Datasphere, and you can monitor the replication of the data. You can copy or schedule copying the full set of data from the source, or you can set up replication of data changes in real-time via change data capturing (CDC).") :arrow_upper_right:\).


