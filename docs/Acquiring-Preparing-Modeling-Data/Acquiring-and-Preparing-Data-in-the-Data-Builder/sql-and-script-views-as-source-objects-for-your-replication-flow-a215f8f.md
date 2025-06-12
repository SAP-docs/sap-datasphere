<!-- loioa215f8f8257d4cf88a9ef927b8b101c5 -->

# SQL and Script Views as Source Objects for Your Replication Flow

You want to use an SQL or a Script view as a source object for your replication flow.

If you use an SQL view or a script view as a source object for your replication flow, you need to consider additional specifics and conditions.



<a name="loioa215f8f8257d4cf88a9ef927b8b101c5__section_znd_yys_3fc"/>

## Available Sources

SQL or Script views can be selected as source objects for the following connections only:

-   SAP HANA Cloud
-   SAP HANA On-premise
-   SAP Datasphere



<a name="loioa215f8f8257d4cf88a9ef927b8b101c5__section_vrh_gzs_3fc"/>

## Prerequisites

You must ensure to meet the following prerequisites to add SQL or script view as source objects:

-   The load type must be *Initial Only*. Other load types are currently not supported.
-   You must define a primary key for your view to allow the deployment. You can do it in the*Object Properties* panel, under *Source Schema Settings* \> *Configure Schema*.

    > ### Note:  
    > Define primary key columns that follow the primary key constraints \(value must be unique and not null\). Wrong settings will result in data inconsistency.

-   Your view must not contain parameters.



<a name="loioa215f8f8257d4cf88a9ef927b8b101c5__section_clj_1fr_kfc"/>

## Restrictions

The following views are not supported:

-   SQL views without a semantic primary key
-   SQL views with input parameters
-   Views other than SQL view \(OLAP, JOIN, HIERARCHY, or CALC\)

