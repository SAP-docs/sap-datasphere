<!-- loio6b3fd2c371284637bac465edb9cc9e50 -->

# Prepare Connectivity to Microsoft Azure Data Lake Store Gen2

To be able to successfully validate and use a connection to Microsoft Azure Data Lake Store Gen2 certain preparations have to be made.



<a name="loio6b3fd2c371284637bac465edb9cc9e50__prereq_df_MS_Azure_SQL_db"/>

## Data Flows and Replication Flows

Before you can use the connection for data flows and replication flows, the following is required:

-   If you're using SAP Datasphere on Microsoft Azure and want to connect to Microsoft Azure Data Lake Store Gen2 in a firewall-protected Microsoft Azure storage account within the same Azure region: An Azure administrator must grant SAP Datasphere access to the Microsoft Azure storage account.

    For more information, see [Obtain SAP Datasphere IP addresses For Allowlisting in Remote Systems](obtain-sap-datasphere-ip-addresses-for-allowlisting-in-remote-systems-0934f7e.md)




<a name="loio6b3fd2c371284637bac465edb9cc9e50__section_glq_wfn_zfc"/>

## Connecting to Microsoft Azure Private Virtual Network Endpoints

If you're using SAP Datasphere on Microsoft Azure and want to connect to an Azure storage service in a firewall-protected Microsoft Azure storage account within the same Azure region, see the following information:

-   SAP Note [3405081](https://me.sap.com/notes/3405081)
-   Blog [Using Azure Private Virtual Network Endpoints with SAP Datasphere Replication](https://community.sap.com/t5/technology-blog-posts-by-sap/using-azure-private-virtual-network-endpoints-with-sap-datasphere/ba-p/13946050) \(published in November 2024\)
-   For obtaining the SAP Datasphere Virtual Network Subnet ID that must be allowed in the Microsoft Azure storage account: [Obtain SAP Datasphere IP addresses For Allowlisting in Remote Systems](obtain-sap-datasphere-ip-addresses-for-allowlisting-in-remote-systems-0934f7e.md)

**Related Information**  


[Microsoft Azure Data Lake Store Gen2 Connections](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/cd06b3c5ab5147c0905e3fa8abd13eb1.html "Use the connection to connect to and access objects in Microsoft Azure Data Lake Gen2 (ADL Gen2).") :arrow_upper_right:

