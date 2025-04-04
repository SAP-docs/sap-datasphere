<!-- loioc05b6a6d06db427dbdd3041d61fd5840 -->

# Unlock a Locked Space

When a space exceeds its assigned storage or when the audit logs enabled in the space consume too much disk storage, the space is automatically locked after 60 minutes if you do not free up space.

When a space is locked, users assigned to the space can continue to create and modify objects and save their changes in the repository, but they cannot deploy their changes to the run-time database.



<a name="loioc05b6a6d06db427dbdd3041d61fd5840__section_bhc_y2j_42c"/>

## Prerequisites

To manually lock or unlock your space, you must have a scoped role that grants you access to your space with the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Spaces* \(`-RU-----`\) - To open and update your space in the *Space Management* tool.
-   *Spaces Files* \(`-RU-----`\) - To read and update objects in your space.

The *DW Space Administrator* role template, for example, grants these privileges. For more information, see [Privileges and Permissions](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/d7350c6823a14733a7a5727bad8371aa.html "A privilege represents a task or an area in SAP Datasphere and can be assigned to a specific role. The actions that can be performed in the area are determined by the permissions assigned to a privilege.") :arrow_upper_right: and [Standard Roles Delivered with SAP Datasphere](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/a50a51d80d5746c9b805a2aacbb7e4ee.html "SAP Datasphere is delivered with several standard roles. A standard role includes a predefined set of privileges and permissions.") :arrow_upper_right:. 

> ### Note:  
> Relevant only for spaces with a storage type *SAP HANA Database \(Disk and In-Memory\)*, and not for *SAP HANA Data Lake Files* spaces.



<a name="loioc05b6a6d06db427dbdd3041d61fd5840__section_ywh_f13_w5b"/>

## Space Locked as it Has Exceeded its Assigned Storage

If a space exceeds its allocations of memory or disk storage, it will be locked until a space user deletes the excess data or an administrator assigns additional storage.

In this situation, these actions are possible:

-   Users assigned to a space can delete data to bring the space back under the limit of its assigned storage.
-   A space administrator can use the *Unlock* button on the *Space Management* page or on the space page to unlock the space for a 24-hour grace period, in case urgent changes must be deployed.
-   An administrator can assign more disk and/or memory storage to the space \(see [Allocate Storage to a Space](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/f414c3d62bfe49b38e2cfdd7b4e7d786.html "Use the Space Storage properties to allocate disk and memory storage to the space and to choose whether it will have access to the SAP HANA data lake.") :arrow_upper_right:\).



<a name="loioc05b6a6d06db427dbdd3041d61fd5840__section_qw3_gc3_w5b"/>

## Space Locked as Audit Logs Consume Too Much Disk Storage

If the total size of all audit logs across all spaces has reached 40% of the tenant disk storage, the system automatically locks any spaces - and deactivate any database analysis users - whose audit logs consume more than 30% of the total audit log size.

In this situation, these actions are possible:

-   A space administrator can use the *Unlock* button on the *Space Management* page or on the space page to unlock the space for a 24-hour grace period, in case urgent changes must be deployed.
-   An administrator can delete audit logs and free up disk space \(see [Delete Audit Logs](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/589fa4251db74fb7955eeee5d86fc25c.html "Delete audit logs and free up disk storage.") :arrow_upper_right:\).
-   A space administrator can disable audit logs or decrease the number of days audit logs are kept for \(see [Logging Read and Change Actions for Audit](logging-read-and-change-actions-for-audit-2665539.md)\).




<a name="loioc05b6a6d06db427dbdd3041d61fd5840__section_hvr_m23_w5b"/>

## Lock a Space

If you want to put a space on hold and you are a space administrator, you can manually lock it.

-   To lock one or more spaces, in the side navigation area, click ![](Integrating-Data-Via-Database-Users/Open-SQL-Schema/images/Space_Management_a868247.png) \(*Space Management*\), locate and select one or more space tiles, and click the *Lock* button.

-   To lock only one space, you can alternatively select the space tile, click *Edit* to open it and click the *Lock* button.


> ### Note:  
> You can unlock one or more spaces that have been manually locked by using the *Unlock* button.

