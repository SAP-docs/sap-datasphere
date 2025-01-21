<!-- loio845fedbd28574aa8b84239df848936f6 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Importing Entities with Semantics from SAP S/4HANA

You can use the *Import Entities* wizard to load metadata from your SAP S/4HANA Cloud and SAP S/4HANA on-premise connections via semantically-rich objects. The wizard creates *Business Builder* and *Data Builder* entities \(along with all the objects on which they depend\) in SAP Datasphere.



## Context

You can import entities from the following types of sources:

-   SAP S/4HANA Cloud \(see [SAP S/4HANA Cloud Connections](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/a98e5ffdf47c44d9a845dca01a18bd82.html "Use an SAP S/4HANA Cloud connection to access or import extraction-enabled ABAP Core Data Services views (ABAP CDS views) from SAP S/4HANA Cloud.") :arrow_upper_right:\).

    > ### Note:  
    > All the connectivity preparations for model import must be completed, including the activation of the necessary communication scenarios in the SAP S/4HANA Cloud system \(see [Prepare Connectivity to SAP S/4HANA Cloud](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/abb159e027184c98a54fc1b2a88dd3f5.html "To be able to successfully validate and use a connection to SAP S/4HANA Cloud, certain preparations have to be made.") :arrow_upper_right:\).

-   SAP S/4HANA On-Premise \(see [SAP S/4HANA On-Premise Connections](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/a49a1e3cc50f4af89711d8306bdd8f26.html "Use an SAP S/4HANA On-Premise connection to access data from SAP S/4HANA on-premise systems.") :arrow_upper_right:\).

    > ### Note:  
    > The on-premise system must be v1610 or higher, and all the connectivity preparations must be completed \(see [Prepare Connectivity to SAP S/4HANA On-Premise](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/8de01dd25c1e443e8e2de7d2fbe1364d.html "To be able to successfully validate and use a connection to SAP S/4HANA, certain preparations have to be made.") :arrow_upper_right:\).


We recommend that, where possible, you use the *Import Entities* wizard for importing CDS views from these connection types, as it as able to leverage their rich semantics to import higher-level objects and to follow associations to dimensions, hierarchies, and text entities and include them in the import.

> ### Note:  
> Only CDS views delivered by SAP via SAP S/4HANA Cloud and SAP S/4HANA on-premise connections from SAP\_BASIS Release 756 onwards \(with a connection based on SAP Note [3463326](https://me.sap.com/notes/3463326)\) can include associated entities in the import.
> 
> Custom CDS views \(and any CDS views from on-premise connections that do not meet these requirements\) cannot follow associations, but the information is included in each imported object's CSN definition, and associations will be automatically recreated in SAP Datasphere if their target entities are already present or are subsequently imported.



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
    
    1.  Select the *SAP S/4HANA Cloud* or *SAP S/4HANA* connection type, and then click *Next Step*.
    2.  Select the connection/target space that you want to import the entities from/into, and click *Next Step*. 

        If you opened the wizard from the <span class="FPA-icons-V3"></span> \(*Data Builder*\), only connections in your current space can be selected.



    
    </td>
    </tr>
    </table>
    
    > ### Note:  
    > If your connection supports using replication flows to load data, the *Data Access* field is displayed and defaults to *Replication Flow to Local Tables*. We recommend using this option to optimize load times but you can, if you prefer, revert to creating *Remote Tables*.

3.  On the *Select Entities* page, select the entities that you want to import from the *Results* list, and click *Next Step*.

    Use the *Search* field to search by label. Depending on your connection type, you can filter by:

    -   Application Component
    -   Modeling Pattern \(see [Supported Capabilities for CDS Views](https://help.sap.com/viewer/0f69f8fb28ac4bf48d2b57b9637e81fa/latest/en-US/6a6ff32b25dd473080e6aeddbefecfca.html) in the *SAP S/4HANA Cloud*\) documentation\)
    -   Release Contract \(see [Stability Contracts for CDS Views](https://help.sap.com/viewer/0f69f8fb28ac4bf48d2b57b9637e81fa/latest/en-US/2e4edbede2f94fb7b7f6eac856c02b19.html) in the *SAP S/4HANA Cloud*\) documentation\)

        > ### Note:  
        > Entities that have a release contract of *C1* \(and that are extraction-enabled\) can be imported as remote tables, which support data federation and replication natively. Other entities can only be imported as local tables and you must provide data replication manually by creating a data flow.

    -   Software Component

4.  On the *Review Entities* page, review the entities that you will import.

    The left pane lists the entities you have selected for import and the right pane has two tabs listing all the entities that will be created in the SAP Datasphere *Business Builder* and *Data Builder* during the import of the selected entity.

    The following entities are created when you import entities with the most common modeling patterns:


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
    
    `ANALYTICAL_FACT`

    \(SAP S/4HANA on-premise only\)
    
    </td>
    <td valign="top">
    
    -   Selected entity:
        -   One business entity \(*Fact*\)

    -   Supporting entities:
        -   One entity \(*Dimension*\) for each associated dimension.



    
    </td>
    <td valign="top">
    
    -   Selected entity:
        -   One remote table \(*Relational Dataset*\)

    -   Supporting entities:
        -   One remote table for each associated dimension, hierarchy, and text entity.



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `ANALYTICAL_DIMENSION`
    
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
    
    </td>
    <td valign="top">
    
    \(none\)
    
    </td>
    <td valign="top">
    
    -   Selected entity:
        -   One remote table \(*Text*\)



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `ANALYTICAL_PARENT_CHILD_HIERARCHY_NODE`
    
    </td>
    <td valign="top">
    
    \(none\)
    
    </td>
    <td valign="top">
    
    -   Selected entity:
        -   One remote table \(*Hierarchy*\)



    
    </td>
    </tr>
    </table>
    
    > ### Note:  
    > When importing from an SAP S/4HANA on-premise connection using data access *Remote Tables*, only a business entity and a remote table are created for the selected entity. Associated objects are not created.

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


6.  Navigate to the appropriate objects to review data access:

    -   *Replication Flow to Local Tables* - Open the replication flow and run it \(or create a schedule\) to replicate the data \(see [Running a Flow](running-a-flow-5b591d4.md)\).
    -   *Remote Tables* - By default, data is only federated. To replicate the data, open the *Data Integration Monitor* \(see [Replicating Data and Monitoring Remote Tables](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/4dd95d7bff1f48b399c8b55dbdd34b9e.html "In the Remote Tables monitor, you can find a remote table monitor per space. Here, you can copy data from remote tables that have been deployed in your space into SAP Datasphere, and you can monitor the replication of the data. You can copy or schedule copying the full set of data from the source, or you can set up replication of data changes in real-time via change data capturing (CDC).") :arrow_upper_right:\).
    -   *Local Tables* - In cases where only local tables are imported, you must find an appropriate method to load data to them.


