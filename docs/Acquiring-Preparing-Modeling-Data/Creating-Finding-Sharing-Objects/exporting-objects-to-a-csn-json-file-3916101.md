<!-- loio391610123f1f4a12abb12cbf77a3294d -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Exporting Objects to a CSN/JSON File

Export the definitions of your tables, views, and other objects to a CSN/JSON file, which can be imported into another space or tenant.



## Context

A CSN \(Core Data Services Schema Notation\) file contains only the definition of the structure of your tables, views, and other objects, and does not contain any data. A CSN file can be imported into another space or another instance of SAP Datasphere. For detailed information about the CSN file format, see [Core Data Services Schema Notation \(CSN\)](https://cap.cloud.sap/docs/cds/csn#entity-definitions).

The *Export to CSN/JSON File* button is available in the following editors:

-   Local tables \(see [Creating a Local Table](../Acquiring-and-Preparing-Data-in-the-Data-Builder/creating-a-local-table-2509fe4.md)\)
-   Remote tables \(see [Importing Tables and Views from Sources](../Acquiring-and-Preparing-Data-in-the-Data-Builder/importing-tables-and-views-from-sources-7c4acd3.md)\)
-   Graphical views \(see [Creating a Graphical View](../creating-a-graphical-view-27efb47.md)\)
-   SQL views \(see [Creating an SQL View](../creating-an-sql-view-81920e4.md)\)
-   Data flows \(see [Creating a Data Flow](../Acquiring-and-Preparing-Data-in-the-Data-Builder/creating-a-data-flow-e30fd14.md)\)
-   Replication flows \(see [Creating a Replication Flow](../Acquiring-and-Preparing-Data-in-the-Data-Builder/creating-a-replication-flow-25e2bd7.md)\)
-   Intelligent lookups \(see [Creating an Intelligent Lookup](../creating-an-intelligent-lookup-8f29f80.md)\)
-   Analytic models \(see [Creating an Analytic Model](../Modeling-Data-in-the-Data-Builder/creating-an-analytic-model-e5fbe9e.md)\)
-   Entity-relationship models \(see [Creating an Entity-Relationship Model](../creating-an-entity-relationship-model-a91c042.md)\)
-   Data access controls \(see [Securing Data with Data Access Controls](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/a032e51c730147c7a1fcac125b4cfe14.html "Users with a space administrator role can create data access controls to allow modelers to apply row-level security to Data Builder and Business Builder objects. Once a data access control is applied to an object, any user viewing its data either directly or via an object using it as a source, will see only those records they are authorized to view, based on the specified criteria.") :arrow_upper_right:\)
-   Task chains \(see [Creating a Task Chain](../Acquiring-and-Preparing-Data-in-the-Data-Builder/creating-a-task-chain-d1afbc2.md)\)



## Procedure

1.  In the editor toolbar, click <span class="FPA-icons-V3"></span> \(Export\)** \> *Export to CSN/JSON File*.

2.  If the editor contains unsaved changes, you are prompted to save. Click *OK*.

    The contents of the editor are exported to <code><i class="varname">&lt;Object_Name&gt;</i>.json</code> and downloaded to your browser:


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
    
    The definition of a task chain does not include the objects that it automates. These objects must be selected manually.
    
    </td>
    </tr>
    </table>
    

