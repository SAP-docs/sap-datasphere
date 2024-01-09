<!-- loio441d327ead5c49d580d8600301735c83 -->

# Replicate Data Changes in Real-Time

Use real-time replication to copy the data changes from your source object in real-time into SAP Datasphere.



<a name="loio441d327ead5c49d580d8600301735c83__prereq_j3v_jmg_h4b"/>

## Prerequisites

> ### Note:  
> Availability of real-time / trigger based replication depends on the connection type. For more information on which connection types support real-time replication, see [Integrating Data via Connections](../Integrating-Data-Via-Connections/integrating-data-via-connections-eb85e15.md).

-   The object in the source has to be enabled for change data capture \(CDC\).

-   If the database table in the source is CDC enabled but the remote table has been deployed before real-time replication was possible with SAP Datasphere, you have to re-deploy the table to allow real-time replication. You can re-deploy the table in the remote table editor in the *Data Builder*.

-   For source views, real-time replication ist not supported.

-   For ABAP Dictionary tables, real-time replication is not supported.

-   For ABAP ODP sources, real-time replication is supported for in the following cases:

    -   ODP-BW: InfoProviders with a change log. This can be:

        -   DataStore objects \(advanced\) with data activation and change log \(object type ADSO\)

        -   Standard DataStore objects \(classic\) \(object type ODSO\)

        -   InfoObjects


        > ### Note:  
        > To properly display real-time capability for ODP-BW InfoProviders in SAP Datasphere, please update your SAP BW to:
        > 
        > -   SAP BW 7.4: Support Package Stack 23 or higher \(see [SAPKW74023](https://launchpad.support.sap.com/#/supportpackage/SAPKW74023)\)
        > 
        > -   SAP BW 7.5: Support Package Stack 17 or higher \(see [SAPK-75017INSAPBW](https://launchpad.support.sap.com/#/supportpackage/SAPK-75017INSAPBW)\)

    -   ODP-CDS: For all ABAP CDS views with primary key and that are delta-enabled

    -   ODP-SAPI: For all extractors that are delta enabled \(delta method ADD\* not allowed\) and have a primary key. For more information, see [CDS Views Enabled for Data Extraction](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/8308e6d301d54584a33cd04a9861bc52/b7a5b8b72d3643b7a8ecf4cd695e0791.html).

        See the blog [Finding the right CDS Extractor in SAP S/4HANA](https://blogs.sap.com/2022/01/07/finding-the-right-cds-extractor-in-sap-s-4hana/) \(published in January 2022\).

        > ### Note:  
        > For an overview of all extractors released for ODP replication \(ODP SAPI\), see SAP note [2232584](https://me.sap.com/notes/2232584).


-   For remote tables using an SAP HANA smart data access connection \(SAP HANA on-premise via Cloud Connector or SAP HANA Cloud\), you can replicate your data changes in real-time but with some restrictions as some remote object types are not supported:

    -   Remote object needs to be a table of type "COLUMN TABLE" \(other table types like Row Tables or Virtual Tables not supported\)
    -   Some data types and SAP HANA table features are not supported. For more information, see [Unsupported Data Types and Other Limitations](https://help.sap.com/viewer/477aa413a36c4a95878460696fcc8896/latest/en-US/06f6eb4859894432a0416cbb49073f32.html?q=Unsupported%20data%20types%20and%20other%20limitations).

    > ### Note:  
    > You can’t pause the replication for connections if SAP HANA smart data access is used.

-   For remote tables connected via an SAP HANA smart data integration Cloud Data Integrator \(CDI\) adapter, we recommend that you use a DP Agent version equal or higher than 2.6.1.



<a name="loio441d327ead5c49d580d8600301735c83__steps_oqr_3wj_h4b"/>

## Procedure

1.  Go to *Data Integration Monitor* and select the space in which the relevant remote table resides.

2.  Go to the *Remote Tables*.

3.  Select the remote table that you want to replicate data for.

4.  When changing from scheduled data replication to real-time replication, you must select *Data Replication* \> *Remove Replicated Data* to delete the current replicated data from the replica table and delete the schedule.

5.  Select *Data Replication* \> *Enable Real-Time Data Replication*.




<a name="loio441d327ead5c49d580d8600301735c83__result_bqm_pm5_m4b"/>

## Results

Real-time replication gets initialized by copying the data from the source. You will see the status *Active* in the *Status* column once real-time replication has been successfully initialized. Whenever data now changes in the source, the changes will be copied into SAP Datasphere. You won't be notified on individual replications. The *Latest Update* column shows date and time when data has been lastly changed in SAP Datasphere.

> ### Note:  
> No logs are generated when data is replicated in real-time mode. The displayed logs relate to previous actions.

