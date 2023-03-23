<!-- loio6de74f7731c54ce88f2883df8f8671a8 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Set Up Cloud Connector in SAP Datasphere

Receive SAP Datasphere subaccount information required for Cloud Connector configuration and complete Cloud Connector setup for creating SAP BW/4HANA Model Transfer connections and for using multiple Cloud Connector instances.



<a name="loio6de74f7731c54ce88f2883df8f8671a8__section_ky2_cgv_tsb"/>

## Context

The Cloud Connector allows you to connect to on-premise data sources and use them for data flows, replication flows, model import from SAP BW∕4HANA, and remote table access from SAP HANA on-premise \(via SAP HANA Smart Data Access\).



<a name="loio6de74f7731c54ce88f2883df8f8671a8__section_yzv_cgv_tsb"/>

## Procedure

1.  In the side navigation area, click <span class="FPA-icons"></span> \(*System*\) ** \> ** <span class="Belize-icons"></span> \(*Administration*\) ** \> *Data Source Configuration*.

    > ### Note:  
    > If your tenant was provisioned prior to version 2021.03, click <span class="FPA-icons"></span> \(Product Switch\) ** \> ** <span class="FPA-icons"></span> *Analytics*** \> ** *System* \> *Administration* \> *Data Source Configuration*.

2.  Perform the required tasks:

    -   Receive the SAP Datasphere subaccount information that is required during Cloud Connector configuration.

        To receive the SAP Datasphere subaccount information, the subaccount needs to be linked to the user ID of your SAP BTP account. In the *SAP BTP Core Account* section, you can check if this has been done and the information is already available in *Account Information*.

        During Cloud Connector configuration, you will then need to enter the following information from your SAP Datasphere subaccount:

        -   *Subaccount*

        -   *Region Host*

        -   *Subaccount User*


        If you have an account but cannot see the *Account Information*, enter the SAP BTP user ID. This ID is typically the email address you used to create your SAP BTP account. After you have entered the ID you can see the *Account Information* for SAP Datasphere:

        > ### Note:  
        > If you don't have an SAP Business Technology Platform \(SAP BTP\) user account yet, create an account in the [SAP BTP cockpit](https://account.hana.ondemand.com/) by clicking *Register* in the cockpit.

    -   To be able to use the Cloud Connector for model import from SAP BW/4HANA Model Transfer connections, in the *Live Data Sources* section, switch on *Allow live data to securely leave my network*.

        > ### Note:  
        > The *Allow live data to securely leave my network* switch is audited, so that administrators can see who switched this feature on and off. To see the changes in the switch state, go to <span class="FPA-icons"></span> \(*Security*\) ** \> ** <span class="SAP-icons"></span> \(*Activities*\), and search for ***ALLOW\_LIVE\_DATA\_MOVEMENT***.

    -   If you have connected multiple Cloud Connector instances to your subaccount with different location IDs and you want to offer them for selection when creating connections using a Cloud Connector, in the *On-premise data sources* section, add the appropriate location IDs. If you don't add any location IDs here, the default location will be used.

        Cloud Connector location IDs identify Cloud Connector instances that are deployed in various locations of a customer's premises and connected to the same subaccount. Starting with Cloud Connector 2.9.0, it is possible to connect multiple Cloud Connectors to a subaccount as long as their location ID is different.



