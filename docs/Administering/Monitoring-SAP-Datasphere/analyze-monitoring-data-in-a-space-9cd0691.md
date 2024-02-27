<!-- loio9cd0691c44a74f2aa47b52f615f74433 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Analyze Monitoring Data in a Space

Define the two spaces dedicated to monitoring SAP Datasphere \(such as monitoring the database for resource consumption\).



<a name="loio9cd0691c44a74f2aa47b52f615f74433__section_ng5_gfb_xpb"/>

## Prerequisites

You need the DW Administrator role to access the *Monitoring* page and select a space.



<a name="loio9cd0691c44a74f2aa47b52f615f74433__section_txh_hfb_xpb"/>

## Context

Monitoring information provided by monitoring views can be sensitive as it includes information on all spaces and views. This is why these views are not accessible to all users by default in SAP Datasphere. However, as an administrator, you can select two spaces dedicated to monitoring information. The users who are assigned to the spaces and have modeling privileges, can then access the monitoring views in the Data Builder.

As the monitoring spaces you choose will provide unfiltered access to monitoring views, be aware that the users assigned to the spaces will be able to see all metadata and object definitions of all spaces.

You can dedicate one or two of these spaces to monitoring:

-   Space to choose among all spaces - Choose a space that you want to dedicate to monitoring views.

    > ### Note:  
    > If you have already selected a space dedicated to monitoring before version 2021.19, you need to select another space, then select the initial space again so that you can access all the views.

-   *<SAP\_ADMIN\>* space - This space is dedicated to the pre-configured monitoring views provided as business content by SAP via the *Content Network*. First create the space with the space ID *<SAP\_ADMIN\>* and the space name *<Administration \(SAP\)\>*, enable access to it and import the package from the *Content Network*.

    > ### Note:  
    > Please do not create a space with the space ID *<SAP\_ADMIN\>* for another purpose.

    For more information about the package prepared by SAP, see [Monitoring Tasks, Logs and Schedules With Dedicated Monitoring Views](monitoring-tasks-logs-and-schedules-with-dedicated-monitoring-views-4ab4509.md).




<a name="loio9cd0691c44a74f2aa47b52f615f74433__section_ukj_hfb_xpb"/>

## Monitoring Views Available in Monitoring Spaces

Once you’ve chosen one or two monitoring spaces, the users assigned to the spaces can access the following monitoring views in the *Data Builder* editors:

