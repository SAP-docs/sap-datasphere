<!-- loio8f149b00b1064770afc0deb2ff749ee8 -->

# Pausing and Restarting Real-Time Replication

To avoid any impacts on real-time replication while performing maintenance activities in the underlying source system, or while applying changes to the SAP HANA smart data integration Data Provisioning agent, you can pause and restart real-time replication.

Whenever you need to perform maintenance operations in one or more underlying source systems, with the `DW Space Administrator` role you can pause real-time replication for selected connections that connect to the sources through a Data Provisioning agent in the *Connections* application. For more information, see [Pause Real-Time Replication for a Connection](../Integrating-Data-Via-Connections/pause-real-time-replication-for-a-connection-a11f244.md).

Whenever you need to upgrade or patch your Data Provisioning agent, or you need to apply any changes to its configuration, with the `DW Administrator` role you can pause real-time replication for all connections that use a specific Data Provisioning agent in the *Configuration* \> *Data Integration* \> *On-Premise Agents*. For more information, see [Pause Real-Time Replication for an Agent](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/internal/en-US/dac31a5e96cb41cf98383668d01d22cc.html "For a selected SAP HANA Smart Data Integration Data Provisioning Agent, you can pause real-time replication for the connections that use the agent while applying changes to it, such as configuration changes or applying patches. After you have finished your agent changes, you can restart real-time replication.") :arrow_upper_right:.

> ### Note:  
> From remote tables using an SAP HANA Cloud connection, you can’t pause the replication in the *Connections* application if SAP HANA smart data access is used.

