<!-- loio23599e6347fb4c9e9a71c82f62449875 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Importing Objects from a CSN/JSON File

Import objects from a CSN/JSON file into your space from the *Data Builder* start page or an entity-relationship model.



## Context

A CSN \(Core Data Services Schema Notation\) file contains only the definition of the structure of your tables, views, and other objects, and does not contain any data. A CSN file can be imported into another space or another instance of SAP Datasphere. For detailed information about the CSN file format, see [Core Data Services Schema Notation \(CSN\)](https://cap.cloud.sap/docs/cds/csn#entity-definitions).



## Procedure

1.  Navigate to the *Data Builder* start page or to an entity-relationship model \(see [Creating an Entity-Relationship Model](../creating-an-entity-relationship-model-a91c042.md)\) and click <span class="FPA-icons-V3"></span> \(Import\)** \> *Import Objects from CSN/JSON File*.

2.  Select the CSN/JSON file you want to import, and click *Next* to open the *Select Objects to Import* dialog, which lists the objects contained in the CSN/JSON file, their type and semantic usage, as well as:


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
    
    Status
    
    </td>
    <td valign="top">
    
    Can be:

    -   *Ready to Import* - No object with this technical name is present in the space.
    -   *Already in the Repository* - The object is already present in the repository. If you select it for import, it will overwrite the existing object


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Messages
    
    </td>
    <td valign="top">
    
    Lists warnings or blocking errors related to the import. Click the message to see more details:

    -   Invalid Release State - An object in the repository will be overwritten by an object in the file with an inconsistent release state \(see [Releasing Stable Views for Consumption](../releasing-stable-views-for-consumption-5b99e9b.md)\).


    
    </td>
    </tr>
    </table>
    
3.  Select the objects you want to import and click *Import*.

    > ### Note:  
    > Remote tables exported from one space can be imported into another only if they were originally imported from a connection created in v2021.19 or later.

    In addition to the objects you select, other objects may be imported:

    -   Any objects on which your objects depend. If any of these objects are already present in the repository, you will see a message asking if you wish to re-import them and overwrite the repository version. Click:
        -   *Yes* - To re-import these objects and overwrite the repository versions. Some data may be lost if the structure of an object has changed.
        -   *No* - To keep the repository versions.
        -   *Cancel* - To cancel the import.

    -   Any simple types contained in the file. These types will be available for selection as a *Data Type* for columns. You cannot delete or modify simple types within SAP Datasphere.

    The objects are imported to the space. If you are in an entity-relationship model, the imported objects are added to the diagram.

    > ### Note:  
    > Objects imported from a CSN/JSON file are not automatically deployed.