-   **SAP HANA SYS Schema Monitoring Views**

    All SAP HANA monitoring views start with M\_. For more information about all the monitoring views available, see [Monitoring Views](https://help.sap.com/viewer/c1d3f60099654ecfb3fe36ac93c121bb/latest/en-US/d3c10d23e8334a35afa8d9bdbc102366.html) in the *SAP HANA Cloud, SAP HANA Database SQL Reference Guide*.

    The views for expensive statement are M\_EXPENSIVE\_STATEMENTS and M\_EXPENSIVE\_STATEMENT\_EXECUTION\_LOCATION\_STATISTICS. For more information, see [M\_EXPENSIVE\_STATEMENTS](https://help.sap.com/viewer/c1d3f60099654ecfb3fe36ac93c121bb/latest/en-US/20af736e751910148162e2ab1982f035.html) and [M\_EXPENSIVE\_STATEMENT\_EXECUTION\_LOCATION\_STATISTICS](https://help.sap.com/viewer/c1d3f60099654ecfb3fe36ac93c121bb/latest/en-US/80c32e9dc5b742efa254adfe164102dc.html) in the *SAP HANA Cloud, SAP HANA Database SQL Reference Guide*.

    The view M\_MULTIDIMENSIONAL\_STATEMENT\_STATISTICS provides extensive information about MDS queries. For more information, see [M\_MULTIDIMENSIONAL\_STATEMENT\_STATISTICS System View](https://help.sap.com/viewer/c1d3f60099654ecfb3fe36ac93c121bb/latest/en-US/5b04f05f501f4f91aea202f1394cfddc.html) in the *SAP HANA Cloud, SAP HANA Database SQL Reference Guide*.

-   **SAP HANA \_SYS\_STATISTICS Schema Statistics Service Views**

    For more information, see [Embedded Statistics Service Views \(\_SYS\_STATISTICS schema\)](https://help.sap.com/viewer/323c57a017234d47a0e7da3e22345822/latest/en-US/d234eedbd29510148efbf332391de7fd.html).

-   **SAP HANA \_SYS\_BI Schema Tables and Views**

    For more information, see [BIMC Tables and Views](https://help.sap.com/docs/hana-cloud-database/sap-hana-cloud-sap-hana-analytics-catalog-bimc-views-reference/bimc-tables-and-views) in the *SAP HANA Cloud, SAP HANA Analytics Catalog \(BIMC Views\) Reference*.

-   **SAP HANA DWC\_GLOBAL Schema Monitoring Views**

    For more information, see [Monitoring Tasks, Logs and Schedules With Dedicated Monitoring Views](monitoring-tasks-logs-and-schedules-with-dedicated-monitoring-views-4ab4509.md).

-   **SAP Datasphere Monitoring Views \(Delivered via the Content Network\)**

    These views are available in the *<SAP\_ADMIN\>* space if you've enabled the space and imported the dedicated monitoring package from the *Content Network*.




<a name="loio9cd0691c44a74f2aa47b52f615f74433__section_b5f_scz_b5b"/>

## *Expensive Statement Tracing*

In the area *Expensive Statement Tracing*, you can enable expensive statement tracing to analyze individual SQL queries whose execution exceeds one or more thresholds that you specify.

-   The information on statements that exceed the specified thresholds are included in dedicated views that you can access in the selected monitoring space.

-   All the database statements that exceed the thresholds specified for memory consumption \(*Threshold Memory*\) and runtime \(*Threshold Duration*\) are displayed in the widgets and tables of the *System Monitor*. If expensive statement tracing is not enabled, then statement information and errors are not traced and you cannot see them in the *System Monitor* \(see [Monitoring SAP Datasphere](monitoring-sap-datasphere-28910cd.md)\).

-   By default, 30 000 records maximum are stored in the monitoring tables. You can change this number, which will impact the views dedicated to monitoring and information related to statements in the *System Monitor*. For example, if about 5 days are traced in the expensive statement tables and you don’t want to change the thresholds, you can double the number of records in *In-Memory Tracing Records* so that about 10 days are traced. Be aware that increasing this number will also increase the used storage.




<a name="loio9cd0691c44a74f2aa47b52f615f74433__section_adv_gcj_gxb"/>

## MDS Information Tracing

To analyze individual SAP HANA multi-dimensional services \(MDS\) query, you can enable the tracing of MDS information in the area *MDS Information Tracing*.

If the tracing is enabled, you can view information on MDS queries when clicking *More* in the column *Statement Details* of the *Statements* tab in the *System Monitor* \(see [Monitoring SAP Datasphere](monitoring-sap-datasphere-28910cd.md)\).



<a name="loio9cd0691c44a74f2aa47b52f615f74433__section_jt3_hfb_xpb"/>

## Procedure

1.  Go to <span class="FPA-icons-V3"></span> \(Configuration\) → *Monitoring*.
2.  Select a space from the drop-down list and click *Confirm Selected Space*.
3.  If you've created the *<SAP\_ADMIN\>* space and you want to enable it, click *Enable access to SAP Monitoring Content Space*. If there isn't any space named *<SAP\_ADMIN\>* in your tenant, this is not available for selection.
4.  To trace expensive statements, select *Enable Expensive Statement Tracing*, specify the following parameters to configure and filter the trace details, then save your changes.

    -   *In-Memory Tracing Records*: Change, if needed, the maximum number of records that are stored in the monitoring tables.

    -   *Threshold CPU Time*: Specifies the threshold CPU time of statement execution. When set to 0, all SQL statements are traced.

    -   *Threshold Memory*: Specifies the threshold memory usage of statement execution. When set to 0, all SQL statements are traced.

    -   *Threshold Duration*: Specifies the threshold execution time. When set to 0, all SQL statements are traced.

    -   *Trace Parameter Values*: In SQL statements, field values may be specified as parameters \(using a "?" in the syntax\). If these parameter values are not required, then do not select the option to reduce the amount of data traced.


    For more information about these parameters, see [Expensive Statements Trace](https://help.sap.com/viewer/f9c5015e72e04fffa14d7d4f7267d897/latest/en-US/5faf04f17830464eacdb7938b383d2ab.html) in the *SAP HANA Cloud, SAP HANA Database Administration Guide*.

5.  To trace MDS information, select *Enable MDS Information Tracing* and save.



<a name="loio9cd0691c44a74f2aa47b52f615f74433__section_qxx_z2n_yqb"/>

## Troubleshooting

After the configuration, if you face authorization issues due to insufficient privilege on the monitoring views \(suffix V\_EXT\) in your monitoring space, the solution is to choose another space as the monitoring space in the configuration UI, and then select the existing current monitoring space again.

