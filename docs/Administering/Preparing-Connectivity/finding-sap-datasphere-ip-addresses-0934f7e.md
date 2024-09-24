<!-- loio0934f7ed9a534e638299f53ab60866ae -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Finding SAP Datasphere IP addresses

Find externally facing IP addresses and IDs that must be added to allowlists in particular remote applications before you can use connections to these remote applications.

Remote applications might restrict access to their instances. Whether an external client such as SAP Datasphere is allowed to access the remote application is often decided by the remote application based on allowlisted IPs. Any external client trying to access the remote appplication has to be made known to the remote application before first trying to access the application by adding the external client's IP address\(es\) to an allowlist in the remote application. As an SAP Datasphere administrator or a user with the System Information = Read privilege you can find the necessary information in the *About* dialog.

Particular remote applications or sources that you might want to access with SAP Datasphere restrict access to their instances and require external SAP Datasphere IP address information to be added to an allowlist in the remote application before first trying to access the application.

Users with the DW Administrator role can open a *More* section to find more details.



<a name="loio0934f7ed9a534e638299f53ab60866ae__section_dlm_gpv_y4b"/>

## Replication/Data Flow NAT IP \(egress\)

To allow SAP Datasphere access to a protected remote application and using the corresponding connection with data flows or replication flows, add the *Replication/Data Flow NAT IP \(egress\)* to the remote application allowlist.

Administrators can find the *Replication/Data Flow NAT IP \(egress\)* from the side navigation area by clicking <span class="FPA-icons-V3"></span> \(*System*\)** \> ** <span class="FPA-icons-V3"></span> \(*About*\)** \> ***More*** \> ** *Replication/Data Flow NAT IP \(egress\)*.



### Examples

The network for Amazon Redshift, Microsoft Azure SQL Database, or SAP SuccessFactors instances, for example, is protected by a firewall that controls incoming traffic. To be able to use connections with these connection types for data flows or replication flows, the connected sources require the relevant SAP Datasphere network address translation \(NAT\) IP address to be added to an allowlist.

For Amazon Redshift and Microsoft Azure SQL Database, find the *Replication/Data Flow NAT IP \(egress\)* in the last step of the connection creation wizard.



<a name="loio0934f7ed9a534e638299f53ab60866ae__section_itp_3pv_y4b"/>

## SAP HANA Cloud NAT IP Addresses \(Egress\)

\(IP address of the SAP Datasphere's SAP HANA Cloud database instance\)

If connecting a REST remote source to the HANA Cloud instance through SDI \(for example, OData Adapter\), then the REST remote source is accessed using one of the NAT / egress IPs.

If connecting a remote source using SDA to the HANA Cloud instance, then the connection uses the NAT / egress IP in case the Cloud Connector is not used in the scenario.

Administrators can find the NAT IPs from the side navigation area by clicking <span class="FPA-icons-V3"></span> \(*System*\)** \> ** <span class="FPA-icons-V3"></span> \(*About*\)** \> ***More*** \> ** *SAP HANA Cloud NAT IP \(egress\)*.

For more information, see [Domains and IP Ranges](https://help.sap.com/docs/hana-cloud/sap-hana-cloud-administration-guide/domains-and-ip-ranges) in the SAP HANA Cloud documentation.



### Example: SAP SuccessFactors

Access to SAP SuccessFactors instances is restricted. To be able to use a*SAP SuccessFactors* connection for remote tables and view building, the connected source requires the externally facing IP addresses of theSAP Datasphere tenant to be added to an allowlist.

For more information about adding the IP addresses in SAP SuccessFactors, see [Adding an IP Restriction](https://help.sap.com/viewer/DRAFT/bf014ed11dae45ecae6f8c6e42fa68bb/latest/en-US/34a127f33b504201b7da29a112f21bc5.html) in the *SAP SuccessFactors platform* documentation.



<a name="loio0934f7ed9a534e638299f53ab60866ae__section_lnc_nmb_ybc"/>

## Microsoft Azure Deployments Only: Virtual Network Subnet ID

If you're using SAP Datasphere on Microsoft Azure and want to connect to an Azure storage service in a firewall-protected Microsoft Azure storage account within the same Azure region, an administrator must allow the SAP Datasphere's Virtual Network Subnet ID in the Microsoft Azure storage account. This is required for connections to Azure storage services such as Microsoft Azure Data Lake Store Gen2.

For more information, see SAP Note [3405081](https://me.sap.com/notes/3405081).

Administrators can find the ID from the side navigation area by clicking <span class="FPA-icons-V3"></span> \(*System*\)** \> ** <span class="FPA-icons-V3"></span> \(*About*\)** \> ***More*** \> ** *Virtual Network Subnet ID \(Microsoft Azure\)*.



<a name="loio0934f7ed9a534e638299f53ab60866ae__section_jjn_2fd_ybc"/>

## Related Links

SAP Note [3456052](https://me.sap.com/notes/3456052) \(FAQ: About IP Addresses used in SAP Datasphere\)

