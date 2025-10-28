<!-- loio095dbdf8db444b279e61b1dcf64150a2 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Create SAP S/4HANA Live Data Connection of Type Tunnel

To securely connect to SAP S/4HANA on-premise when searching for ABAP CDS Views to be imported with the *Import Entities* wizard, you need to connect via Cloud Connector. This requires that you create a live data connection of type tunnel to the SAP S/4HANA system.



<a name="loio095dbdf8db444b279e61b1dcf64150a2__prereq_o3n_brv_rxb"/>

## Prerequisites

In addition, consider the prerequisites in[Model Import \(Data Access: Remote Tables\)](prepare-connectivity-to-sap-s-4hana-on-premise-8de01dd.md#loio8de01dd25c1e443e8e2de7d2fbe1364d__prereq_mt_S4_OP).



## Procedure

1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(*System*\) ** \> ** :wrench: \(*Configuration*\) ** \> *Data Integration*.

2.  In the *Live Data Connections \(Tunnel\)* section, click *Manage Live Data Connections*.

    The *Manage Live Data Connections* dialog appears.

3.  On the *Connections* tab, click :heavy_plus_sign:.

    The *Select a data source* dialog appears.

4.  Expand *Connect to Live Data* and select *SAP S/4HANA*.

    The *New S/4HANA Live Connection* dialog appears.

5.  Enter a name and description for your connection. Note that the connection name cannot be changed later.

6.  Set the *Connection Type* to *Tunnel*.

7.  Select the Location ID.

    > ### Note:  
    > In the next step, you will need to specify the virtual host that is mapped to your on-premise system. This depends on the settings in your selected Cloud Connector location.

8.  Add your SAP S/4HANA host name, HTTPS port, and client.

    Use the virtual host name and virtual port that were configured in the Cloud Connector.

9.  Optional: Choose a *Default Language* from the list.

    This language will always be used for this connection and cannot be changed by users without administrator privileges.

    > ### Note:  
    > You must know which languages are installed on your SAP S/4HANA system before adding a language code. If the language code you enter is invalid, SAP Datasphere will default to the language specified by your system metadata.

10. Under *Authentication Method* select *User Name and Password*.

11. Enter user name \(case sensitive\) and password of the technical user for the connection.

12. Select *Save this credential for all users on this system*.

13. Click *OK*.




<a name="loio095dbdf8db444b279e61b1dcf64150a2__result_vbf_zqg_2nb"/>

## Results

The connection is saved and now available for selection in the SAP Datasphere connection creation wizard for the *SAP S/4HANA On-Premise* connection.

