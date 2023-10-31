<!-- loiodac31a5e96cb41cf98383668d01d22cc -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Pause Real-Time Replication for an Agent

For a selected SAP HANA Smart Data Integration Data Provisioning Agent, you can pause real-time replication for the connections that use the agent while applying changes to it, such as configuration changes or applying patches. After you have finished your agent changes, you can restart real-time replication.



<a name="loiodac31a5e96cb41cf98383668d01d22cc__context_t3g_gpm_jrb"/>

## Context

If you need to perform maintenance activities in a source system, you can pause real-time replication for the corresponding connection. For more information, see [Pause Real-Time Replication for a Connection](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/a11f2441b840405c91918de757589097.html "Pause real-time replication for a connection while updating or maintaining the source. After you have finished with your maintenance activities you can restart real-time replication.") :arrow_upper_right:.



## Procedure

1.  In SAP Datasphere, from the <span class="SAP-icons"></span>main menu, open *Configuration* \> *Data Integration* \> *On-Premise Agents*.

2.  To show the Data Provisioning Agent tiles with a list of all connections they use, click the *Connections* button.

    The real-time replication status of a connection shown here, can be:


    <table>
    <tr>
    <th valign="top">

    Real-Time Replication status
    
    </th>
    <th valign="top">

    When do we show the status?
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Active*
    
    </td>
    <td valign="top">
    
    The connection type supports real-time replication and for the connection at least one table is replicated via real-time replication \(even if the status in the *Remote Table Monitor* is *Error*\).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Inactive*
    
    </td>
    <td valign="top">
    
    The connection type supports real-time replication and for the connection currently there is no table replicating via real-time replication.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Paused*
    
    </td>
    <td valign="top">
    
    The connection type supports real-time replication and for the connection at least for one table real-time replication is paused.
    
    </td>
    </tr>
    </table>
    
3.  To pause the agent's connections with replication status *Active* or *Inactive*, on the tile of the agent choose <span class="SAP-icons"></span> \(menu\) and then <span class="SAP-icons"></span> *Pause All Connections*.

    In the list of connections shown on the tile, the status for affected connections changes to *Paused*. You can also see the status change for the connections in the *Connections* application.

    In the *Remote Table Monitor* the status for affected tables changes to *Paused* and actions related to real-time replication are not available for these tables. Also, you cannot start real-time replication for any table of a paused connection.

4.  You can now apply the changes to your Data Provisiong Agent.

5.  Once you're finished with the changes, restart real-time replication for the agent. Choose <span class="SAP-icons"></span> \(menu\) and then :arrow_forward: *Restart All Connections*.

    The status in the list of connections shown on the tile, in the *Connections* application as well as in the *Remote Table Monitor* changes accordingly and you can again perform real-time related actions for the tables or start real-time replication.


