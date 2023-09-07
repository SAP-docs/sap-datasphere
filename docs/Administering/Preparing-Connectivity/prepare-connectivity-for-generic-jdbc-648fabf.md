<!-- loio648fabfc94ad4da7853ef9a4d284aeac -->

# Prepare Connectivity for Generic JDBC

To be able to successfully validate and use a Generic JDBC connection for remote tables certain preparations have to be made.



<a name="loio648fabfc94ad4da7853ef9a4d284aeac__prereq_rt_Generic_JDBC"/>

## Remote Tables

Before you can use the connection for creating views and accessing data via remote tables, the following is required:

-   An administrator has connected an SAP HANA smart data integration Data Provisioning Agent to SAP Datasphere and registered the CamelJdbcAdapter.

    For more information, see [Preparing Data Provisioning Agent Connectivity](preparing-data-provisioning-agent-connectivity-f1a39d1.md).

-   It has been checked that the data source is supported by the CamelJdbcAdapter.

    For latest information about supported data sources and versions, see the [SAP HANA Smart Data Integration Product Availability Matrix \(PAM\)](https://support.sap.com/content/dam/launchpad/en_us/pam/pam-essentials/TIP/PAM_HANA_SDI_2_0.pdf).

    > ### Note:  
    > For information about unsupported data sources, see [3130999](https://me.sap.com/notes/3130999).

-   An administrator has downloadad and installed the required JDBC library in the <code><i class="varname">&lt;DPAgent_root&gt;</i>/camel/lib</code> folder and restarted the Data Provisioning Agent before registering the adapter with SAP Datasphere.

    For more information, see [Set up the Camel JDBC Adapter](https://help.sap.com/viewer/7952ef28a6914997abc01745fef1b607/latest/en-US/1247c9518f8d4b5b93fa2ad54cb2dcf6.html) in the *SAP HANA Smart Data Integration and SAP HANA Smart Data Quality Installation and Configuration Guide*.

    For information about the proper JDBC library for your source, see the *SAP HANA smart data integration Product Availability Matrix \(PAM\)*.


