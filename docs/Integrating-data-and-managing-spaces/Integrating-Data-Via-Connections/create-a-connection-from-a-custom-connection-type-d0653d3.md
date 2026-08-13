<!-- loiod0653d37167a49679d0a3e909547a674 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Create a Connection from a Custom Connection Type

Create a connection from custom connection type to allow users assigned to a file space to use the connected REST API source for loading JSON-based data to the SAP Datasphere object store using replication flows.



<a name="loiod0653d37167a49679d0a3e909547a674__section_prerequisites"/>

## Prerequisites

To create, edit, and delete connections, you must have a scoped role that grants you access to a space with the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Data Warehouse Connection* \(`CRUD----`\) - To create, edit, or delete connections.
-   *Space Files* \(`CRUD----`\) - To create, read, update, and delete objects in your spaces.

The *DW Space Administrator* and *DW Integrator* role templates, for example, grant these privileges. For more information, see [Privileges and Permissions](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/d7350c6823a14733a7a5727bad8371aa.html "A privilege represents a task or an area in SAP Datasphere and can be assigned to a specific role. The actions that can be performed in the area are determined by the permissions assigned to a privilege.") :arrow_upper_right: and [Standard Roles Delivered with SAP Datasphere](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/a50a51d80d5746c9b805a2aacbb7e4ee.html "SAP Datasphere is delivered with several standard roles. A standard role includes a predefined set of privileges and permissions.") :arrow_upper_right:. 

In addition, if you want to create and use a connection based on a custom connection type in an existing file space, you first need to re-deploy the space.



## Context

> ### Note:  
> Connections based on custom connection types are not supported by the SAP Datasphere command line interface or the SAP Datasphere *Connections* API. You cannot list, read, create, edit, delete, or validate these connections via the command line interface or the API.



## Procedure

1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(*Connections*\) and select a space if necessary.
2.  On the *Connections* tab, click <span class="FPA-icons-V3"></span> \(Add Connection\) ** \> *Create Connection* to open the connection creation wizard.
3.  Click the tile for your custom connection type. Search, sort, or filter options help you to quickly find your connection type.
4.  Complete the properties in the following sections and click *Next Step*.


    <table>
    <tr>
    <th valign="top">

    Property Section
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Information*
    
    </td>
    <td valign="top">
    
    Enter the base URL used to access your REST API endpoint.

    > ### Note:  
    > Only URLs that resolve to real, public IP addresses are supported. Dummy values aren't allowed, even if they are in a proper URL format.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Authentication*
    
    </td>
    <td valign="top">
    
    Select the authentication type \(if your connection type offers more than one\), complete further properties as required by authentication type, and provide your credentials.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Actions*
    
    </td>
    <td valign="top">
    
    From the resource or resources available for the connection type, select the action or actions that you want to provide as source containers to replication flows.
    
    </td>
    </tr>
    </table>
    
5.  Complete the following properties:


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
    
    *Business Name*
    
    </td>
    <td valign="top">
    
    Enter a descriptive name to help users identify the object. This name can be changed at any time.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Technical Name*
    
    </td>
    <td valign="top">
    
    Displays the name used in scripts and code, synchronized by default with the *Business Name*.

    The technical name can only contain alphanumeric characters and underscores \(\_\). It cannot start or end with underscore \(\_\). The name must be unique within the space.

    > ### Note:  
    > The system generates target object \(table\) names in a replication flow using the format <code><i class="varname">&lt;custom_connection_technical_name&gt;</i>.<i class="varname">&lt;action_technical_name&gt;</i>.<i class="varname">&lt;entity_name&gt;</i></code>. The maximum total length is 100 characters: 15 for connection, 45 for action, and 40 for entity. If a component name exceeds its character limit, the system truncates it. This truncation can create duplicate target object names, causing your replication flow deployment to fail.
    > 
    > You cannot rename the target object or map to an existing target object. To avoid duplicates, choose your connection, action, and entity names carefully.

    > ### Note:  
    > Once the object is saved, the technical name can no longer be modified.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Package* 
    
    </td>
    <td valign="top">
    
    Select the package to which the connection belongs. 

    Users with the *DW Space Administrator* role \(or equivalent privileges\) can create packages in the *Packages* editor. Once a package is created in your space, you can select it here.

    Packages are used to group related objects in order to facilitate their transport between tenants.

    > ### Note:  
    > Once a package is selected, it cannot be changed here. Only a user with the DW Space Administrator role \(or equivalent privileges\) can modify a package assignment in the *Packages* editor.

    For more information, see [Creating Packages to Export](../Transporting-Content-Between-Tenants/creating-packages-to-export-24aba84.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Description*
    
    </td>
    <td valign="top">
    
    Provide more information to help users understand the object.
    
    </td>
    </tr>
    </table>
    
6.  Click *Create Connection* to create the connection and add it to the overview of available connections.

    > ### Note:  
    > -   Validation is not supported for connections created from custom connection types.
    > -   Any later changes to a custom connection type that has been used for creating a connection won't be reflected in the connection. For example, if you add an authentication type to a custom connection type, the new authentication type won't be available for you when you edit a connection that has been created based on this connection type before the new authentication type has been introduced. The information *Modified* or *Deleted* in the *Type* column of the connection overview helps you to identify connections for which the connection types used for their creation have been changed or deleted afterwards. If you want to consider custom connection type changes that have been introduced after you have created your connection based on this connection type, you must create a new connection.




<a name="loiod0653d37167a49679d0a3e909547a674__section_using_connections"/>

## Results

You can use the connection to create replication flows.

For more information, see:

-   [Creating a Replication Flow](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/25e2bd7a70d44ac5b05e844f9e913471.html "Create a replication flow to copy multiple data assets from a source to a target with support for delta loads.") :arrow_upper_right:
-   [Rest API Custom Connection Sources for Replication Flows](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/cc0fad818e9b4d409c43969195d3fd82.html "You can use REST API connections as sources in replication flows to replicate data into local table file spaces, using SAP Datasphere (HDL_Files) as the target. The REST API acts as a data source similar to other connections. When you select an action from the connection, the system retrieves data records from the API response and creates corresponding replication objects.") :arrow_upper_right:

