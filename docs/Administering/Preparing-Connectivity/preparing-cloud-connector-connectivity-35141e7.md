<!-- loio35141e7668774958b5e59495f7a7828e -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Preparing Cloud Connector Connectivity

Connections to on-premise sources used for data flows, replication flows, and other use cases require Cloud Connector to act as link between SAP Datasphere and the source. Before creating the connection, the Cloud Connector requires an appropriate setup.



<a name="loio35141e7668774958b5e59495f7a7828e__section_iyq_hvz_4tb"/>

## Context

Cloud Connector serves as a link between SAP Datasphere and your on-premise sources and is required for connections that you want to use for:

-   Data flows

-   Replication flows

-   Model import from:

    -   SAP BW/4HANA Model Transfer connections \(Cloud Connector is required for the live data connection of type tunnel that you need to create the model import connection\)

    -   SAP S/4HANA On-Premise connections \(Cloud Connector is required for the live data connection of type tunnel that you need to search for the entities in the SAP S/4HANA system\)


-   Remote tables \(only for SAP HANA on-premise via SAP HANA Smart Data Access\)


For an overview of connection types that require a Cloud Connector setup to be able to use any of these features, see [Preparing Connectivity for Connections](preparing-connectivity-for-connections-bffbd58.md).



<a name="loio35141e7668774958b5e59495f7a7828e__section_j3m_4vz_4tb"/>

## Procedure

To prepare connectivity via Cloud Connector, perform the following steps:

1.  Install the Cloud Connector in your on-premise network.

    For more information, see [Cloud Connector Installation](https://help.sap.com/viewer/cca91383641e40ffbe03bdc78f00f681/Cloud/en-US/57ae3d62f63440f7952e57bfcef948d3.html) in the *SAP BTP Connectivity* documentation.

2.  Make sure to hold the SAP Datasphere subaccount information ready. You can find the information in <span class="FPA-icons-V3"></span> \(*System*\) ** \> ** <span class="Belize-icons"></span> \(*Administration*\) ** \> *Data Source Configuration*.

    For more information, see [Set Up Cloud Connector in SAP Datasphere](set-up-cloud-connector-in-sap-datasphere-6de74f7.md).

3.  In the Cloud Connector administration, set up and configure Cloud Connector according to your requirements.

    For more information, see [Configure Cloud Connector](configure-cloud-connector-f289920.md).

4.  If you have connected multiple Cloud Connector instances to your subaccount and you want to use these locations for your connections, add the location IDs in <span class="FPA-icons-V3"></span> \(*System*\) ** \> ** <span class="Belize-icons"></span> \(*Administration*\) ** \> *Data Source Configuration*.

    For more information, see [Set Up Cloud Connector in SAP Datasphere](set-up-cloud-connector-in-sap-datasphere-6de74f7.md).

5.  If you you want to create SAP BW/4HANA Model Transfer connections or SAP S/4HANA On-Premise connections for model import, make sure you have switched on *Allow live data to securely leave my network* in <span class="FPA-icons-V3"></span> \(*System*\) ** \> ** <span class="Belize-icons"></span> \(*Administration*\) ** \> *Data Source Configuration*.

    For more information, see [Set Up Cloud Connector in SAP Datasphere](set-up-cloud-connector-in-sap-datasphere-6de74f7.md).




<a name="loio35141e7668774958b5e59495f7a7828e__section_stc_svz_4tb"/>

## Result

The Cloud Connector respectively Cloud Connector instances are available for creating connections and enabling these for the supported features.



<a name="loio35141e7668774958b5e59495f7a7828e__section_vpb_spb_s5b"/>

## Related Links

[Frequently Asked Questions \(about the Cloud Connector\)](https://help.sap.com/docs/CP_CONNECTIVITY/cca91383641e40ffbe03bdc78f00f681/f8d6f9ab43c14e52a9e8036515a472e9.html) in the *SAP BTP Connectivity* documentation

