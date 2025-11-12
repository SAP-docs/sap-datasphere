<!-- loio27c7761eaef44a6da4e3ae6bc9acbc90 -->

# Export Your Space Data

You can export the data contained in your space at any time. For example, you may want to export data before deleting your space.

> ### Note:  
> Relevant only for spaces with a storage type *SAP HANA Database \(Disk and In-Memory\)*, and not for *SAP HANA Data Lake Files* spaces.



<a name="loio27c7761eaef44a6da4e3ae6bc9acbc90__section_jvy_c3j_42c"/>

## Prerequisites

All of the data you want to export for your space must either be contained in views that are exposed for consumption \(see [Exposing Data For Consumption](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/40ec77ec24f244279a81448969a7e769.html "Data can only be accessed outside of your SAP Datasphere space if it is exposed for consumption.") :arrow_upper_right:\) or be written to an Open SQL schema from the space via a flow \(see [Allow the Space to Access the Open SQL Schema](Integrating-Data-Via-Database-Users/Open-SQL-Schema/allow-the-space-to-access-the-open-sql-schema-7eaa370.md)\). Also, you must have access to a database user \(see [Create a Database User](Integrating-Data-Via-Database-Users/Open-SQL-Schema/create-a-database-user-798e3fd.md)\).



<a name="loio27c7761eaef44a6da4e3ae6bc9acbc90__section_ylp_13j_42c"/>

## Procedure

To export data using an ETL tool such as SAP HANA Database Explorer, follow these steps:

1.  Connect to your Open SQL schema with SAP HANA Database Explorer \(see [Connect to Your Open SQL Schema](Integrating-Data-Via-Database-Users/Open-SQL-Schema/connect-to-your-open-sql-schema-b78ad20.md)\).

2.  Export the data \(see [Export Schemas, Tables, and Other Catalog Objects](https://help.sap.com/docs/SAP_HANA_COCKPIT/e8d0ddfb84094942a9f90288cd6c05d3/1f20a6c4364c4b0680596e74e4ba281d.html) in the *SAP HANA Database Explorer* guide\).


