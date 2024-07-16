<!-- loio0934f7ed9a534e638299f53ab60866ae -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Finding SAP Datasphere IP addresses

Find externally facing IP addresses and IDs that must be added to allowlists in particular remote applications before you can use connections to these remote applications.

Particular remote applications or sources that you might want to access with SAP Datasphere restrict access to their instances and require external SAP Datasphere IP address information to be added to an allowlist in the remote application before first trying to access the application.



<a name="loio0934f7ed9a534e638299f53ab60866ae__section_dlm_gpv_y4b"/>

## Outbound IP Address

The network for Amazon Redshift, Microsoft Azure SQL Database, or SAP SuccessFactors instances, for example, is protected by a firewall that controls incoming traffic. To be able to use connections with these connection types for data flows or replication flows, the connected sources require the SAP Datasphere outbound IP address to be added to an allowlist.

Find the *Outbound IP Address* in the last step of the connection creation wizard.

Administrators can find the *Outbound IP Address* from the side navigation area by clicking <span class="FPA-icons-V3"></span> \(*System*\)** \> ** <span class="FPA-icons-V3"></span> \(*About*\) and expanding the *More* section in the dialog.



<a name="loio0934f7ed9a534e638299f53ab60866ae__section_itp_3pv_y4b"/>

## SAP HANA Cloud NAT IP Addresses \(Egress\)

Access to SAP SuccessFactors instances is restricted. To be able to use a*SAP SuccessFactors* connection for remote tables and view building, the connected source requires the externally facing IP addresses of theSAP Datasphere tenant to be added to an allowlist.

Administrators can find the NAT IPs from the side navigation area by clicking <span class="FPA-icons-V3"></span> \(*System*\)** \> ** <span class="FPA-icons-V3"></span> \(*About*\)** \> ***More*** \> ** *HANA IP Addresses*.

For more information about adding the IP addresses in SAP SuccessFactors, see [Adding an IP Restriction](https://help.sap.com/viewer/DRAFT/bf014ed11dae45ecae6f8c6e42fa68bb/latest/en-US/34a127f33b504201b7da29a112f21bc5.html) in the *SAP SuccessFactors platform* documentation.



<a name="loio0934f7ed9a534e638299f53ab60866ae__section_lnc_nmb_ybc"/>

## Microsoft Azure Deployments Only: Virtual Network Subnet ID

If you're using SAP Datasphere on Microsoft Azure and want to connect to an Azure storage service in a firewall-protected Microsoft Azure storage account within the same Azure region, an administrator must allow the SAP Datasphere's Virtual Network Subnet ID in the Microsoft Azure storage account. This is required for connections to Azure storage services such as Microsoft Azure Data Lake Store Gen2.

For more information, see SAP Note [3405081](https://me.sap.com/notes/3405081).

Administrators can find the ID from the side navigation area by clicking <span class="FPA-icons-V3"></span> \(*System*\)** \> ** <span class="FPA-icons-V3"></span> \(*About*\)** \> ***More*** \> ** *Virtual Network Subnet ID \(Microsoft Azure\)*.



<a name="loio0934f7ed9a534e638299f53ab60866ae__section_jjn_2fd_ybc"/>

## Related Links

SAP Note [3456052](https://me.sap.com/notes/3456052) \(FAQ: About IP Addresses used in SAP Datasphere\)

