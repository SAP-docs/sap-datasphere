<!-- loio962de2f99d234967b8b10541599f00c6 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Preparing SAP BW/4HANA Model Transfer Connectivity

Accessing SAP BW/4HANA meta data and importing models into SAP Datasphere with a SAP BW/4HANA Model Transfer connection requires two protocols \(or endpoints\): Http and SAP HANA Smart Data Integration based on the SAP HANA adapter.

For accessing SAP BW∕4HANA, http is used to securely connect to the SAP BW∕4HANA system via Cloud Connector, and SAP HANA SQL is used to connect to the SAP HANA database of SAP BW∕4HANA via Data Provisioning Agent. Using Cloud Connector to make http requests to SAP BW∕4HANA requires a live data connection of type tunnel to SAP BW∕4HANA.

For information on supported SAP BW/4HANA source versions, see [Supported Source Versions for SAP BW∕4HANA Model Transfer Connections](supported-source-versions-for-sap-bw-4hana-model-transfer-connections-4aefe38.md).



Before creating a connection for SAP BW/4HANA Model Transfer in SAP Datasphere, you need to prepare the following:

1.  In SAP BW∕4HANA, make sure that the following services are active in transaction code SICF:

    -   BW InA - BW Information Access Services:

        -   /sap/bw/ina/GetCatalog

        -   /sap/bw/ina/GetResponse

        -   /sap/bw/ina/GetServerInfo

        -   /sap/bw/ina/ValueHelp

        -   /sap/bw/ina/BatchProcessing

        -   /sap/bw/ina/Logoff


    -   /sap/bw4


2.  In SAP BW∕4HANA, activate OData service ESH\_SEARCH\_SRV in *Customizing* \(transaction SPRO\) under *SAP NetWeaver* \> *Gateway* \> *OData Channel* \> *Administration* \> *General Settings* \> *Activate and Maintain Services*.
3.  Install and configure Cloud Connector. For more information, see [Configure Cloud Connector](configure-cloud-connector-f289920.md).

4.  In the side navigation area of SAP Datasphere, click *System* \> *Administration* \> *Data Source Configuration* \> *Live Data Sources* and switch on *Allow live data to leave my network*.

    > ### Note:  
    > If your SAP Datasphere tenant was provisioned prior to version 2021.03, click <span class="FPA-icons-V3"></span> \(Product Switch\) ** \> ** <span class="FPA-icons-V3"></span> *Analytics*** \> ** *System* \> *Administration* \> *Data Source Configuration* \> *Live Data Sources*.

    For more information, [Set Up Cloud Connector in SAP Datasphere](set-up-cloud-connector-in-sap-datasphere-6de74f7.md).

5.  In the side navigation area of SAP Datasphere, click *System* \> *Administration* \> *Data Source Configuration* \> *On-premise data sources* and add the location ID of your Cloud Connector instance.

    > ### Note:  
    > If your SAP Datasphere tenant was provisioned prior to version 2021.03, click <span class="FPA-icons-V3"></span> \(Product Switch\) ** \> ** <span class="FPA-icons-V3"></span> *Analytics*** \> ** *System* \> *Administration* \> *Data Source Configuration* \> *On-premise data sources*.

    For more information, [Set Up Cloud Connector in SAP Datasphere](set-up-cloud-connector-in-sap-datasphere-6de74f7.md).

6.  In the side navigation area of SAP Datasphere, open *System* \> *Configuration* \> *Data Integration* \> *Live Data Connections \(Tunnel\)* and create a live data connection of type tunnel to SAP BW∕4HANA.

    > ### Note:  
    > If your SAP Datasphere tenant was provisioned prior to version 2021.03, click <span class="FPA-icons-V3"></span> \(Product Switch\) ** \> ** <span class="FPA-icons-V3"></span> *Analytics*** \> ** <span class="FPA-icons-V3"></span> \(Connections\).

    For more information, see [Create Live Data Connection of Type Tunnel](create-live-data-connection-of-type-tunnel-5d02f11.md).

7.  Install and configure a Data Provisioning Agent and register the SAP HANA adapter with SAP Datasphere:

    -   Install the latest Data Provisioning Agent version on a local host or update your agent to the latest version. For more information, see [Install the Data Provisioning Agent](install-the-data-provisioning-agent-8f61850.md).

    -   In SAP Datasphere, add the external IPv4 address of the server on which your Data Provisioning Agent is running, or in case you are using a network firewall add the public proxy IP address to the IP allowlist. For more information, see [Manage IP Allowlist](manage-ip-allowlist-a3c2145.md).

    -   Connect the Data Provisioning Agent to SAP Datasphere. For more information, see [Connect and Configure the Data Provisioning Agent](connect-and-configure-the-data-provisioning-agent-e87952d.md).

    -   In SAP Datasphere, register the SAP HANA adapter with SAP Datasphere. For more information, see [Register Adapters with SAP Datasphere](register-adapters-with-sap-datasphere-085fc49.md).



**Related Information**  


[SAP BW∕4HANA Model Transfer Connections](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/1caba954bc604e00bf8e82e383a46368.html "Use an SAP BW/4HANA Model Transfer connection to import analytic queries from SAP BW∕4HANA with their Composite Providers and InfoObjects.") :arrow_upper_right:

