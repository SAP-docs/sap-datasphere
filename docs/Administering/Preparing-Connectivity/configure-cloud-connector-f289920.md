<!-- loiof289920243a34127b0c8b13012a1a4b5 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Configure Cloud Connector

Configure Cloud Connector before connecting to on-premise sources and using them in various use cases. In the Cloud Connector administration, connect the SAP Datasphere subaccount to your Cloud Connector, add a mapping to each relevant source system in your network, and specify accessible resources for each source system. 



<a name="loiof289920243a34127b0c8b13012a1a4b5__prereq_jpb_mg5_gmb"/>

## Prerequisites

Before configuring the Cloud Connector, the following prerequisites must be fulfilled:

-   The Cloud Connector is installed in your on-premise network.

    For more information, see [Cloud Connector Installation](https://help.sap.com/viewer/cca91383641e40ffbe03bdc78f00f681/Cloud/en-US/57ae3d62f63440f7952e57bfcef948d3.html) in the *SAP BTP Connectivity* documentation.

-   If you are using egress firewalling, add the following domains \(wildcard\) to the firewall/proxy allowlist in your on-premise network:

    -   `*.hanacloud.ondemand.com`

    -   `*.k8s-hana.ondemand.com`


-   Before configuring the Cloud Connector, you or the owner of your organization will need an SAP Business Technology Platform \(SAP BTP\) account. If you don't have an account yet, create an account by clicking *Register* in the [SAP BTP cockpit](https://account.hana.ondemand.com/).

-   During Cloud Connector configuration you will need information for your SAP Datasphere subaccount. Make sure that you have the subaccount information available in *System* \> *Administration* \> *Data Source Configuration* \> *SAP BTP Core Account*.

    For more information, see [Set Up Cloud Connector in SAP Datasphere](set-up-cloud-connector-in-sap-datasphere-6de74f7.md).

    > ### Note:  
    > If you have an account but cannot see the account information here, enter the SAP BTP user ID. This ID is typically the email address you used to create your SAP BTP account. After you have entered the ID, you can see the *Account Information* for SAP Datasphere.




<a name="loiof289920243a34127b0c8b13012a1a4b5__context_gvs_rkm_2xb"/>

## Context

For more information about the supported use cases depending on the connection type, see [Preparing Cloud Connector Connectivity](preparing-cloud-connector-connectivity-35141e7.md).



## Procedure

1.  Log on to the *Cloud Connector Administration* on <code>https://<i class="varname">&lt;hostname&gt;</i>:8443</code>.

    *<hostname\>* refers to the machine on which the Cloud Connector is installed. If installed on your machine, you can simply enter localhost.

2.  To connect the SAP Datasphere subaccount to your Cloud Connector, perform the following steps:

    1.  In the side navigation area of the *Cloud Connector Administration*, click *Connector* to open the *Connector* page and click :heavy_plus_sign: *Add Subaccount* to open the *Add Subaccount* dialog.

    2.  Enter or select the following information to add the SAP Datasphere subaccount to the Cloud Connector.

        > ### Note:  
        > You can find the subaccount, region, and subaccount user information in SAP Datasphere under *System* \> *Administration* \> *Data Source Configuration* \> *SAP BTP Core Account* \> *Account Information*.


        <table>
        <tr>
        <th valign="top">

        *Property*
        
        </th>
        <th valign="top">

        *Description*
        
        </th>
        </tr>
        <tr>
        <td valign="top">
        
        *Region*
        
        </td>
        <td valign="top">
        
        Select your region host from the list.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *Subaccount*
        
        </td>
        <td valign="top">
        
        Add your SAP Datasphere subaccount name.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *Display Name*
        
        </td>
        <td valign="top">
        
        \[optional\] Add a name for the account.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *Subaccount User*
        
        </td>
        <td valign="top">
        
        Add your subaccount \(S-User\) username.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *Password*
        
        </td>
        <td valign="top">
        
        Add your S-User password for the SAP Business Technology Platform.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *Location ID*
        
        </td>
        <td valign="top">
        
        \[optional\] Define a location ID that identifies the location of this Cloud Connector for the subaccount.

        > ### Note:  
        > -   Using location IDs you can connect multiple Cloud Connector instances to your subaccount. If you don't specify any value, the default is used. For more information, see [Managing Subaccounts](https://help.sap.com/viewer/cca91383641e40ffbe03bdc78f00f681/Cloud/en-US/f16df12fab9f4fe1b8a4122f0fd54b6e.html) in the *SAP BTP Connectivity* documentation.
        > 
        > -   Each Cloud Connector instance must use a different location, and an error will appear if you choose a location that is already been used.
        > 
        > -   We recommend that you leave the *Location ID* empty if you don't plan to set up multiple Cloud Connectors in your system landscape.


        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *Description*
        
        </td>
        <td valign="top">
        
        \(Optional\) Add a description for the Cloud Connector.
        
        </td>
        </tr>
        </table>
        
    3.  Click *Save*.

        In the *Subaccount Dashboard* section of the *Connector* page, you can see all subaccounts added to the Cloud Connector at a glance. After you added your subaccount, you can check the status to verify that the Cloud Connector is connected to the subaccount.


3.  To allow SAP Datasphere to access systems \(on-premise\) in your network, you must specify the systems and the accessible resources in the Cloud Connector \(URL paths or function module names depending on the used protocol\). Perform the following steps for each system that you want to be made available by the Cloud Connector:

    1.  In the side navigation area, under your subaccount menu, click *Cloud To On-Premise* and then :heavy_plus_sign:in the *Mapping Virtual To Internal System* section of the *Access Control* tab to open the *Add System Mapping* dialog.

        > ### Note:  
        > The side navigation area shows the display name of your subaccount. If the area shows another subaccount, select your subaccount from the *Subaccount* field of the *Cloud Connector Administration*.

    2.  Add your system mapping information to configure access control and save your configuration.

        The procedure to add your system mapping information is specific to the protocol that you are using for communication \(see [Configure Access Control](https://help.sap.com/docs/connectivity/sap-btp-connectivity-cf/configure-access-control) in the *SAP BTP Connectivity* documentation\).

        **SAP Datasphere Connections**


        <table>
        <tr>
        <th valign="top">

        Connection Type \(Feature used with the Connection\)
        
        </th>
        <th valign="top">

        Protocol
        
        </th>
        </tr>
        <tr>
        <td valign="top">
        
        *Apache Kafka* on-premise \(replication flows\)
        
        </td>
        <td valign="top">
        
        TCP
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *Confluent* - Confluent Platform on-premise - for the Kafka broker \(replication flows\)
        
        </td>
        <td valign="top">
        
        TCP
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *Confluent* - Confluent Platform on-premise - for the Schema Registry \(replication flows\)
        
        </td>
        <td valign="top">
        
        HTTPS
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *Generic OData* \(data flows\)
        
        </td>
        <td valign="top">
        
        HTTPS
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *Generic SFTP* \(data flows, replication flows\) 
        
        </td>
        <td valign="top">
        
        TCP
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *Microsoft SQL Server* \(data flows, replication flows\) 
        
        </td>
        <td valign="top">
        
        TCP
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *Oracle* \(data flows\)
        
        </td>
        <td valign="top">
        
        TCP
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *SAP ABAP* on-premise \(data flows, replication flows\)
        
        </td>
        <td valign="top">
        
        RFC
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *SAP ABAP* on-premise \(remote tables via ABAP SQL service\)
        
        </td>
        <td valign="top">
        
        HTTPS
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *SAP BW* \(data flows\)
        
        </td>
        <td valign="top">
        
        RFC
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *SAP BW/4HANA Model Transfer* - live data tunnel connection \(model import\)
        
        </td>
        <td valign="top">
        
        HTTPS
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *SAP ECC* \(data flows\)
        
        </td>
        <td valign="top">
        
        RFC
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *SAP HANA* on-premise \(data flows, replication flows, remote tables via SAP HANA Smart Data Access and Cloud Connector\)
        
        </td>
        <td valign="top">
        
        TCP

        For information about how to enable encrypted communication, see the *Security* properties in [Configuring Connection Properties (SAP HANA on-premise)](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/e6b63f176d3640609adcf06297fb37e9.html#loio77cec6a1e8d04371a791658e641dc0d5 "") :arrow_upper_right:.
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *SAP S/4HANA On-Premise* \(data flows, replication flows, model import\)
        
        </td>
        <td valign="top">
        
        RFC
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *SAP S/4HANA On-Premise* \(remote tables via ABAP SQL service\)
        
        </td>
        <td valign="top">
        
        HTTPS
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *SAP S/4HANA On-Premise* - live data tunnel connection \(model import\)
        
        </td>
        <td valign="top">
        
        HTTPS
        
        </td>
        </tr>
        </table>
        
        > ### Note:  
        > -   When adding the system mapping information, you enter internal and virtual system information. The internal host and port specify the actual host and port under which the backend system can be reached within the intranet. It must be an existing network address that can be resolved on the intranet and has network visibility for the Cloud Connector. The Cloud Connector tries to forward the request to the network address specified by the internal host and port, so this address needs to be real. The virtual host name and port represent the fully qualified domain name of the related system in the cloud.
        > 
        >     We recommend to use a virtual \(cloud-side\) name that is different from the internal name.
        > 
        > -   For ABAP-based connection types: When using load balancing, make sure to directly specify the message server port in the *System ID* field of the system mapping information.
        > -   For ABAP-based connection types: The *Connection Type* selected in the system mapping information \(load balancing logon or connecting to a specific application server\) must match the *SAP Logon Connection Type* selected in SAP Datasphere connection management \(*Message Server* or *Application Server*\).
        > -   If encrypted communication using TLS/SSL is defined in the SAP Datasphere connection \(to establish end-to-end encryption\), ensure that the associated system mapping in the Cloud Connector does not use TLS.
        > -   For *SAP S/4HANA On-Premise* connections using the ABAP SQL service for data federation with remote tables:
        >     -   Using the model import feature is not supported with the same connection.
        >     -   If you want to use the same connection for remote tables and flows, you need to create two system mappings. For more information about what to consider when creating the required system mappings, see [Using ABAP SQL Services for Accessing Data from SAP S/4HANA](using-abap-sql-services-for-accessing-data-from-sap-s-4hana-4d74745.md).
        > 
        > -   For *SAP ABAP* \(on-premise\) connections using the ABAP SQL service for data federation with remote tables: If you want to use the same connection for remote tables and flows, you need to create two system mappings. For more information about what to consider when creating the required system mappings, see [Using ABAP SQL Services for Accessing Data from SAP S/4HANA](using-abap-sql-services-for-accessing-data-from-sap-s-4hana-4d74745.md).

        **Catalog Remote Systems**


        <table>
        <tr>
        <th valign="top">

        Remote System Type
        
        </th>
        <th valign="top">

        Protocol
        
        </th>
        </tr>
        <tr>
        <td valign="top">
        
        **SAP BW∕4HANA**
        
        </td>
        <td valign="top">
        
        HTTPS
        
        </td>
        </tr>
        </table>
        
    3.  To grant access only to the resources needed by SAP Datasphere, select the system host you just added from the *Mapping Virtual To Internal System* list, and for each resource that you want to allow to be invoked on that host, click :heavy_plus_sign: in the *Resources Of *<virtual host\>** section to open the *Add Resource* dialog.

    4.  Depending on the connection type, protocol, and use case, add the required resources \(see [Configure Access Control \(HTTP\)](https://help.sap.com/viewer/cca91383641e40ffbe03bdc78f00f681/Cloud/en-US/e7d4927dbb571014af7ef6ebd6cc3511.html) and [Configure Access Control \(RFC\)](https://help.sap.com/viewer/cca91383641e40ffbe03bdc78f00f681/Cloud/en-US/ca5868997e48468395cf0ca4882f5783.html) in the *SAP BTP Connectivity* documentation\).

        **SAP Datasphere Connections**


        <table>
        <tr>
        <th valign="top">

        Connection Type \(Protocol\)
        
        </th>
        <th valign="top">

        Accessible Resources Based on Use Case
        
        </th>
        </tr>
        <tr>
        <td valign="top">
        
        *SAP BW/4HANA Model Import* \(HTTPS\)
        
        </td>
        <td valign="top">
        
        For model import, limit the accessible services for the live data tunnel connection used with the *SAP BW/4HANA Model Import* connection to the following URL paths:

        -   `/sap/opu/odata/sap/ESH_SEARCH_SRV/SearchQueries`

        -   `/sap/bw4/v1/dwc/dbinfo`

        -   `/sap/bw4/v1/dwc/metadata/queryviews` – *Path and all sub-paths*

        -   `/sap/bw4/v1/dwc/metadata/treestructure` – *Path and all sub-paths*

        -   `/sap/bw/ina` – *Path and all sub-paths*



        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *SAP S/4HANA On-Premise* \(HTTPS\)
        
        </td>
        <td valign="top">
        
        For model import, limit the accessible services for the live data tunnel connection used with the *SAP S/4HANA On-Premise* connection to the following URL path:

        -   `/`


        For data federation with remote tables via the ABAP SQL service, limit the accessible services as follows:

        -   Enter the service path of the SQL service endpoint on the SAP S/4HANA system. For example: `/sap/bc/sql/sql1/sap/s_privileged` – *Path and all sub-paths*
        -   Select the *Upgrade Allowed* option in the *Add Resources* dialog.

            > ### Note:  
            > In older Cloud Connector versions, the option might appear as *WebSocket* or *WebSocket Upgrade*.



        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *SAP ABAP* , *SAP S/4HANA On-Premise* \(RFC\)
        
        </td>
        <td valign="top">
        
        If you are connecting to an SAP S/4HANA system without DMIS add-on installed, limit the accessible resources to the following function modules:

        -   DHAMB\_ – *Prefix*

        -   DHAPE\_ – *Prefix*

        -   RFC\_FUNCTION\_SEARCH


        If you are connecting to an ABAP-based system with DMIS add-on installed, limit the accessible resources to the following function modules:

        -   LTAMB\_ – *Prefix*

        -   LTAPE\_ – *Prefix*

        -   RFC\_FUNCTION\_SEARCH


        For more information, see SAP Note [2835207](https://me.sap.com/notes/2835207).
        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *SAP BW*, *SAP ECC* \(RFC\)
        
        </td>
        <td valign="top">
        
        For accessing data using ODP connectivity \(for legacy systems that do not have the ABAP Pipeline Engine extension or DMIS Addon installed\), limit the accessible resources to the following function modules:

        -   /SAPDS/ – *Prefix*

        -   RFC\_FUNCTION\_SEARCH

        -   RODPS\_REPL\_ – *Prefix*



        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *SAP Datasphere, SAP BW bridge* \(RFC\)
        
        </td>
        <td valign="top">
        
        For information about configuring Cloud Connector to connect to ODP source systems to SAP Datasphere, SAP BW bridge and limiting the accessible resources, see:

        -   [Preparing Connectivity for ODP Source Systems in SAP BW Bridge](https://help.sap.com/viewer/e2d2b48377c14490b55466b5f1872640/DEV_CURRENT/en-US/18d69431efb34a71b1939eb5a071db08.html "") :arrow_upper_right:
        -   [Add Resources to Source System](https://help.sap.com/viewer/e2d2b48377c14490b55466b5f1872640/DEV_CURRENT/en-US/2505f3efb2744a829a811985cb2b62c3.html "You need to add some additional ressources to your source system.") :arrow_upper_right:


        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
        *Confluent* \(HTTPS\)
        
        </td>
        <td valign="top">
        
        If you are connecting to Confluent Platform \(on-premise\), limit the accessible resources for the Schema Registry to the following URL path:

        `/`
        
        </td>
        </tr>
        </table>
        
        **Catalog Remote Systems**


        <table>
        <tr>
        <th valign="top">

        Remote System Type \(Protocol\)
        
        </th>
        <th valign="top">

        Resources
        
        </th>
        </tr>
        <tr>
        <td valign="top">
        
        SAP BW∕4HANA \(HTTPS\)
        
        </td>
        <td valign="top">
        
        For metadata extraction, limit the accessible services to the following URL paths:

        -   `/sap/bc/http/sap/bw4/v1/system/information`
        -   `/sap/opu/odata4/sap/rv_i_dwc_area_tree_sb/` - *Path and all sub-paths*
        -   `/sap/opu/odata4/sap/rv_c_dwc_obj_header/` - *Path and all sub-paths*
        -   `/sap/opu/odata4/sap/rv_i_dwc_details_sb/` - *Path and all sub-paths*


        
        </td>
        </tr>
        </table>
        
    5.  Choose *Save*.


4.  \[optional\] If you want to enable secure network communication \(SNC\) to an ABAP-based on-premise system, which you want to connect to for using data flows or replication flows, configure SNC in the Cloud Connector and consider the SNC-specific settings when adding the system mapping information:

    -   In the *Back-end Type* field, select *ABAP System*.
    -   In the *Protocol* field, select *RFC SNC*.
    -   In the *Principal Type* field, select *X.509 Certificate*.
    -   In the *SNC Partner Name* field, enter the ABAP system's SNC identity name \(for example, `p:CN=SID, O=Trust Community, C=DE`\). The SNC partner name needs to contain the correct SNC identification of the ABAP system. The value can typically be found in the ABAP system instance profile parameter `snc/identity/as` \(and hence is provided per application server\).

    For more information about configuring SNC, see [Initial Configuration \(RFC\)](https://help.sap.com/viewer/DRAFT/cca91383641e40ffbe03bdc78f00f681/Validation/en-US/f09eefe71d1e4d4484e1dd4b121585fb.html) in the *SAP BTP Connectivity* documentation.




<a name="loiof289920243a34127b0c8b13012a1a4b5__postreq_u1v_lvd_hpb"/>

## Next Steps

1.  If you have defined a location ID in the Cloud Connector configuration and want to use it when creating connections, you need to add the location ID in <span class="FPA-icons-V3"></span> \(*System*\) ** \> ** <span class="Belize-icons"></span> \(*Administration*\) ** \> *Data Source Configuration*.

    For more information, see [Set Up Cloud Connector in SAP Datasphere](set-up-cloud-connector-in-sap-datasphere-6de74f7.md).

2.  If you want to create SAP BW/4HANA Model Transfer connections or SAP S/4HANA On-Premise connections for model import, you need to switch on *Allow live data to securely leave my network* in <span class="FPA-icons-V3"></span> \(*System*\) ** \> ** <span class="Belize-icons"></span> \(*Administration*\) ** \> *Data Source Configuration*

    For more information, see [Set Up Cloud Connector in SAP Datasphere](set-up-cloud-connector-in-sap-datasphere-6de74f7.md).


You can now create your connections in the SAP Datasphere *Connections* app or in the <span class="SAP-icons-V5"></span>\(*Catalog & Marketplace*\) ** \> ** :desktop_computer: \(*Metadata Extractions*\) app.

For answers to the most common questions about the Cloud Connector, see [Frequently Asked Questions](https://help.sap.com/docs/CP_CONNECTIVITY/cca91383641e40ffbe03bdc78f00f681/f8d6f9ab43c14e52a9e8036515a472e9.html) in the *SAP BTP Connectivity* documentation.

  


