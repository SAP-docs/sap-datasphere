<!-- loiofb1aa1107f40429888a633bf940f4ad4 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Prepare Connectivity to SAP Open Connectors

Integrate SAP Open Connectors with SAP Datasphere to be able to connect to third party data sources powered by SAP Open Connectors. 



<a name="loiofb1aa1107f40429888a633bf940f4ad4__section_pqp_5gn_rpb"/>

## Preparations in SAP BTP and SAP Open Connectors Account

1.  Set up an SAP BTP account and enable the SAP Integration Suite service with the SAP Open Connectors capability.

    > ### Note:  
    > You need to know your SAP BTP subaccount information \(provider, region, environment, trial - yes/no\) later to select the appropriate SAP BTP subaccount region in SAP Datasphere when integrating the SAP Open Connectors account in your space.

    For information about setting up an SAP BTP trial version with the SAP Integration Suite service, see [Set Up Integration Suite Trial](https://developers.sap.com/tutorials/cp-starter-isuite-onboard-subscribe.html). To enable SAP Open Connectors, you need to activate the *Extend Non-SAP Connectivity* capability in the Integration Suite.

    For information about setting up SAP Integration Suite from a production SAP BTP account, see [Initial Setup](https://help.sap.com/viewer/51ab953548be4459bfe8539ecaeee98d/sap.cp.integration.suite/en-US/3dcf507f92f54597bc203600bf8f94c5.html) in the *SAP Integration Suite* documentation.

    For information about SAP Open Connectors availability in data centers, see SAP Note [2903776](https://me.sap.com/notes/2903776).

2.  In your SAP Open Connectors account, create connector instances for the sources that you want to connect to SAP Datasphere.

    For more information about creating an instance, see [Authenticate a Connector Instance \(UI\)](https://help.openconnectors.ext.hana.ondemand.com/home/authenticate-an-element-instance-ui) in the *SAP Open Connectors* documentation.

    For more information about connector-specific setup and connector-specific properties required to create an instance, see [Connectors Catalog](https://help.openconnectors.ext.hana.ondemand.com/home/catalog) in the *SAP Open Connectors* documentation. There, click the connector in question and then *<connector name\> API Provider Setup* or *<connector name\> Authenticate a Connector Instance*.

3.  In your SAP Open Connectors account, record the following information which you will require later in SAP Datasphere:

    -   Organization secret and user secret - required when integrating the SAP Open Connectors account in your space.

    -   Name of the connector instance - required when selecting the instance in the connection creation wizard





<a name="loiofb1aa1107f40429888a633bf940f4ad4__section_vgv_wyq_spb"/>

## Preparations in SAP Datasphere



1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(*Connections*\), select a space if necessary, click the *SAP Open Connectors* tab, and then click *Integrate your SAP Open Connectors Account* to open the *Integrate your SAP Open Connectors Account* dialog.

2.  In the dialog, provide the following data:

    1.  In the *SAP BTP Sub Account Region* field, select the appropriate entry according to your SAP BTP subaccount information \(provider, region, environment, trial - yes/no\).

    2.  Enter your SAP Open Connectors organisation and user secret.


3.  Click *OK* to integrate your SAP Open Connectors account with SAP Datasphere.




## Results

With connection type *Open Connectors* you can now create connections to the third-party data sources available as connector instances with your SAP Open Connectors account.

**Related Information**  


[Open Connectors Connections](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/9bfe7db51216449d985a0b59f5e181c4.html "Use an Open Connectors connection to access data from sources that are connected to the SAP Open Connectors account that is integrated with your space.") :arrow_upper_right:

