<!-- loio845fedbd28574aa8b84239df848936f6 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Import Semantically-Rich Entities from SAP BW Bridge and SAP S/4HANA Cloud

You can use the *Import Entities* wizard to import semantically-rich objects from SAP BW Bridge and SAP S/4HANA Cloud connections. The wizard creates *Business Builder* and *Data Builder* entities \(along with all the objects on which they depend\) in SAP Datasphere.



## Context

The following connection types are supported in the *Import Entities* wizard:

-   SAP BW Bridge \(see [Using SAP Datasphere, SAP BW Bridge in SAP Datasphere](https://help.sap.com/viewer/07fda46007d24ff7b8af36b26f9b9634/cloud/en-US/b2a2df3c588849a494295aff0aa698a0.html "SAP Datasphere, SAP BW bridge enables you to use SAP BW functionality in the public cloud, to convert SAP BW∕4HANA and SAP BW models into SAP BW bridge models, and to import SAP BW bridge models into SAP Datasphere.") :arrow_upper_right:\)

    > ### Note:  
    > You must have a user in the bridge tools with the business role template `SAP_DW4_BC_MODELING_DWC_PC` \(see [Business Role Templates](https://help.sap.com/docs/SAP_BW_BRIDGE/107a6e8a38b74ede94c833ca3b7b6f51/75d2fa4c36a548ca86d0b8527123beb6.html) in the *SAP Data Warehouse Cloud, SAP BW Bridge* documentation\).

-   SAP S/4HANA Cloud \(see [SAP S/4HANA Cloud Connections](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/a98e5ffdf47c44d9a845dca01a18bd82.html "Use an SAP S/4HANA Cloud connection to access or import extraction-enabled ABAP Core Data Services views (ABAP CDS views) from SAP S/4HANA Cloud.") :arrow_upper_right:\)

    > ### Note:  
    > All the connectivity preparations for model import must be completed, including the activation of the necessary communication scenarios in the SAP S/4HANA Cloud system \(see [Prepare Connectivity to SAP S/4HANA Cloud](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/abb159e027184c98a54fc1b2a88dd3f5.html "To be able to successfully validate and use a connection to SAP S/4HANA Cloud, certain preparations have to be made.") :arrow_upper_right:\).


We recommend that, where possible, you use the *Import Entities* wizard for importing CDS views from these connection types, as it as able to leverage their rich semantics to import higher-level objects and to follow associations to dimensions, hierarchies, and text entities and include them in the import.



## Procedure

1.  Open the wizard from the *Repository Explorer* or the *Data Builder*:

    -   In the side navigation area, click <span class="SAP-icons"></span> \(*Repository Explorer*\), and click *Import* \> *Import Entities*.
    -   In the side navigation area, click ![](../Creating-Finding-Sharing-Objects/images/Data_Builder_f73dc45.png) \(*Data Builder*\), select a space if necessary, and click *Import* \> *Import Entities*.

2.  On the *Select Connection Type* page, select the appropriate connection type, and then click *Next Step*.

3.  On the *Select Target Space* page, click the target space that you want to import the objects into, and click *Next Step*.

    If you opened the wizard from the ![](../Creating-Finding-Sharing-Objects/images/Data_Builder_f73dc45.png) \(*Data Builder*\), only your current space can be selected.

    > ### Note:  
    > The *SAP BW Bridge* space cannot be selected as the target space. When importing objects from a bridge connection, any remote tables are imported to the *SAP BW Bridge* space and automatically shared to your selected target space, where the remaining objects are imported.

4.  On the *Select Connection* page, click the specific connection that you want to import from, and click *Next Step*.

5.  On the *Select Entities* page, select the entity that you want to import from the *Results* list, and click *Next Step*.

    Use the *Search* field to search by label. Depending on your connection type, you can filter by:

    -   Application Component
    -   Modeling Pattern \(see [Supported Capabilities for CDS Views](https://help.sap.com/viewer/0f69f8fb28ac4bf48d2b57b9637e81fa/latest/en-US/6a6ff32b25dd473080e6aeddbefecfca.html) in the *SAP S/4HANA Cloud*\) documentation\)
    -   Release Contract \(see [Stability Contracts for CDS Views](https://help.sap.com/viewer/0f69f8fb28ac4bf48d2b57b9637e81fa/latest/en-US/2e4edbede2f94fb7b7f6eac856c02b19.html) in the *SAP S/4HANA Cloud*\) documentation\)

        > ### Note:  
        > Objects that have a release contract of *C1* \(and that are extraction-enabled\) can be imported as remote tables, which support data federation and replication natively. Other objects can only be imported as local tables and you must provide data replication manually by creating a data flow.

    -   Software Component

6.  On the *Review Entities* page, review the entities that you will import.

    The two tabs list all the objects that will be created in SAP Datasphere during the import of the selected entity in the *Business Builder* and *Data Builder*.

    The following objects are created when you import objects with the most common modeling patterns:


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

    Supported in: SAP BW Bridge


    
    </td>
    <td valign="top">

    -   Selected object:
        -   One consumption model containing a perspective.

    -   Supporting objects:
        -   One entity \(*Analytical Dataset*\)
        -   One entity \(*Dimension*\) for each associated dimension.



    
    </td>
    <td valign="top">

    -   Supporting objects:
        -   One view \(*Analytical Dataset*\)
        -   One remote table \(*Relational Dataset*\)
        -   One view and one remote table for each associated dimension.



    
    </td>
    </tr>
    <tr>
    <td valign="top">

    `ANALYTICAL_CUBE`

    Supported in: SAP BW Bridge


    
    </td>
    <td valign="top">

    -   Selected object:
        -   One business entity \(*Analytical Dataset*\)

    -   Supporting objects:
        -   One entity \(*Dimension*\) for each associated dimension.



    
    </td>
    <td valign="top">

    -   Selected object:
        -   One view \(*Analytical Dataset*\)
        -   One remote table \(*Relational Dataset*\)

    -   Supporting objects:
        -   One view and one remote table for each associated dimension.



    
    </td>
    </tr>
    <tr>
    <td valign="top">

    `ANALYTICAL_FACT`

    Supported in: SAP S/4HANA Cloud


    
    </td>
    <td valign="top">

    -   Selected object:
        -   One business entity \(*Analytical Dataset*\)

    -   Supporting objects:
        -   One entity \(*Dimension*\) for each associated dimension.



    
    </td>
    <td valign="top">

    -   Selected object:
        -   One view \(*Analytical Dataset*\)
        -   One remote table \(*Relational Dataset*\)

    -   Supporting objects:
        -   One view and one remote table for each associated dimension, hierarchy, and text entity.



    
    </td>
    </tr>
    <tr>
    <td valign="top">

    `ANALYTICAL_DIMENSION`

    Supported in: SAP BW Bridge, SAP S/4HANA Cloud


    
    </td>
    <td valign="top">

    -   Selected object:
        -   One business entity \(*Dimension*\)

    -   Supporting objects:
        -   One entity \(*Dimension*\) for each associated dimension.



    
    </td>
    <td valign="top">

    -   Selected object:
        -   One view \(*Dimension*\)
        -   One remote table \(*Relational Dataset*\)

    -   Supporting objects:
        -   One view and one remote table for each associated dimension, hierarchy, and text entity.



    
    </td>
    </tr>
    <tr>
    <td valign="top">

    `ANALYTICAL_PARENT_CHILD_HIERARCHY_NODE`

    Supported in: SAP S/4HANA Cloud


    
    </td>
    <td valign="top">

    \(none\)


    
    </td>
    <td valign="top">

    -   Selected object:
        -   One remote table \(*Hierarchy*\)



    
    </td>
    </tr>
    <tr>
    <td valign="top">

    `LANGUAGE_DEPENDENT_TEXT`

    Supported in: SAP S/4HANA Cloud


    
    </td>
    <td valign="top">

    \(none\)


    
    </td>
    <td valign="top">

    -   Selected object:
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

    -   Click the first notification to see the imported objects listed in the <span class="SAP-icons"></span> \(*Repository Explorer*\).
    -   Click the second notification to view the import log messages.

        If any object could not be created, an error is given.


    The imported objects are available for review and use in the <span class="FPA-icons"></span> \(*Business Builder*\) and the ![](../Creating-Finding-Sharing-Objects/images/Data_Builder_f73dc45.png) \(*Data Builder*\).


