<!-- loioa11f2441b840405c91918de757589097 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Pause Real-Time Replication for a Connection

Pause real-time replication for a connection while updating or maintaining the source. After you have finished with your maintenance activities you can restart real-time replication.



<a name="loioa11f2441b840405c91918de757589097__context_kg3_ppt_y4b"/>

## Context

You can pause real-time replication for connections that connect to a source through SAP HANA Smart Data Integration and its Data Provisioning Agent.

If you need to upgrade or patch your Data Provisioning Agent, or you need to apply any changes to its configuration, you can pause all connections for the Data Provisioning Agent. For more information, see [Pause Real-Time Replication for an Agent](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/dac31a5e96cb41cf98383668d01d22cc.html "For a selected SAP HANA Smart Data Integration Data Provisioning Agent, you can pause real-time replication for the connections that use the agent while applying changes to it, such as configuration changes or applying patches. After you have finished your agent changes, you can restart real-time replication.") :arrow_upper_right:.



## Procedure

1.  In the side navigation area, click <span class="FPA-icons"></span> \(*Connections*\), select a space if necessary, and then click the *Local Connections* tab.

2.  In the list of connections, you can see the *Real-Time Replication Status* for each connection. Depending on the status you can perform different actions.


    <table>
    <tr>
    <th valign="top">

    Real-Time Replication status
    
    </th>
    <th valign="top">

    Possible actions
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Not Applicable*

    Shown when the connection type doesn't support real-time replication.

    Shown when the *Remote Tables* feature for an SAP HANA connection is set to *Data Access* = *Remote Only*.
    
    </td>
    <td valign="top">
    
    none
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Active*

    Shown when the connection type supports real-time replication and for the connection at least one table is replicated via real-time replication \(even if the status in the *Remote Table Monitor* is *Error*\).
    
    </td>
    <td valign="top">
    
    Pause
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Paused*

    Shown when the connection type supports real-time replication and for the connection at least for one table real-time replication is paused.
    
    </td>
    <td valign="top">
    
    Restart
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Inactive*

    Shown when the connection type supports real-time replication and for the connection currently there is no table replicating via real-time replication.
    
    </td>
    <td valign="top">
    
    Pause
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Disconnected*

    Shown when the connection uses a Data Provisioning Agent that currently has status *Disconnected*.
    
    </td>
    <td valign="top">
    
    none
    
    </td>
    </tr>
    </table>
    
3.  From the list of connections, select the connection in question and click *Pause*.

    The status in the list of the connections changes from *Active* or *Inactive* to *Paused*.

    In the *Remote Table Monitor*, the status for affected tables changes to *Paused* and actions related to real-time replication are not available for these tables. Also, you cannot start real-time replication for any table of a paused connection.

4.  You can now perform maintenance activities in the source.

5.  Once your maintenance activities finished, restart real-time replication. Select the connection in question and click *Restart*.

    The status in the list of the connections as well as in the *Remote Table Monitor* changes accordingly and you can again perform real-time related actions for the tables or start real-time replication.


