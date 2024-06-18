<!-- loiof5e0c06fdc834c62a10eeb19d9a79bab -->

# Prepare Connectivity to SAP Marketing Cloud

To be able to successfully validate and use a connection to SAP Marketing Cloud for remote tables or data flows, certain preparations have to be made.



<a name="loiof5e0c06fdc834c62a10eeb19d9a79bab__prereq_rt_Marketing_Cloud"/>

## Remote Tables

Before you can use the connection for creating views and accessing data via remote tables, the following is required:

-   An administrator has connected an SAP HANA smart data integration Data Provisioning Agent to SAP Datasphere and registered the CloudDataIntegrationAdapter.

    For more information, see [Preparing Data Provisioning Agent Connectivity](preparing-data-provisioning-agent-connectivity-f1a39d1.md).

-   A communication arrangement has been created for communication scenario `SAP_COM_0531` in the source system. 

    For more information, see [Integrating CDI](https://help.sap.com/viewer/e0cd7c1ecf3d4f2f9feb46ec1c5b68fb/latest/en-US/4a006b43551d4cb5aed6399c0ace6b98.html) in the *SAP Marketing Cloud* documentation.




<a name="loiof5e0c06fdc834c62a10eeb19d9a79bab__prereq_df_Marketing_Cloud"/>

## Data Flows

Before you can use the connection for data flows, the following is required:

-   A communication arrangement has been created for communication scenario `SAP_COM_0531` in the source system. 

    For more information, see [Integrating CDI](https://help.sap.com/viewer/e0cd7c1ecf3d4f2f9feb46ec1c5b68fb/latest/en-US/4a006b43551d4cb5aed6399c0ace6b98.html) in the *SAP Marketing Cloud* documentation.


**Related Information**  


[SAP Marketing Cloud Connections](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/4de4959620c24d12a53a3cc357d3e003.html "Use an SAP Marketing Cloud connection to access data from SAP Marketing Cloud via its OData-based APIs for data integration and SAP HANA Smart Data Integration.") :arrow_upper_right:

