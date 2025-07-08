<!-- loio5d02f1103dd742aab5c0fc930debe51b -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Create Live Data Connection of Type Tunnel

To securely connect and make http requests to SAP BW∕4HANA, you need to connect via Cloud Connector. This requires that you create a live data connection of type tunnel to the SAP BW∕4HANA system.



<a name="loio5d02f1103dd742aab5c0fc930debe51b__prereq_sz1_frg_2nb"/>

## Prerequisites

See the prerequisites 1 to 5 in [Preparing SAP BW/4HANA Model Transfer Connectivity](preparing-sap-bw-4hana-model-transfer-connectivity-962de2f.md).



## Procedure

1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(*System*\) ** \> ** :wrench: \(*Configuration*\) ** \> *Data Integration*.

2.  In the *Live Data Connections \(Tunnel\)* section, click *Manage Live Data Connections*.

    The *Manage Live Data Connections* dialog appears.

3.  On the *Connections* tab, click :heavy_plus_sign:.

    The *Select a data source* dialog will appear.

4.  Expand *Connect to Live Data* and select *SAP BW*.

    The *New BW Live Connection* dialog appears.

5.  Enter a name and description for your connection. Note that the connection name cannot be changed later.

6.  Set the *Connection Type* to *Tunnel*.

    By enabling tunneling, data from the connected source will always be transferred through the Cloud Connector.

7.  Select the Location ID.

    > ### Note:  
    > In the next step, you will need to specify the virtual host that is mapped to your on-premise system. This depends on the settings in your selected Cloud Connector location.

8.  Add your SAP BW∕4HANA host name, HTTPS port, and client.

    Use the virtual host name and virtual port that were configured in the Cloud Connector.

9.  Optional: Choose a *Default Language* from the list.

    This language will always be used for this connection and cannot be changed by users without administrator privileges.

    > ### Note:  
    > You must know which languages are installed on your SAP BW∕4HANA system before adding a language code. If the language code you enter is invalid, SAP Datasphere will default to the language specified by your system metadata.

10. Under *Authentication Method*, select *User Name and Password*.

11. Enter user name \(case sensitive\) and password of the technical user for the connection.

    The user needs the following authorizations:

    -   Authorization object S\_BW4\_REST \(authorization field: BW4\_URI, value: /sap/bw4/v1/dwc\*\)

    -   Authorization object SDDLVIEW \(authorization field: DDLSRCNAME, value: RSDWC\_SRCH\_QV\)

    -   Read authorizations for SAP BW∕4HANA metadata \(Queries, CompositeProviders and their InfoProviders\)

        Using authorizations for SAP BW∕4HANA metadata, you can restrict a model transfer connection to a designated semantic SAP BW/4HANA area.

        For more information, see [Overview: Authorization Objects](https://help.sap.com/viewer/107a6e8a38b74ede94c833ca3b7b6f51/2.0.latest/en-US/4c658f3245e31ca6e10000000a42189c.html) in the SAP BW∕4HANA documentation.


12. Select *Save this credential for all users on this system*.

13. Click *OK*.

    > ### Note:  
    > While saving the connection, the system checks if it can access /sap/bc/ina/ services in SAP BW∕4HANA.




<a name="loio5d02f1103dd742aab5c0fc930debe51b__result_vbf_zqg_2nb"/>

## Results

The connection is saved and now available for selection in the SAP Datasphere connection creation wizard for the SAP BW∕4HANA Model Transfer connection.

