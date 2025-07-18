<!-- loio73068ac8e1934615b419d8c6c4095a9a -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Copy a Space and its Contents

You can copy a space and all the *Data Builder* objects it contains into a new space.



<a name="loio73068ac8e1934615b419d8c6c4095a9a__prereq_okr_vnr_mdc"/>

## Prerequisites

To copy a space and its contents, you must have a global role that grants you the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Spaces* \(`C-------`\) - To create spaces.
-   *Spaces* \(`-------M`\) - To update all spaces and space properties.

The *DW Administrator* global role, for example, grants these privileges. For more information, see [Privileges and Permissions](../Managing-Users-and-Roles/privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](../Managing-Users-and-Roles/standard-roles-delivered-with-sap-datasphere-a50a51d.md). 

> ### Note:  
> A space cannot be copied if it contains any *Business Builder* objects.
> 
> If the space is used as storage by an associated SAP Analytics Cloud tenant, then it cannot be copied if any SAP Analytics Cloud objects are exposed \(see [Exposing Objects for Consumption in SAP Datasphere](https://help.sap.com/docs/SAP_ANALYTICS_CLOUD/fc70db459bea4083bb50c51c87ff9cf0/0bf207d4b49c4adeb70c36e023eecf9f.html)\).

> ### Note:  
> Relevant only for spaces with a storage type *SAP HANA Database \(Disk and In-Memory\)*, and not for *SAP HANA Data Lake Files* spaces.



## Context

If you copy a space that contains objects protected by a namespace, the copied objects will be modified so that they are removed from the namespace and become editable. Copying protected content in this way allows you to extend content delivered through SAP Business Data Cloud \(see [Extending Intelligent Applications](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/3c158685865d4b408938a148e828e21f.html "The data products installed via SAP Business Data Cloud as part of an intelligent application do not include any extensions defined in your source system. However, you can update the data products to include any required custom fields, and adjust the delivered views and analytic models to consume them.") :arrow_upper_right:\).



<a name="loio73068ac8e1934615b419d8c6c4095a9a__steps_zjt_j44_ccc"/>

## Procedure

1.  In the side navigation area, click ![](../images/Space_Management_a868247.png) \(*Space Management*\), locate your space tile, and click *Edit* to open it.

2.  Click <span class="FPA-icons-V3"></span> \(More\)** \> *Copy*.

3.  Enter the name of the new space who want to copy to.

    By default, the contents of the space will be copied to the new space, but will not be deployed. To have them deployed, select *Deploy Objects*.

4.  Click *Copy*.

    The following actions are performed:

    -   The new space is configured exactly as the original space but has a new *Space ID* and *Space Name*.
    -   The following objects are copied:

        -   All *Data Builder* objects.
        -   All connections \(credentials need to be re-entered unless the connection is a shared UCL connection\).

        > ### Note:  
        > Replication task schedules are not copied and must be recreated manually.

    -   Any objects shared to the original space are shared to the new space.
    -   The new space is added as a scope to all scoped roles that the original space belongs to, but no users are added to the new space, by default.

        For information about adding users to a space, see [Create a Scoped Role to Assign Privileges to Users in Spaces](../Managing-Users-and-Roles/create-a-scoped-role-to-assign-privileges-to-users-in-spaces-b5c4e0b.md).


    You will receive a notification when the copy is complete.


