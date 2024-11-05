<!-- loio67ec785b5de842488781f20c4ab52a9f -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Defining Allowed Spaces for Unified Customer Landscape Connections

For remote systems that are integrated with SAP Datasphere in the Unified Customer Landscape, connections are generated in SAP Datasphere. These generated connections are not assigned to any spaces yet. In the *Configuration* tool, users with an administrator role can control which spaces users with an integrator role can add the connection to. Once added to a space, space users can use the connection to replicate data with replication flows from the remote systems.



<a name="loio67ec785b5de842488781f20c4ab52a9f__section_tsl_b2w_rbc"/>

## Prerequisites

In SAP BTP Unified Customer Landscape, a formation with type *Integration with SAP Datasphere* has been created integrating your SAP Datasphere tenant with one or more remote systems.



<a name="loio67ec785b5de842488781f20c4ab52a9f__section_ysv_4dw_rbc"/>

## Context

Formations of type *Integration with SAP Datasphere* including a SAP Datasphere tenant and one or more remote systems generate one or more connections \(with connection type *SAP HANA Cloud, Data Lake Files*\) in the same SAP Datasphere tenant. The generated connections are not available for use in any space yet. Before such a connection can be used in a space:

1.  In the *Configuration* tool, an administrator must decide to which spaces users with an integrator role are allowed to add the connection \(see below\).

2.  In the *Connections* app, a space user with an integrator role must add the connection to the space \(see [Add a Connection to a System in Unified Customer Landscape to the Space](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/2629b2e8d2d54754bee3e83196b7f710.html "For systems that are integrated with SAP Datasphere in the Unified Customer Landscape of SAP BTP, connections are generated in SAP Datasphere when creating a formation. These generated connections are not assigned to any space yet. If an administrator in the Configuration tool has allowed the connection to be added to your space, users with an integrator role can add the connection to the space in the Connections app.") :arrow_upper_right:\).


For more information about creating formations, see [Including Systems in a Formation](https://help.sap.com/docs/btp/sap-business-technology-platform/including-sap-systems-in-formation) in the *SAP Business Technology Platform* documentation.



<a name="loio67ec785b5de842488781f20c4ab52a9f__section_uyw_sdw_rbc"/>

## Procedure

1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(*System*\) ** \> ** :wrench: \(*Configuration*\) ** \> *Unified Customer Landscape*.

2.  \[optional\] Select a generated connection and choose *Edit Business Name* to provide a more reasonable business name.

3.  To allow adding a connection to selected spaces, click <span class="SAP-icons-V5"></span> \(Details\) to open the side panel.

4.  In the side panel, use the following options to define the list of spaces in which you allow space users to add and use the connection:

    -   Choose *Add* to add one or more spaces to the list and confirm your selection.

    -   Enable the *Allow Connection in All Spaces* option to add all available spaces to the list.

        > ### Note:  
        > Once you enabled the option, the following applies:
        > 
        > -   You cannot remove spaces from the list but only disable the option to remove all spaces.
        > 
        > -   You can only disable the option if the connection hasn't been added to any space in the *Connections* app \(see the *Connections Added* column in the list of spaces\).

    -   Select one or more spaces and choose *Remove* to remove the selected spaces from the list.

        > ### Note:  
        > -   You can only remove a space if the connection hasn't been added to the space in the *Connections* app \(see the *Connections Added* column in the list of spaces\).
        > 
        > -   You cannot remove spaces when you enabled the *Allow Connection in All Spaces* option.



