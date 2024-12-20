<!-- loio2629b2e8d2d54754bee3e83196b7f710 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Add a Connection to a System in Unified Customer Landscape to the Space

For systems that are integrated with SAP Datasphere in the Unified Customer Landscape of SAP BTP, connections are generated in SAP Datasphere when creating a formation. These generated connections are not assigned to any space yet. If an administrator in the *Configuration* tool has allowed the connection to be added to your space, users with an integrator role can add the connection to the space in the *Connections* app.



<a name="loio2629b2e8d2d54754bee3e83196b7f710__prereq_bnc_gmy_rbc"/>

## Prerequisites

In <span class="FPA-icons-V3"></span> \(*System*\) ** \> ** :wrench: \(*Configuration*\) ** \> *Unified Customer Landscape*, an administrator has added your space to the list of spaces in which space users are allowed to add the connection.

For more information, see [Defining Allowed Spaces for Unified Customer Landscape Connections](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/67ec785b5de842488781f20c4ab52a9f.html "For remote systems that are integrated with SAP Datasphere in the Unified Customer Landscape, connections are generated in SAP Datasphere. These generated connections are not assigned to any spaces yet. In the Configuration tool, users with an administrator role can control which spaces users with an integrator role can add the connection to. Once added to a space, space users can use the connection to replicate data with replication flows from the remote systems.") :arrow_upper_right:.



## Procedure

1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(*Connections*\) and select a space if necessary.

2.  On the *Connections* tab, click <span class="FPA-icons-V3"></span> \(Add Connection\) ** \> *Add Connection to System in Unified Customer Landscape*.

3.  In the following dialog, select the generated connection and click *Add*.

    When adding the connection to the list, its configuration gets completed with all required configuration and credentials. The remote source system is now connected to SAP Datasphere and the connection is available for use in replication flows.


