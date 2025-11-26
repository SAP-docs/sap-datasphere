<!-- loioa0b3a6e9c3f94f0bb06b81722fc5cb2b -->

# Integrating Data From SAP Integrated Business Planning

Data from SAP Integrated Business Planning can be pushed to SAP Datasphere object store to be used for further modeling activities.

> ### Note:  
> This feature is currently only available for early adopters in SAP Integrated Business Planning, which is a limited group of customers. To request being considered as an early adopter and having the feature activated in your system, contact SAP. Please use the SCM-IBP-INT-BDC component to log your request.

SAP Integrated Business Planning \(SAP IBP\) is a cloud-based solution that combines S&OP, forecasting and demand, response and supply, demand-driven replenishment, and inventory planning. To allow data push to SAP Datasphere, a connection between SAP IBP and SAP Datasphere is established using communication scenarios SAP\_COM\_1260 and SAP\_COM\_1263. For more information, [Data Integration Using SAP Datasphere of SAP Business Data Cloud](https://help.sap.com/docs/SAP_INTEGRATED_BUSINESS_PLANNING/da797ae2bf6246d58abd417f24915d55/a73c893e6a604e65b12ba0ed01903c57.html).

Once the communication scenario is ready on the SAP IBP side, you can push data to SAP Datasphere object store by scheduling an application job. Predefined application job templates are available to pick the right data up in SAP IBP and push them in SAP Datasphere.

> ### Note:  
> To push data to SAP Datasphere, you must use one of the application job templates starting with "Business Data Cloud".

For more information, see [Job Scheduling](https://help.sap.com/docs/SAP_INTEGRATED_BUSINESS_PLANNING/feae3cea3cc549aaa9d9de7d363a83e6/2a7140faec6f42a5943b855fc6b2aabf.html) and [Predefined Application Job Templates](https://help.sap.com/docs/SAP_INTEGRATED_BUSINESS_PLANNING/feae3cea3cc549aaa9d9de7d363a83e6/21918e56087ad95fe10000000a441470.html).

When publishing the data into SAP Datasphere, the application job:

1.  Collects the data from SAP IBP according to the application job template used.
2.  Pushes this data through the defined communication scenario in the inbound buffer of a dedicated SAP IBP space with storage type SAP HANA Data Lake Files \(File space\).
3.  Creates a local table \(file\) with this data in the *Data Builder*.

    > ### Note:  
    > When configuring the application job, the system administrator has defined the business name and technical name for the table that will be reused in SAP Datasphere.


The local tables \(file\) created using the SAP IBP application jobs are read-only, but data management tasks \(for example deleting data\) are possible. To use these local tables \(file\) for further modeling, you can share them to other spaces where they can be consumed, for example, in views and analytic models.

