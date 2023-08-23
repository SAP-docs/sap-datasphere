<!-- loio25e2bd7a70d44ac5b05e844f9e913471 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Creating a Replication Flow

Create a replication flow if you want to copy multiple data assets from the same source to the same target in a fast and easy way and do not require complex projections.



## Context

You can use replication flows to copy data from the following source objects:

-   CDS views \(in ABAP-based SAP systems\) that are enabled for extraction

-   Tables that have a unique key \(primary key\)

-   Objects from ODP providers, such as extractors or SAP BW artifacts


For more information about available connection types, sources, and targets, see [Integrating Data via Connections](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/eb85e157ab654152bd68a8714036e463.html "Connections provide access to data from a wide range of sources, cloud as well as on-premise sources, SAP as well as Non-SAP sources, and partner tools. They allow space members to use objects from the connected source to acquire, prepare and access data from those sources in SAP Datasphere. To connect to different sources, SAP Datasphere provides different connection types.") :arrow_upper_right:.

> ### Note:  
> Replication flows may not be available in SAP Datasphere tenants provisioned prior to version 2021.03. To request the migration of your tenant, see SAP note [3268282](https://launchpad.support.sap.com/#/notes/3268282).



<a name="loio25e2bd7a70d44ac5b05e844f9e913471__steps_qxh_dqv_fvb"/>

## Procedure

1.  In the side navigation area, click ![](../Creating-Finding-Sharing-Objects/images/Data_Builder_f73dc45.png) \(*Data Builder*\), select a space if necessary, and click *New Replication Flow* to open the editor.

2.  Select a source connection and a source container, then add source objects \(see [Add a Source](add-a-source-7496380.md)\).

    The *Details* side panel shows the properties of your replication flow. If you select an object in the canvas, the side panel changes to show the properties of the selected object.

3.  Select a target connection and target container \(see [Add a Target](add-a-target-ab490fb.md)\).

4.  Review the default settings for *Load Type* and *Truncate* and change them if necessary \(see [Configure Your Replication Flow](configure-your-replication-flow-3f5ba0c.md)\).

5.  Define filters and mapping as required for your use case:

    -   Define filters to delimit the scope of your replication flow \(see [Define Filters](define-filters-5a6ef36.md)\).

    -   Define mappings to specify where you want the data from the source to go in the target \(see [Define Mapping](define-mapping-2c7948f.md)\).


6.  Click <span class="FPA-icons"></span> \(Save\). A dialog box appears. Enter a business name and a technical name for your replication flow.

    When you enter a business name, the system automatically suggests a corresponding technical name, but you can change the technical name if required. Both names must be unique within the space you work in.

7.  Click <span class="SAP-icons"></span> \(Deploy\) to make your replication flow ready to run.

    When you deploy your replication flow, it gets saved in the shared repository and is available for other users to view, import, or modify.

    When deploying your replication flow, the system does a series of validation checks and outputs an error message if it finds an issue in the flow configuration.

8.  Click <span class="FPA-icons"></span> \(Run\) to start your replication flow.

    For more information about how to monitor your replication flow run, see [Monitoring Flows](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/b661ea0766a24c7d839df950330a89fd.html "In the Flow Monitor, you can find all the deployed flows per space.") :arrow_upper_right:.


