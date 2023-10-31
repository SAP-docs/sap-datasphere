<!-- loioc05b6a6d06db427dbdd3041d61fd5840 -->

# Lock or Unlock Your Space

If a space exceeds its assigned storage or if the audit logs enabled in the space consume too much disk storage, the space is automatically locked.

If you want to put a space on hold and you are a space administrator, you can manually lock it.

When a space is locked, users assigned to the space can continue to create and modify objects and save their changes in the repository, but they cannot deploy their changes to the run-time database.



<a name="loioc05b6a6d06db427dbdd3041d61fd5840__section_ywh_f13_w5b"/>

## Space Locked as it Has Exceeded its Assigned Storage

If a space exceeds its allocations of in-memory or disk storage, it will be locked until a space user deletes the excess data or an administrator assigns additional storage.

In this situation, these actions are possible:

-   Users assigned to a space can delete data to bring the space back under the limit of its assigned storage.
-   A space administrator can use the *Unlock* button on the *Space Management* page or on the space page to unlock the space for a 24-hour grace period, in case urgent changes must be deployed.
-   An administrator can assign more disk and/or in-memory storage to the space \(see [Allocate Storage to a Space](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/f414c3d62bfe49b38e2cfdd7b4e7d786.html "Use the Storage Assignment properties to allocate disk and in-memory storage to the space and to choose whether it will have access to the SAP HANA data lake.") :arrow_upper_right:\).



<a name="loioc05b6a6d06db427dbdd3041d61fd5840__section_qw3_gc3_w5b"/>

## Space Locked as Audit Logs Consume Too Much Disk Storage

If the total size of all audit logs across all spaces has reached 50% of the tenant disk storage, the system automatically locks any spaces whose audit logs consume more than 30% of the total audit log size.

In this situation, these actions are possible:

-   A space administrator can use the *Unlock* button on the *Space Management* page or on the space page to unlock the space for a 24-hour grace period, in case urgent changes must be deployed.
-   An administrator can delete audit logs and free up disk space \(see [Delete Audit Logs](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/589fa4251db74fb7955eeee5d86fc25c.html "Delete audit logs and free up disk space.") :arrow_upper_right:\).
-   A space administrator can disable audit logs or decrease the number of days audit logs are kept for \(see [Enable Audit Logging](enable-audit-logging-2665539.md)\).




<a name="loioc05b6a6d06db427dbdd3041d61fd5840__section_hvr_m23_w5b"/>

## Lock or Unlock a Space

-   To lock or unlock one or more spaces, in the side navigation area, click ![](Integrating-Data-Via-Database-Users/Open-SQL-Schema/images/Space_Management_a868247.png) \(*Space Management*\), locate and select one or more space tiles, and use the *Lock* or *Unlock* buttons.

-   To lock or unlock only one space, you can alternatively select the space tile, click *Edit* to open it and use the *Lock* or *Unlock* buttons.


