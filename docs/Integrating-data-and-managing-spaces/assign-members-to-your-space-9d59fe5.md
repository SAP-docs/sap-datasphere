<!-- loio9d59fe511ae644d98384897443054c16 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Assign Members to Your Space

As a Space Administrator, you can assign users as members of your space.



**Prerequisites**

-   A user with the Administrator role has assigned you as a member of the space.

-   The users that you want to add as members of the space have been created in <span style="font-size:16px;"><span class="FPA-icons"></span></span> *Security* → <span style="font-size:16px;"><span class="FPA-icons"></span></span> *Users*.


**Procedure**

1.  In the side navigation area, click ![](Integrating-Data-Via-Database-Users/Open-SQL-Schema/images/Space_Management_a868247.png) \(*Space Management*\), locate your space tile, and click *Edit* to open it.

2.  In the *Members* section, click *Add*.

3.  Choose the members from the list of SAP Datasphere users and click *Add*.

    Depending on the roles that the users have, they are able to do different actions in the space:

    -   Roles providing privileges to work in SAP Datasphere spaces:
        -   **DW Space Administrator** - Can manage all aspects of a space \(except the *Storage Assignment* and *Workload Management* properties\) and can create data access controls and use the *Content Network*.
        -   *DW Integrator* - Can integrate data via connections and can manage and monitor data integration in spaces of which they are a member.
        -   **DW Modeler** - Can create and edit objects in the *Data Builder* and *Business Builder* and view data in all objects in spaces of which they are a member.
        -   **DW Viewer** - Can view objects in spaces of which they are a member and view data output by views that are exposed for consumption in these spaces.

    -   Roles providing privileges to consume the data exposed by SAP Datasphere spaces:
        -   **DW Consumer** - Can consume data exposed by SAP Datasphere spaces of which they are members using SAP Analytics Cloud, and other clients, tools, and apps, but cannot log into SAP Datasphere. This role is intended for business analysts and other users who use SAP Datasphere data to drive their visualizations, but who have no need to access the modeling environment.



The users you've added as members of the space are dislayed in the table of the *Members* area.

You can also use the SAP Datasphere command line interface, `dwc`, to assign members to a space. For more information, see [Manage Spaces via the Command Line](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/5eac5b71e2d34c32b63f3d8d47a0b1d0.html "You can use the SAP Datasphere command line interface, datasphere, to create, read, update, and delete spaces. You can set space properties, assign (or remove) members, create database users, create or update objects (tables, views, and data access controls), and associate HDI containers to a space.") :arrow_upper_right:.

