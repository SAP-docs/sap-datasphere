<!-- loio27d4c686dc9f49c5bd70d826232ee814 -->

# Manage Tenant Disk Storage

You should regularly monitor your tenant disk storage and delete unneeded data. To protect your tenant from storage-related outages, SAP Datasphere locks all spaces once a critical threshold of disk usage is attained. In such a case, to continue working with your tenant, you must either increase your tenant disk storage or delete unneeded data.



## Monitor Your Tenant Disk Storage

You can monitor your tenant disk storage usage in the *System Monitor* \(see [Monitoring SAP Datasphere in the System Monitor](Monitoring-SAP-Datasphere/monitoring-sap-datasphere-in-the-system-monitor-28910cd.md)\).



## Increase Your Tenant Storage

You can increase the disk storage of your tenant in the *Tenant Configuration* page \(see [Configure the Size of Your SAP Datasphere Tenant](Creating-and-Configuring-Your-Tenant/configure-the-size-of-your-sap-datasphere-tenant-33f8ef4.md)\).



## Delete Tenant Data

You can perform the following actions to delete data and reduce your tenant disk storage usage:

-   Delete unneeded spaces and all their data - A user with a space administrator role can delete unneeded spaces \(see [Delete Your Space](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/3eb19b96e6ba41dfbffd759c5c8370bb.html "Delete a space if you are sure that you no longer need any of its content or data. The space is moved to the recycle bin, from which it can either be restored or permanently deleted from the database.") :arrow_upper_right:\), then a user with an administrator role can empty the recycle bin and therefore permanently delete the spaces and their data \(see [Restore Spaces from, or Empty the Recycle Bin](Creating-Spaces-and-Allocating-Storage/restore-spaces-from-or-empty-the-recycle-bin-c4e26c0.md).
-   Delete audit logs for spaces or database analysis users - A user with an administrator role can delete audit logs \(see [Delete Audit Logs](delete-audit-logs-589fa42.md)\).
-   Delete task logs generated for run activities - A user with an administrator role can delete task logs \(see [Delete Task Logs to Reduce Storage Consumption](delete-task-logs-to-reduce-storage-consumption-c690202.md)\).

> ### Note:  
> To delete data in a space that is locked, you must first unlock the space \(see [Unlock a Locked Space](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/c05b6a6d06db427dbdd3041d61fd5840.html "When a space exceeds its assigned storage or when the audit logs enabled in the space consume too much disk storage, the space is automatically locked after 60 minutes if you do not free up space. Also, when the tenant disk usage has reached a critical threshold, all spaces are automatically locked to protect your tenant from storage-related outages.") :arrow_upper_right:\).

