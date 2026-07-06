<!-- loioe84545bd205b4f9f9c1731144c7d3075 -->

# Integrating Data to and From SAP HANA Cloud Data Lake

Users with an administrator role can connect an SAP Datasphere space with SAP HANA Cloud, data lake to store and access large amounts of data. 

> ### Caution:  
> The information below is about working on spaces created with SAP Hana Cloud, data lake relational engine \(see [Working with Data Lake](working-with-data-lake-93d0b5d.md)\) and not SAP HANA Cloud, data lake files which is used to create spaces dedicated to the object store \(see [Create a File Space to Load Data in the Object Store](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/947444683e524cfd9169d7671b72ba0c.html "Create a file space and allocate compute resources to it. File spaces are intended for loading and preparing large quantities of data in an inexpensive inbound staging area and are stored in the SAP Datasphere object store.") :arrow_upper_right:\).
> 
> You might check the following additional documentations on SAP HANA Cloud, data lake relational engine:
> 
> -   [What's the Difference Between Data Lake Relational Engine and SAP HANA Database SQL Statements?](https://help.sap.com/docs/SAP_HANA_DATA_LAKE/9220e7fec0fe4503b5c5a6e21d584e63/f23b60ec161a46f9b906eac15c5a3b95.html)
> -   [System Views in Data Lake Relational Engine \(SAP HANA DB-Managed\)](https://help.sap.com/docs/SAP_HANA_DATA_LAKE/a898e08b84f21015969fa437e89860c8/92e2e6c466d844e0b0e961069aa3b8d7.html)
> -   [Query Data in Data Lake Relational Engine \(SAP HANA DB-Managed\)](https://help.sap.com/docs/SAP_HANA_DATA_LAKE/9220e7fec0fe4503b5c5a6e21d584e63/9c80f123c5d74f71a9f536682f2f479c.html)



## What is SAP HANA Cloud, data lake?

Data lake is a fully managed cloud service for securely storing and analyzing large amounts of data that is infrequently updated. It leverages inexpensive storage options to lower costs, while maintaining excellent performance and full SQL access to data.

Data lake includes elastically scalable compute to provide high-performance analysis on-demand, and enabling cost control when it isn’t in use. It’s fully integrated into SAP HANA Cloud, sharing common security, tenancy, and tooling.

For more information on data lake, please visit the [SAP HANA Cloud, Data Lake](https://help.sap.com/docs/hana-cloud-data-lake) product page.



<a name="loioe84545bd205b4f9f9c1731144c7d3075__section_u51_snh_2mb"/>

## Working with data lake in SAP Datasphere

To benefit from data lake, you need to assign a SAP Datasphere space that gets access to the data lake. Currently, only one space can be assigned to access and use the data lake.

Tables in the data lake are accessed via virtual tables in the open SQL schema. These tables can be consumed in the *Data Builder*. SAP Datasphere provides two stored procedures to ease this task. Take a look at [Data Lake API](data-lake-api-12b6825.md) for more details and examples on how to use the procedures.

For a detailed step-by-step guide to connect and work with your data lake see [Working with Data Lake](working-with-data-lake-93d0b5d.md).

