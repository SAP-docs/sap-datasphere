<!-- loioabb159e027184c98a54fc1b2a88dd3f5 -->

# Prepare Connectivity to SAP S/4HANA Cloud

To be able to successfully validate and use a connection to SAP S/4HANA Cloud, certain preparations have to be made.



<a name="loioabb159e027184c98a54fc1b2a88dd3f5__prereq_rt"/>

## Remote Tables

Before you can use the connection for creating views and accessing data via remote tables, the following is required:

-   An administrator has connected an SAP HANA smart data integration Data Provisioning Agent to SAP Datasphere and registered the CloudDataIntegrationAdapter.

    For more information, see [Preparing Data Provisioning Agent Connectivity](preparing-data-provisioning-agent-connectivity-f1a39d1.md).

-   A communication arrangement has been created for communication scenario `SAP_COM_0531` in the source system. 

    For more information, see [Integrating CDI](https://help.sap.com/viewer/0f69f8fb28ac4bf48d2b57b9637e81fa/latest/en-US/4a006b43551d4cb5aed6399c0ace6b98.html) in the *SAP S/4HANA Cloud* documentation.




<a name="loioabb159e027184c98a54fc1b2a88dd3f5__prereq_df"/>

## Data Flows

Before you can use the connection for data flows, the following is required:

-   If you want to replicate CDS views:

    A communication arrangement has been created for communication scenario `SAP_COM_0532` in the SAP S/4HANA Cloud system.

    For more information, see [Integrating CDS Views Using SAP Datasphere](https://help.sap.com/viewer/0f69f8fb28ac4bf48d2b57b9637e81fa/latest/en-US/f509eddda867452db9631dae1ae442a3.html) in the *SAP S/4HANA Cloud* documentation.




<a name="loioabb159e027184c98a54fc1b2a88dd3f5__section_ijd_xmz_y1c"/>

## Replication Flows

Before you can use the connection for replication flows, the following is required:

-   If you want to replicate CDS views:

    A communication arrangement has been created for communication scenario `SAP_COM_0532` in the SAP S/4HANA Cloud system.

    For more information, see [Integrating CDS Views Using SAP Datasphere](https://help.sap.com/viewer/0f69f8fb28ac4bf48d2b57b9637e81fa/latest/en-US/f509eddda867452db9631dae1ae442a3.html) in the *SAP S/4HANA Cloud* documentation.

-   If you want to replicate CDS view entities using the SQL service exposure from SAP S/4HANA Cloud:

    In SAP S/4HANA Cloud, your system administration has created the relevant communication arrangements:

    -   Communication arrangements for exposing SQL services \(see [Exposing the SQL Service for Data Federation and Replication with Privileged Access](https://help.sap.com/docs/SAP_S4HANA_CLOUD/6aa39f1ac05441e5a23f484f31e477e7/70b2fc2a9e37475b993d4e6fd6d3eb07.html) in the *SAP S/4HANA Cloud* documentation\)

    -   A communication arrangement for communication scenario `SAP_COM_0532` \(see [Integrating SQL Services Using SAP Datasphere](https://help.sap.com/docs/SAP_S4HANA_CLOUD/0f69f8fb28ac4bf48d2b57b9637e81fa/a91d39c3ea494344897fca7bc9578b85.html) in the *SAP S/4HANA Cloud* documentation\)


    > ### Note:  
    > Note that the same communication user must be added to all communication arrangements.

    For more information about using SQL services to replicate ABAP-managed data to SAP Datasphere, see [Data Consumption Using SAP Datasphere](https://help.sap.com/docs/SAP_S4HANA_CLOUD/6aa39f1ac05441e5a23f484f31e477e7/ec312dd3e39f401b84681c53adc08ad8.html) in the *SAP S/4HANA Cloud* documentation.




<a name="loioabb159e027184c98a54fc1b2a88dd3f5__prereq_mt"/>

## Model Import

Before you can use the connection for model import, the following is required:

-   A connection to an SAP HANA Smart Data Integration \(SDI\) Data Provisioning Agent with a registered CloudDataIntegrationAdapter.

    For more information, see [Preparing Data Provisioning Agent Connectivity](preparing-data-provisioning-agent-connectivity-f1a39d1.md).

-   In the SAP S/4HANA Cloud system, communication arrangements have been created for the following communication scenarios:

    -   `SAP_COM_0532` 

        For more information, see [Integrating CDS Views Using SAP Datasphere](https://help.sap.com/viewer/0f69f8fb28ac4bf48d2b57b9637e81fa/latest/en-US/f509eddda867452db9631dae1ae442a3.html) in the *SAP S/4HANA Cloud* documentation.

    -   `SAP_COM_0531`

        For more information, see [Integrating CDI](https://help.sap.com/viewer/0f69f8fb28ac4bf48d2b57b9637e81fa/latest/en-US/4a006b43551d4cb5aed6399c0ace6b98.html) in the *SAP S/4HANA Cloud* documentation.

    -   `SAP_COM_0722` 

        For more information, see [Integrating SAP Data Warehouse Cloud](https://help.sap.com/viewer/0f69f8fb28ac4bf48d2b57b9637e81fa/latest/en-US/8b0662cbc94940b98d8bb6f0696ccfa4.html) in the *SAP S/4HANA Cloud* documentation.



**Related Information**  


[SAP S/4HANA Cloud Connections](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/a98e5ffdf47c44d9a845dca01a18bd82.html "Use an SAP S/4HANA Cloud connection to access or import extraction-enabled ABAP Core Data Services views (ABAP CDS views) from SAP S/4HANA Cloud.") :arrow_upper_right:

