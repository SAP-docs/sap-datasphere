<!-- loio0934f7ed9a534e638299f53ab60866ae -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Obtain SAP Datasphere IP addresses For Allowlisting in Remote Systems

Remote systems may restrict access to their instances. The remote system often decides whether an external client, such as SAP Datasphere, can access it based on allowlisted IPs. You must add SAP Datasphere's IP address to the remote system's allowlist before SAP Datasphere attempts access, via connections, for example.



<a name="loio0934f7ed9a534e638299f53ab60866ae__section_qhs_4mf_xgc"/>

## Prerequisites



<a name="loio0934f7ed9a534e638299f53ab60866ae__section_o3g_3nf_xgc"/>

## Procedure

1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(*System*\) ** \> **<span class="FPA-icons-V3"></span> \(*About*\).
2.  Open the *More* section in the dialog.
3.  You can find the following information:


    <table>
    <tr>
    <th valign="top">

    IP Adress/Information
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Replication/Data Flow NAT IP \(egress\)*
    
    </td>
    <td valign="top">
    
    To allow SAP Datasphere access to a protected remote system and using the corresponding connection with data flows or replication flows, add the *Replication/Data Flow NAT IP \(egress\)* to the allowlist in the remote system.

    **Examples:**

    -   The network for Amazon Redshift, Microsoft Azure SQL Database, or SAP SuccessFactors instances, for example, is protected by a firewall that controls incoming traffic. To be able to use connections with these connection types for data flows or replication flows, the connected sources require the relevant SAP Datasphere network address translation \(NAT\) IP address to be added to an allowlist.

    -   For Amazon Redshift and Microsoft Azure SQL Database, find the *Replication/Data Flow NAT IP \(egress\)* in the last step of the connection creation wizard.



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *SAP HANA Cloud NAT IP Addresses \(egress\)*
    
    </td>
    <td valign="top">
    
    If connecting a REST remote source to the SAP HANA Cloud instance through SAP HANA Smart Data Integration \(for example, via OData Adapter\), then the REST remote source is accessed using one of the NAT / egress IPs.

    If connecting a remote source to the SAP HANA Cloud instance using SAP HANA Smart Data Access, then the connection uses the NAT / egress IP in case the Cloud Connector is not used in the scenario.

    For more information, see [Domains and IP Ranges](https://help.sap.com/docs/hana-cloud/sap-hana-cloud-administration-guide/domains-and-ip-ranges) in the SAP HANA Cloud documentation.

    **Example:**

    Access to SAP SuccessFactors instances is restricted. To be able to use a*SAP SuccessFactors* connection for remote tables, the connected source requires the externally facing IP addresses of theSAP Datasphere tenant to be added to an allowlist.

    For more information about adding the IP addresses in SAP SuccessFactors, see [Adding an IP Restriction](https://help.sap.com/viewer/DRAFT/bf014ed11dae45ecae6f8c6e42fa68bb/latest/en-US/34a127f33b504201b7da29a112f21bc5.html) in the *SAP SuccessFactors platform* documentation.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Virtual Network Subnet ID* \(for Microsoft Azure deployments only\)
    
    </td>
    <td valign="top">
    
    If you're using SAP Datasphere on Microsoft Azure and want to connect to an Azure storage service in a firewall-protected Microsoft Azure storage account within the same Azure region, an administrator must allow the SAP Datasphere's Virtual Network Subnet ID in the Microsoft Azure storage account. This is required for connections to Azure storage services such as Microsoft Azure Data Lake Store Gen2.

    For more information, see SAP Note [3405081](https://me.sap.com/notes/3405081).
    
    </td>
    </tr>
    </table>
    



<a name="loio0934f7ed9a534e638299f53ab60866ae__section_jjn_2fd_ybc"/>

## Related Links

SAP Note [3456052](https://me.sap.com/notes/3456052) \(FAQ: About IP Addresses used in SAP Datasphere\)

