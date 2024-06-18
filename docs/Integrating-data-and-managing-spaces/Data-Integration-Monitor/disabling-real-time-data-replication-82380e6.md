<!-- loio82380e6f01c84fac898a285ac40a1e50 -->

# Disabling Real-Time Data Replication

Disable real-time data replication even if your source system is unreachable, and switch the data access from *Replicated \(Real-time\)* to *Replicated \(Snapshot\)*.

If the source system is not reachable or if you simply don' t need to get your data updated in real-time, you can disable the real-time data replication.

From the *Remote Tables* monitor, select one or more remote tables and click *Data Replication* \> *Disable Real-Time Data Replication*.

> ### Note:  
> The selected remote tables must fulfill the following requirements to support disabling real-time data replication:
> 
> -   The remote table must be in real-time data replication.
> 
> -   The remote table must be connected via SAP HANA smart data integration \(in the connection, *Data Provisioning* option is set to *Data Provisioning Agent*\) and not via SAP HANA smart data access.

When you disable the real-time data replication, it changes the data access from *Replicated \(Real-Time\)* to *Replicated \(Snapshot\)*. It preserves the replica table and its replicated data to allow further data consumption.

Switching the data access from *Replicated \(Real-Time\)* to *Replicated \(Snapshot\)* allows you to:

-   Delete the remote table as it is not possible to delete a remote table, which is in data access *Replicated \(Real-time\)*.
-   Change the properties of the connection. For more information, see [Modify or Duplicate Remote Tables](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/8c3632f28dc94e068dbdab8fe9bbeeb9.html "From the remote table editor, you can change the remote table connection and/or the remote table source object. You can also create a copy of an existing remote table.") :arrow_upper_right:.

> ### Note:  
> If your remote table is connected via SAP HANA smart data access, you can delete it. This will stop the data replication in real-time and you’ll be able to modify the connection details and restart a data replication.

