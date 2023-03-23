<!-- loioabb159e027184c98a54fc1b2a88dd3f5 -->

# Prepare Connectivity to SAP S/4HANA Cloud

To be able to successfully validate and use a connection to SAP S/4HANA Cloud, certain preparations have to be made.



<a name="loioabb159e027184c98a54fc1b2a88dd3f5__prereq_rt"/>

## Remote Tables

Before you can use the connection for creating views and accessing data via remote tables, the following is required:

-   An administrator has connected an SAP HANA smart data integration Data Provisioning Agent to SAP Datasphere and registered the CloudDataIntegrationAdapter.

    For more information, see [Preparing Data Provisioning Agent Connectivity](preparing-data-provisioning-agent-connectivity-f1a39d1.md).

-   A communication arrangement has been created for communication scenario `SAP_COM_0531` \(*CDI API for CDS Based Extraction*\) in the source system. 

    For more information, see [Integrating CDI](https://help.sap.com/viewer/0f69f8fb28ac4bf48d2b57b9637e81fa/latest/en-US/4a006b43551d4cb5aed6399c0ace6b98.html) in the *SAP S/4HANA Cloud* documentation.




<a name="loioabb159e027184c98a54fc1b2a88dd3f5__prereq_df"/>

## Data Flows and Replication Flows

Before you can use the connection for data flows, the following is required:

-   A communication arrangement has been created for communication scenario `SAP_COM_0532` \(*SAP Data Hub – ABAP CDS Pipeline Integration*\) in the SAP S/4HANA Cloud system.

    For more information, see [Integrating CDS Views Using ABAP CDS Pipeline](https://help.sap.com/viewer/0f69f8fb28ac4bf48d2b57b9637e81fa/latest/en-US/f509eddda867452db9631dae1ae442a3.html) in the *SAP S/4HANA Cloud* documentation.

-   For replication flows, CDS view replication is supported for SAP S/4HANA Cloud version 2202 and higher.




<a name="loioabb159e027184c98a54fc1b2a88dd3f5__prereq_mt"/>

## Model Import

Before you can use the connection for model import, the following is required:

-   A connection to an SAP HANA Smart Data Integration \(SDI\) Data Provisioning Agent with a registered CloudDataIntegrationAdapter.

    For more information, see [Preparing Data Provisioning Agent Connectivity](preparing-data-provisioning-agent-connectivity-f1a39d1.md).

-   In the SAP S/4HANA Cloud system, communication arrangements have been created for the following communication scenarios:

    -   `SAP_COM_0532` \(*SAP Data Hub – ABAP CDS Pipeline Integration*\)

        For more information, see [Integrating CDS Views Using ABAP CDS Pipeline](https://help.sap.com/viewer/0f69f8fb28ac4bf48d2b57b9637e81fa/latest/en-US/f509eddda867452db9631dae1ae442a3.html) in the *SAP S/4HANA Cloud* documentation.

    -   `SAP_COM_0531` \(CDI API for CDS Based Extraction\)

        For more information, see [Integrating CDI](https://help.sap.com/viewer/0f69f8fb28ac4bf48d2b57b9637e81fa/latest/en-US/4a006b43551d4cb5aed6399c0ace6b98.html) in the *SAP S/4HANA Cloud* documentation.

    -   `SAP_COM_0722` 

        For more information, see [Integrating SAP Data Warehouse Cloud](https://help.sap.com/viewer/0f69f8fb28ac4bf48d2b57b9637e81fa/latest/en-US/8b0662cbc94940b98d8bb6f0696ccfa4.html) in the *SAP S/4HANA Cloud* documentation.



