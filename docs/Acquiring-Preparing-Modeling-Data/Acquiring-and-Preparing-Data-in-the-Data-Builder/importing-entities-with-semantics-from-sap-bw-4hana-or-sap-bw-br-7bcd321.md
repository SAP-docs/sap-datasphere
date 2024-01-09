<!-- loio7bcd3218b4064b898ca367b47ff246e2 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Importing Entities with Semantics from SAP BW∕4HANA or SAP BW Bridge

You can use the *Import Entities* wizard to load metadata from your SAP BW∕4HANA and SAP BW bridge connection via semantically-rich objects. The wizard creates *Business Builder* and *Data Builder* entities \(along with all the objects on which they depend\) in SAP Datasphere.



<a name="loio7bcd3218b4064b898ca367b47ff246e2__prereq_pxy_pzs_cyb"/>

## Prerequisites

You must have a user in the bridge tools with the business role template `SAP_DW4_BC_MODELING_DWC_PC`. For more information, see [Business Role Templates](https://help.sap.com/docs/SAP_BW_BRIDGE/107a6e8a38b74ede94c833ca3b7b6f51/75d2fa4c36a548ca86d0b8527123beb6.html) in the *SAP Datasphere, SAP BW Bridge* documentation.



## Context

You can import entities from the following types of sources:

-   SAP BW∕4HANA \(see [SAP BW∕4HANA Model Transfer Connections](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/1caba954bc604e00bf8e82e383a46368.html "Use an SAP BW/4HANA Model Transfer connection to import analytic queries from SAP BW∕4HANA with their Composite Providers and InfoObjects.") :arrow_upper_right:\).
-   SAP BW bridge

    If the SAP Datasphere, SAP BW bridge option is enabled:

    -   A SAP BW bridge space is created, containing an SAP BW bridge connection to your bridge tools.
    -   You can use the *Import Entities* wizard to import your SAP BW bridge Queries, CompositeProviders, DataStore objects \(inbound table and/or active table depending on the type of the DataStore object\), and Master data tables:
        -   Remote tables to load the data are created in the SAP BW bridge space and then automatically shared to the target space you specify in the wizard.
        -   Views and business entities that draw their data from and are built on these remote tables are created in your target space.


    For importing queries, there are certain restrictions:

    -   When an object is remodeled in SAP BW bridge, the query definition is broken.
    -   Input and exit variables are removed.
    -   Constant selection is not supported.
    -   For dimensions, the following features are not supported: external hierarchies, compound characteristics, and time dependency.

    You can use the app *Query* to get an overview on the supported analytical queries. For more information, see [Overview of Apps](https://help.sap.com/docs/SAP_BW_BRIDGE/107a6e8a38b74ede94c833ca3b7b6f51/65fc810abf0549ee861b0d2c7b73ada2.html).




## Procedure

1.  Open the wizard from the *Repository Explorer*, *Semantic Onboarding*, or the *Data Builder*:

    -   In the side navigation area, click <span class="SAP-icons"></span> \(*Repository Explorer*\), and click *Import* \> *Import Entities*.
    -   In the side navigation area, click <span class="FPA-icons"></span> \(*Semantic Onboarding*\), and then click the appropriate tile.
    -   In the side navigation area, click ![](../Creating-Finding-Sharing-Objects/images/Data_Builder_f73dc45.png) \(*Data Builder*\), select a space if necessary, and click *Import* \> *Import Entities*.

2.  On the *Select Connection Type* page, select the *SAP BW/4HANA* or *SAP BW Bridge* connection type, and then click *Next Step*.

3.  On the *Select Target Space* page, click the target space that you want to import the entities into, and click *Next Step*.

    If you opened the wizard from the ![](../Creating-Finding-Sharing-Objects/images/Data_Builder_f73dc45.png) \(*Data Builder*\), only your current space can be selected.

    > ### Note:  
    > The *SAP BW Bridge* space cannot be selected as the target space. When importing entities from bridge, any remote tables are imported to the *SAP BW Bridge* space and automatically shared to your selected target space, where the remaining objects are created.

4.  On the *Select Connection* page, click the specific connection to the source you want to import from, and click *Next Step*.

5.  On the *Select Entities* page, select the entities that you want to import from the *Results* list, and click *Next Step*.

    Use the *Search* field to search by label. Depending on your connection type, you can filter by:

    -   Application Component
    -   Modeling Pattern
    -   Software Component

6.  On the *Review Entities* page, review the entities that you will import.

    The left pane lists the entities you have selected for import and the right pane has two tabs listing all the entities that will be created in the SAP Datasphere *Business Builder* and *Data Builder* during the import of the selected entity.

    The following entities are created when you import entities with the most common modeling patterns:

    > ### Note:  
    > If an associated entity cannot be imported, it is left out. The generated object however will still be a complete object.


    <table>
    <tr>
    <th valign="top">

    Source Modeling Pattern
    
    </th>
    <th valign="top">

    Business Builder Objects Created
    
    </th>
    <th valign="top">

    Data Builder Objects Created
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    `ANALYTICAL_QUERY`
    
    </td>
    <td valign="top">
    
    -   Selected entity:
        -   One consumption model containing a perspective.

    -   Supporting entities:
        -   One entity \(*Fact*\)
        -   One entity \(*Dimension*\) for each associated dimension.



    
    </td>
    <td valign="top">
    
    -   Supporting entities:
        -   One view \(*Fact*\)
        -   One remote table \(*Relational Dataset*\)
        -   One view and one remote table for each associated dimension.



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `ANALYTICAL_CUBE`
    
    </td>
    <td valign="top">
    
    -   Selected entity:
        -   One business entity \(*Fact*\)

    -   Supporting entities:
        -   One entity \(*Dimension*\) for each associated dimension.



    
    </td>
    <td valign="top">
    
    -   Selected entity:
        -   One view \(*Fact*\)
        -   One remote table \(*Relational Dataset*\)

    -   Supporting entities:
        -   One view and one remote table for each associated dimension.



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `ANALYTICAL_DIMENSION`

    \(SAP BW Bridge only\)
    
    </td>
    <td valign="top">
    
    -   Selected entity:
        -   One business entity \(*Dimension*\)

    -   Supporting entities:
        -   One entity \(*Dimension*\) for each associated dimension.



    
    </td>
    <td valign="top">
    
    -   Selected entity:
        -   One view \(*Dimension*\)
        -   One remote table \(*Relational Dataset*\)

    -   Supporting entities:
        -   One view and one remote table for each associated dimension, hierarchy, and text entity.



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `LANGUAGE_DEPENDENT_TEXT`

    \(SAP BW Bridge only\)
    
    </td>
    <td valign="top">
    
    \(none\)
    
    </td>
    <td valign="top">
    
    -   Selected entity:
        -   One remote table \(*Text*\)



    
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
    
7.  Click *Import and Deploy*.

    A notification is sent immediately, and this notification will update as the import process continues.

    When the import is complete, you will have two notifications:

    -   Click the first notification to see the imported entities listed in the <span class="SAP-icons"></span> \(*Repository Explorer*\).
    -   Click the second notification to view the import log messages.

        If any entity could not be created, an error is given.


    The imported entities are available for review and use in the <span class="FPA-icons"></span> \(*Business Builder*\) and the ![](../Creating-Finding-Sharing-Objects/images/Data_Builder_f73dc45.png) \(*Data Builder*\).


