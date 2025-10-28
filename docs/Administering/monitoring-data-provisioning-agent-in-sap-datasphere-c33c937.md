<!-- loioc33c9374b62b458f84ee23ed1ca69bc8 -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Monitoring Data Provisioning Agent in SAP Datasphere

For connected Data Provisioning Agents, you can proactively become aware of resource shortages on the agent instance and find more useful information.



<a name="loioc33c9374b62b458f84ee23ed1ca69bc8__section_qpt_gs1_xgc"/>

## Prerequisites



<a name="loioc33c9374b62b458f84ee23ed1ca69bc8__section_ohx_hs1_xgc"/>

## Monitoring Information Available in SAP Datasphere

1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(*System*\) ** \> ** :wrench: \(*Configuration*\) ** \> *Data Integration*.
2.  In the *On-Premise Agents* section, click *Monitor* to show the following information:
    -   Information about free and used physical memory and swap memory on the Data Provisioning Agent server.

    -   Information about when the agent was connected the last time.

    -   Information about the overall number of connections that use the agent and the number of connections that actively use real-time replication, with active real-time replication meaning that the connection type supports real-time replication and for the connection at least one table is replicated via real-time replication.

        You can change to the *Connections* view to see the agents with a list of all connections they use and their real-time replication status. You can pause real-time replication for the connections of the while applying changes to the agent. For more information, see [Pause Real-Time Replication for an Agent](pause-real-time-replication-for-an-agent-dac31a5.md).



