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

    > ### Note:  
    > When you re-import a SAP BW∕4HANA entity, the imported table in SAP Datasphere is overwritten. So in case you have made changes to the imported table, these changes will be lost.
    > 
    > If you would like to keep the changes you have made to the table in SAP Datasphere, you can refresh the table in the table editor in order to get updates from the original entity in the SAP BW∕4HANA system.

-   SAP BW bridge

    If the SAP Datasphere, SAP BW bridge option is enabled:

    -   A SAP BW bridge space is created, containing an SAP BW bridge connection to your bridge tools.
    -   You can use the *Import Entities* wizard to import your SAP BW bridge Queries, CompositeProviders, DataStore objects \(inbound table and/or active table depending on the type of the DataStore object\), and Master data tables \(including hierarchies\):
        -   Remote tables to load the data are created in the SAP BW bridge space and then automatically shared to the target space you specify in the wizard.
        -   Views and business entities that draw their data from and are built on these remote tables are created in your target space.


    For SAP BW bridge, you can import hierarchies modeled in SAP BW bridge including its semantic information into SAP Datasphere and use it as display hierarchy in the analytic model. When importing an InfoObject \(ANALYTICAL\_DIMENSION\) which has a hierarchy, the hierarchy is imported as well. The following objects are created for the hierarchy with directory in the Data Builder: hierarchy store, hierarchy directory, hierarchy directory description, and hierarchy note text.

    When you import objects with variables, you can use these variables in an analytic model. The default values set in SAP BW bridge are displayed in the preview. You can also define your own values.

    Not all types of variables are supported in SAP Datasphere. In most cases these are input-ready variables for characteristic values. Note also that the variable in the global filter can be the only restriction.

    For importing queries, there are certain restrictions:

    -   When an object is remodeled in SAP BW bridge, the query definition is broken.
    -   For dimensions, the following features are not supported: compound characteristics, and time dependency.

    You can use the app *Query* to get an overview on the supported analytical queries. For more information, see [Overview of Apps](https://help.sap.com/docs/SAP_BW_BRIDGE/107a6e8a38b74ede94c833ca3b7b6f51/65fc810abf0549ee861b0d2c7b73ada2.html).




## Procedure

1.  Open the wizard from *Semantic Onboarding*, the *Repository Explorer*, or the *Data Builder*:

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
    
    Select the connection to the source you want to import from from the list, and then click *Next Step*.

    You can use the *Filter By* pane on the left to filter the connections by space.
    
    </td>
    <td valign="top">
    
    1.  Select the *SAP BW/4HANA* or *SAP BW Bridge* connection type, and then click *Next Step*.
    2.  Select the connection/target space that you want to import the entities from/into, and click *Next Step*.

        If you opened the wizard from the <span class="FPA-icons-V3"></span> \(*Data Builder*\), only your current space can be selected.

        > ### Note:  
        > The *SAP BW Bridge* space cannot be selected as the target space. When importing entities from bridge, any remote tables are imported to the *SAP BW Bridge* space and automatically shared to your selected target space, where the remaining objects are created.



    
    </td>
    </tr>
    </table>
    
3.  On the *Select Entities* page, select the entities that you want to import from the *Results* list, and click *Next Step*.

    Use the *Search* field to search by label. Depending on your connection type, you can filter by:

    -   Application Component
    -   Modeling Pattern
    -   Software Component

4.  On the *Review Entities* page, review the entities that you will import.

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
    
5.  Click *Import and Deploy*.

    A notification is sent immediately, and this notification will update as the import process continues. When the import is complete:

    -   You have two notifications:
        -   Click the first notification to see the imported entities listed in the <span class="SAP-icons-V5"></span> \(*Repository Explorer*\).
        -   Click the second notification to view the import log messages.

            If any entity could not be created, an error is given.


    -   The imported entities are available for use in the <span class="FPA-icons-V3"></span> \(*Business Builder*\) and the <span class="FPA-icons-V3"></span> \(*Data Builder*\).

        > ### Note:  
        > If you have enabled metadata translation in the target space and the entities are available in the specified source language then they will be imported in this language \(see [Translating Metadata for SAP Analytics Cloud](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/fe829debe389450394cf7a15860e2caa.html "Users with a scoped role containing the Translation privilege can translate metadata such as business names and column names for dimensions and analytic models, and hierarchy dimension labels for SAP Analytics Cloud stories.") :arrow_upper_right:\). Otherwise, they will be imported in English, by default.


6.  \[optional\] By default, data is only federated to your remote tables. To replicate the data, open the *Data Integration Monitor* \(see [Replicating Data and Monitoring Remote Tables](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/4dd95d7bff1f48b399c8b55dbdd34b9e.html "In the Remote Tables monitor, you can find a remote table monitor per space. Here, you can copy data from remote tables that have been deployed in your space into SAP Datasphere, and you can monitor the replication of the data. You can copy or schedule copying the full set of data from the source, or you can set up replication of data changes in real-time via change data capturing (CDC).") :arrow_upper_right:\).


