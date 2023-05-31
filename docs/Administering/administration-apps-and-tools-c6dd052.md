<!-- loioc6dd05236838466c831170c5cd67e85e -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Administration Apps and Tools

You administer SAP Datasphere using apps and tools in the side navigation area.



<a name="loioc6dd05236838466c831170c5cd67e85e__section_qvk_d5x_25b"/>

## ![](images/Space_Management_a868247.png) \(*Space Management*\)

In the *Space Management*, you can set up, configure, and monitor your spaces, including assigning users to them. For more information, see [Preparing Your Space and Integrating Data](https://help.sap.com/viewer/d4f3c5a0bb074d09ae9b42b2b9bd7a08/cloud/en-US/8cb00503395049029055bb7aceafc080.html "Users with the DW Space Administrator or DW Integrator role can create connections to source systems and databases and use other methods to bring data into their space. They can schedule and monitor data replication and other data integration tasks. Space administrators are responsible for maintaining the list of space members and monitoring and managing the space. They can create data access controls to secure data, and can transport content between tenants.") :arrow_upper_right:.



<a name="loioc6dd05236838466c831170c5cd67e85e__section_irx_vkk_c5b"/>

## \(*System Monitor*\)

In the *System Monitor*, you can monitor the performance of your system and identify storage, task, out-of-memory, and other issues. For more information, see [Monitoring SAP Datasphere](Monitoring-SAP-Datasphere/monitoring-sap-datasphere-28910cd.md).



<a name="loioc6dd05236838466c831170c5cd67e85e__section_ar4_2cn_fsb"/>

## Security


<table>
<tr>
<th valign="top">

Tool



</th>
<th valign="top">

Task



</th>
<th valign="top">

More Information



</th>
</tr>
<tr>
<td valign="top">

*Users*



</td>
<td valign="top">

Create, modify, and manage users in SAP Datasphere.



</td>
<td valign="top">

[Managing SAP Datasphere Users](Managing-Users-and-Roles/managing-sap-datasphere-users-4fb82cb.md)



</td>
</tr>
<tr>
<td valign="top">

*Roles*



</td>
<td valign="top">

Assign pre-defined standard roles or custom roles that you have created to users.



</td>
<td valign="top">

[Managing Roles and Privileges](Managing-Users-and-Roles/managing-roles-and-privileges-3740dac.md)



</td>
</tr>
<tr>
<td valign="top">

*Activities*



</td>
<td valign="top">

Track the activities that users perform on objects such as spaces, tables, views, data flows, and others, track changes to users and roles, and more.



</td>
<td valign="top">

[Monitor Object Changes with Activities](Monitoring-SAP-Datasphere/monitor-object-changes-with-activities-08e607c.md)



</td>
</tr>
</table>



<a name="loioc6dd05236838466c831170c5cd67e85e__section_qvw_cbb_dpb"/>

## System ** \> ** Configuration


<table>
<tr>
<th valign="top">

Tab



</th>
<th valign="top">

Task



</th>
<th valign="top">

More Information



</th>
</tr>
<tr>
<td valign="top" rowspan="3">

*Data Integration*



</td>
<td valign="top">

*Live Data Connections \(Tunnel\)*: For SAP BW∕4HANA model import, you need Cloud Connector to make http requests to SAP BW∕4HANA. This requires a live data connection of type tunnel to SAP BW∕4HANA.



</td>
<td valign="top">

[Create Live Data Connection of Type Tunnel](Preparing-Connectivity/create-live-data-connection-of-type-tunnel-5d02f11.md)



</td>
</tr>
<tr>
<td valign="top">

*On-Premise Agents*: Manage Data Provisioning Agents which are required to act as gateway to SAP Datasphereto enable using connections to on-premise sources for remote tables and building views.



</td>
<td valign="top">

[Connect and Configure the Data Provisioning Agent](Preparing-Connectivity/connect-and-configure-the-data-provisioning-agent-e87952d.md)

[Register Adapters with SAP Datasphere](Preparing-Connectivity/register-adapters-with-sap-datasphere-085fc49.md)

[Monitoring Data Provisioning Agent in SAP Datasphere](monitoring-data-provisioning-agent-in-sap-datasphere-c33c937.md)

[Pause Real-Time Replication for an Agent](pause-real-time-replication-for-an-agent-dac31a5.md)



</td>
</tr>
<tr>
<td valign="top">

*Third-Party Drivers*: Upload driver files that are required for certain third-party cloud connections to use them for data flows.



</td>
<td valign="top">

[Upload Third-Party ODBC Drivers \(Required for Data Flows\)](Preparing-Connectivity/upload-third-party-odbc-drivers-required-for-data-flows-b9b5579.md)



</td>
</tr>
<tr>
<td valign="top">

*Tenant Links*



</td>
<td valign="top">

*Link My Tenants*: Link an SAP Analytics Cloud tenant to your SAP Datasphere tenant to enable the product switch in the top right of the shell bar, and be able to easily navigate between them.



</td>
<td valign="top">

[Enable the Product Switch to Access an SAP Analytics Cloud Tenant](Creating-and-Configuring-Your-Tenant/enable-the-product-switch-to-access-an-sap-analytics-cloud-tenant-40db567.md)



</td>
</tr>
<tr>
<td valign="top" rowspan="2">

*Security*



</td>
<td valign="top">

*SSL/TLS Certificates* : Upload server certificates to enable secure SSL/TLS-based connections to certain sources.



</td>
<td valign="top">

[Upload Certificates \(Required for Remote Tables\)](Preparing-Connectivity/upload-certificates-required-for-remote-tables-46f5467.md)



</td>
</tr>
<tr>
<td valign="top">

*Password Policy Configuration*: Define your password policy settings for the database users. The policy can be enabled when configuring your database users.



</td>
<td valign="top">

[Set a Password Policy for Database Users](Managing-Users-and-Roles/set-a-password-policy-for-database-users-14aedf6.md)



</td>
</tr>
<tr>
<td valign="top">

*Audit*



</td>
<td valign="top">

*Audit View Enablement*: Configure a space that gets access to audit views and allows you to display the audit logs in that space.



</td>
<td valign="top">

[Enable or Disable Audit Logging](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/266553976e1c4db9aaa28a75e2308b77.html "You can enable audit logs for your space so that read and change actions (policies) are recorded. Administrators can then analyze who did what and when in the database.") :arrow_upper_right:



</td>
</tr>
<tr>
<td valign="top">

*IP Allowlist*



</td>
<td valign="top">

*IP Allowlist*: Control the range of external public IPv4 addresses that get access to the database of your SAP Datasphere by adding them to an allowlist.



</td>
<td valign="top">

[Add IP address to IP Allowlist](Preparing-Connectivity/add-ip-address-to-ip-allowlist-a3c2145.md)



</td>
</tr>
<tr>
<td valign="top">

*Task Logs*



</td>
<td valign="top">

Clean-up task logs to reduce storage consumption in your SAP Datasphere tenant.



</td>
<td valign="top">

[Deleting Task Logs to Reduce Storage Consumption](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/c6902024ecd74956b4ba2d1c67ccb073.html "In the Configuration area, you can check how much spaces the task logs are using on your tenant, and decide to delete the obsolete ones to reduce storage consumption.") :arrow_upper_right:



</td>
</tr>
<tr>
<td valign="top" rowspan="2">

*Database Access*



</td>
<td valign="top">

*Database Analysis Users*: Create a database analysis user to connect to your SAP HANA Cloud database to analyze, diagnose and solve database issues. Only create this user for a specific specific task and delete right after the task has been completed.



</td>
<td valign="top">

[Monitoring SAP Datasphere](Monitoring-SAP-Datasphere/monitoring-sap-datasphere-28910cd.md)



</td>
</tr>
<tr>
<td valign="top">

*Database User Groups*: Create an isolated environment with corresponding administrators where you can work more freely with SQL in your SAP HANA Cloud database.



</td>
<td valign="top">

[Creating a Database User Group](Creating-a-Database-User-Group/creating-a-database-user-group-1097a47.md)



</td>
</tr>
<tr>
<td valign="top">

*Tenant Configuration*



</td>
<td valign="top">

Allocate the capacity units to storage and compute resources for your tenant.



</td>
<td valign="top">

[Configure the Size of Your SAP Datasphere Tenant](Creating-and-Configuring-Your-Tenant/configure-the-size-of-your-sap-datasphere-tenant-33f8ef4.md)



</td>
</tr>
</table>



<a name="loioc6dd05236838466c831170c5cd67e85e__section_yvv_dbb_dpb"/>

## System ** \> ** Administration


<table>
<tr>
<th valign="top">

Tab



</th>
<th valign="top">

Task



</th>
<th valign="top">

More Information



</th>
</tr>
<tr>
<td valign="top">

*System Configuration*



</td>
<td valign="top">

*Session timeout*: Set the amount of time before a user session expires if the user doesn't interact with the system.



</td>
<td valign="top">

By default the session timeout is set to 3600 seconds \(1 hour\). The minimum value is 300 seconds, and the maximum value is 43200 seconds.



</td>
</tr>
<tr>
<td valign="top" rowspan="3">

*Data Source Configuration*



</td>
<td valign="top">

*SAP Cloud Platform \(SAP CP\) Account*: Get subaccount information for SAP Datasphere. You need the information to configure the Cloud Connector that SAP Datasphere uses to connect to sources for data flows and model import.



</td>
<td valign="top" rowspan="3">

[Set Up Cloud Connector in SAP Datasphere](Preparing-Connectivity/set-up-cloud-connector-in-sap-datasphere-6de74f7.md)



</td>
</tr>
<tr>
<td valign="top">

*Live Data Sources*: If you want to use SAP BW∕4HANA model import, you need to allow data from your live data connection of type tunnel to securely leave your network.



</td>
</tr>
<tr>
<td valign="top">

*On-premise data sources*: Add location IDs if you have connected multiple Cloud Connector instances to your SAP Datasphere subaccount and you want to offer them for selection when creating connections using a Cloud Connector.



</td>
</tr>
<tr>
<td valign="top" rowspan="2">

*Security*



</td>
<td valign="top">

*Authentication Method*: Select the authentication method used by SAP Datasphere.



</td>
<td valign="top" rowspan="2">

[Enabling a Custom SAML Identity Provider](Managing-Users-and-Roles/enabling-a-custom-saml-identity-provider-9b26536.md)



</td>
</tr>
<tr>
<td valign="top">

*SAML Single Sign-On \(SSO\) Configuration*: Configure SAML SSO if you selected it as authentication method.



</td>
</tr>
<tr>
<td valign="top" rowspan="3">

*App Integration*



</td>
<td valign="top">

*OAuth Clients*: You can use Open Authorization \(OAuth\) protocol to allow third-party applications access.



</td>
<td valign="top" rowspan="3">

[Create OAuth2.0 Clients to Authenticate Against SAP Datasphere](Creating-and-Configuring-Your-Tenant/create-oauth2-0-clients-to-authenticate-against-sap-datasphere-3f92b46.md)



</td>
</tr>
<tr>
<td valign="top">

*Trusted Identity Providers*: If you use the OAuth 2.0 SAML Bearer Assertion workflow, you must add a trusted identity provider.



</td>
</tr>
<tr>
<td valign="top">

*Trusted Origins*: Enter the origins that will be hosting your client application.



</td>
</tr>
<tr>
<td valign="top">

*Notifications*



</td>
<td valign="top">

Make sure that users are notified appropriately about issues in the tenant.



</td>
<td valign="top">

[Configure Notifications](Monitoring-SAP-Datasphere/configure-notifications-4388411.md)



</td>
</tr>
</table>



<a name="loioc6dd05236838466c831170c5cd67e85e__section_eyw_dbb_dpb"/>

## System ** \> ** About

Every user can view information about the software components and versions of your system, in particular:

-   *Version*: Shows the version of the SAP Datasphere tenant.
-   *Platform Version*: Shows the version of the SAP Analytics Cloud components used in SAP Datasphere.

Users with the DW Administrator role can open a *More* section to find more details. They can find outbound and database IP addresses that might be required for allowlists in source systems or databases of SAP Datasphere for example \(see [Finding SAP Datasphere IP addresses](Preparing-Connectivity/finding-sap-datasphere-ip-addresses-0934f7e.md)\).

