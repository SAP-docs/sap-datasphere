<!-- loioe84545bd205b4f9f9c1731144c7d3075 -->

# Integrating Data to and From SAP HANA Cloud Data Lake

Connect your SAP Datasphere space with SAP HANA Cloud, data lake to store and gain access to large amounts of data.



## What is SAP HANA Cloud, data lake?

Data lake is a fully managed cloud service for securely storing and analyzing large amounts of data that is infrequently updated. It leverages inexpensive storage options to lower costs, while maintaining excellent performance and full SQL access to data.

Data lake includes elastically scalable compute to provide high-performance analysis on-demand, and enabling cost control when it isn’t in use. It’s fully integrated into SAP HANA Cloud, sharing common security, tenancy, and tooling.

For more information on data lake, please visit the [SAP HANA Cloud, Data Lake](https://help.sap.com/docs/hana-cloud-data-lake) product page.



<a name="loioe84545bd205b4f9f9c1731144c7d3075__section_u51_snh_2mb"/>

## Working with data lake in SAP Datasphere

To benefit from data lake, you need to assign a SAP Datasphere space that gets access to the data lake. Currently, only one space can be assigned to access and use the data lake.

Tables in the data lake are accessed via virtual tables in the open SQL schema. These tables can be consumed in the *Data Builder*. SAP Datasphere provides two stored procedures to ease this task. Take a look at [Data Lake API](data-lake-api-12b6825.md) for more details and examples on how to use the procedures.

For a detailed step-by-step guide to connect and work with your data lake see [Working with Data Lake](working-with-data-lake-93d0b5d.md).

