<!-- loio391610123f1f4a12abb12cbf77a3294d -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Exporting Objects to a CSN/JSON File

Export the definitions of your tables, views, and other objects to a CSN/JSON file, which can be imported into another space.



## Context

A CSN \(Core Data Services Schema Notation\) file contains only the definition of the structure of your tables, views, and other objects, and does not contain any data. A CSN file can be imported into another space or another instance of SAP Datasphere. For detailed information about the CSN file format, see [Core Data Services Schema Notation \(CSN\)](https://cap.cloud.sap/docs/cds/csn#entity-definitions).

The *Export to CSN/JSON File* button is available in the following editors:

-   Table editor
-   Graphical view editor
-   SQL view editor
-   Data flow editor
-   Intelligent lookup editor
-   Analytic model editor
-   Entity-relationship model editor



## Procedure

1.  In the editor toolbar, click <span class="FPA-icons"></span> \(Export\)** \> *Export to CSN/JSON File*.

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
    

