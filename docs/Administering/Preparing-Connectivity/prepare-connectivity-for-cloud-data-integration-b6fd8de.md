<!-- loiob6fd8def1c00408e9c5e34efb897aa31 -->

# Prepare Connectivity for Cloud Data Integration

To be able to successfully validate and use a Cloud Data Integration connection for remote tables or data flows certain preparations have to be made.



<a name="loiob6fd8def1c00408e9c5e34efb897aa31__prereq_rt_CDI"/>

## Remote Tables

Before you can use the connection for creating views and accessing data via remote tables, the following is required:

-   An administrator has connected an SAP HANA smart data integration Data Provisioning Agent to SAP Datasphere and registered the CloudDataIntegrationAdapter.

    For more information, see [Preparing Data Provisioning Agent Connectivity](preparing-data-provisioning-agent-connectivity-f1a39d1.md).

-   For ABAP-based cloud SAP systems such as SAP S/4HANA Cloud or SAP Marketing Cloud: A communication arrangement has been created for communication scenario `SAP_COM_0531` in the source system. 

    For more information, see [Integrating CDI](https://help.sap.com/viewer/0f69f8fb28ac4bf48d2b57b9637e81fa/latest/en-US/4a006b43551d4cb5aed6399c0ace6b98.html) in the *SAP S/4HANA Cloud* documentation.




<a name="loiob6fd8def1c00408e9c5e34efb897aa31__prereq_df_CDI"/>

## Data Flows

Before you can use the connection for data flows, the following is required:

-   An administrator has installed and configured Cloud Connector to connect to your on-premise source.

    For more information, see [Configure Cloud Connector](configure-cloud-connector-f289920.md).

-   For ABAP-based cloud SAP systems such as SAP S/4HANA Cloud or SAP Marketing Cloud: A communication arrangement has been created for communication scenario `SAP_COM_0531` in the source system.

    For more information, see [Integrating CDI](https://help.sap.com/viewer/0f69f8fb28ac4bf48d2b57b9637e81fa/latest/en-US/4a006b43551d4cb5aed6399c0ace6b98.html) in the *SAP S/4HANA Cloud* documentation.


