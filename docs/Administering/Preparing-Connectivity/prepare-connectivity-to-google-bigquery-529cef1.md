<!-- loio529cef1eee6a45a69ae4e51951718900 -->

# Prepare Connectivity to Google BigQuery

To be able to successfully validate and use a connection to a Google BigQuery data source for remote tables, certain preparations have to be made.



<a name="loio529cef1eee6a45a69ae4e51951718900__prereq_rt_GBQ"/>

## Remote Tables

Before you can use the connection for remote tables, the following is required:

-   A DW administrator has uploaded the server certificate to SAP Datasphere.

    > ### Note:  
    > The root certificates `GTS Root R1` and `GTS Root R4` \(valid until 2036\) are required. In your browser, open [https://pki.goog/repository/](https://pki.goog/repository/)\(*Google Trust Services Repository*\) to download the certificates \(supported filename extensions are .pem and .crt\).
    > 
    > For more information, see SAP Notes [3424000](https://me.sap.com/notes/3424000) and [3567141](https://me.sap.com/notes/3567141).

    For more information, see [Manage Certificates for Connections](manage-certificates-for-connections-46f5467.md).




<a name="loio529cef1eee6a45a69ae4e51951718900__prereq_df_GBQ"/>

## Replication Flows

Before you can use the connection for replication flows, the following is required:

-   A DW administrator has uploaded the required ODBC driver file to SAP Datasphere.

    For more information, see [Upload Third-Party ODBC Drivers \(Required for Data Flows\)](upload-third-party-odbc-drivers-required-for-data-flows-b9b5579.md).


**Related Information**  


[Google BigQuery Connections](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/30ed77de13864368bdc596099b37ed70.html "Use the connection to connect to and access data from Google BigQuery.") :arrow_upper_right:

