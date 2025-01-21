<!-- loio749638060e8746e48b0f9bf0e50c6d0c -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Add the Source for a Replication Flow

Define the source for your replication flow \(connection, container, and objects\).



<a name="loio749638060e8746e48b0f9bf0e50c6d0c__context_x4r_ghf_vvb"/>

## Context

-   Connections are created by your system administration. You can only use a data source if a connection has been created for it in your space and if you have the necessary authorizations.

-   Containers are the parent objects that hold the data:

    -   For CDS view entities, the container is called SQL\_SERVICE.

    -   For standard CDS views, the container is the CDS root folder \(CDS\_EXTRACTION\).

        If a standard CDS view for which replication is enabled is not shown in the CDS\_EXTRACTION folder, make sure that the user in the source connection has the required authorizations. For connections to an SAP S/4HANA Cloud source system, this might mean that the user must be assigned to an authorization group that contains the CDS view \(as described in [Integrating CDS Views Using ABAP CDS Pipeline](https://help.sap.com/docs/SAP_S4HANA_CLOUD/0f69f8fb28ac4bf48d2b57b9637e81fa/f509eddda867452db9631dae1ae442a3.html?version=2308.503)\).

    -   For database tables, the container is the schema that includes the table.

    -   For SAP Landscape Transformation Replication Server \(SLT\), the container is the relevant mass transfer ID. Make sure that it is available in SLT before you start creating your replication flow.

    -   For cloud storage providers, the container is the folder that contains the relevant dataset folders.


-   You can use the SQL service exposure from SAP BTP, ABAP environment, or SAP S/4HANA Cloud, respectively, to replicate custom and standard CDS view entities if your system administration has created the relevant communication arrangements. For more information, see [Data Consumption using SAP Datasphere](https://help.sap.com/docs/btp/sap-business-technology-platform/data-consumption-using-sap-datasphere). For information about the relevant integration scenario, see [Integrating SQL Services using SAP Datasphere](https://help.sap.com/docs/btp/sap-business-technology-platform/integrating-sql-services-using-sap-datasphere).

-   Replication objects are the datasets that you choose for replication, for example individual CDS view entities or database tables.




## Procedure

1.  Choose *Select Source Connection* at the bottom left of the screen. A list of available source connections appears. Select the relevant one for your use case.

    If you are not sure which one to choose, or if none of the connections in the list is suitable for your purposes, contact your administration.

    Alternatively, you can get started by clicking <span class="FPA-icons-V3"></span> \(Browse source connections\)

2.  Choose *Select Source Container*. A list of available source containers appears. Select the relevant one for your use case.

    To narrow down the selection, start typing a part of the folder name in the *Search* field.

    -   If you choose SAP Datasphere as the source connection, the source container is automatically defined as the space you are in.

    -   If CDS view entities have been made available using the SQL service exposure in SAP BTP, ABAP environment, you find these entities in a folder called SQL\_SERVICE.


3.  Choose *Add Source Objects*. A list of available objects appears. Select the relevant ones for your use case and choose *Next*. A list of the objects you selected appears.

    > ### Note:  
    > -   The list only shows objects for which replication is supported. For example, if you select SAP S/4HANA Cloud as the source and the folder SQL\_SERVICE as the container, you will only be shown CDS view entities that have the required annotations for data extraction.
    > 
    > -   If you use SAP Datasphere as the source connection, your source objects must be local tables that have been deployed and have a primary key.

4.  If you decide that you do not want to include an object after all, select it and choose *Remove from Selection*. If you want to include more objects, go back to the *Available* tab and select the relevant objects. When you are done, choose *Add Selection*. The system then imports the object definitions so that they are available for the subsequent process steps.

    > ### Note:  
    > An object can only be included in one replication flow at any given point in time \(not multiple ones\).




<a name="loio749638060e8746e48b0f9bf0e50c6d0c__result_d5p_s5r_lvb"/>

## Results

You have all necessary information about your data source in place and can move on to add your target.

