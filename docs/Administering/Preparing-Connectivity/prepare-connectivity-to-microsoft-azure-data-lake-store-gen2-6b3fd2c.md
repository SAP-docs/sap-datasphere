<!-- loio6b3fd2c371284637bac465edb9cc9e50 -->

# Prepare Connectivity to Microsoft Azure Data Lake Store Gen2

To be able to successfully validate and use a connection to Microsoft Azure Data Lake Store Gen2 certain preparations have to be made.



<a name="loio6b3fd2c371284637bac465edb9cc9e50__prereq_df_MS_Azure_SQL_db"/>

## Data Flows and Replication Flows

Before you can use the connection for data flows and replication flows, the following is required:

-   If you're using SAP Datasphere on Microsoft Azure and want to connect to Microsoft Azure Data Lake Store Gen2 in a firewall-protected Microsoft Azure storage account within the same Azure region: An Azure administrator must grant SAP Datasphere access to the Microsoft Azure storage account.

    For more information, see [Finding SAP Datasphere IP addresses](finding-sap-datasphere-ip-addresses-0934f7e.md)




<a name="loio6b3fd2c371284637bac465edb9cc9e50__section_glq_wfn_zfc"/>

## Connecting to Microsoft Azure Private Virtual Network Endpoints

If you're using SAP Datasphere on Microsoft Azure and want to connect to an Azure storage service in a firewall-protected Microsoft Azure storage account within the same Azure region, see the following information:

-   SAP Note [3405081](https://me.sap.com/notes/3405081)
-   Blog [Using Azure Private Virtual Network Endpoints with SAP Datasphere Replication](https://community.sap.com/t5/technology-blog-posts-by-sap/using-azure-private-virtual-network-endpoints-with-sap-datasphere/ba-p/13946050) \(published in November 2024\)
-   For obtaining the SAP Datasphere Virtual Network Subnet ID that must be allowed in the Microsoft Azure storage account: [Microsoft Azure Deployments Only: Virtual Network Subnet ID](finding-sap-datasphere-ip-addresses-0934f7e.md#loio0934f7ed9a534e638299f53ab60866ae__section_lnc_nmb_ybc)

**Related Information**  


[Microsoft Azure Data Lake Store Gen2 Connections](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/cd06b3c5ab5147c0905e3fa8abd13eb1.html "Use the connection to connect to and access objects in Microsoft Azure Data Lake Gen2 (ADL Gen2).") :arrow_upper_right:

