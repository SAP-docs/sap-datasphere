<!-- loioc6dd05236838466c831170c5cd67e85e -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Administration Apps and Tools

You administer SAP Datasphere using apps and tools in the side navigation area.



<a name="loioc6dd05236838466c831170c5cd67e85e__section_qvk_d5x_25b"/>

## ![](images/Space_Management_a868247.png) \(*Space Management*\)

In the *Space Management*, you can set up, configure, and monitor your spaces, including assigning users to them. For more information, see [Preparing Your Space and Integrating Data](https://help.sap.com/viewer/ac696daa26f0413db39626bc2971e6c2/DEV_CURRENT/en-US/8cb00503395049029055bb7aceafc080.html "Users with a space administrator or integrator role can create connections to source systems and databases and can schedule and monitor data replication and other data integration tasks. Space administrators are, additionally, responsible for controlling user access to their space, creating data access controls to secure data, enabling other forms of data integration, transporting content between tenants, and monitoring and otherwise managing the space.") :arrow_upper_right:.



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

*Live Data Connections \(Tunnel\)*: For SAP BW∕4HANA and SAP S/4HANA model import, you need Cloud Connector. This requires a live data connection of type tunnel.

</td>
<td valign="top">

[Create Live Data Connection of Type Tunnel](Preparing-Connectivity/create-live-data-connection-of-type-tunnel-5d02f11.md) \(SAP BW∕4HANA\)

[Create SAP S/4HANA Live Data Connection of Type Tunnel](Preparing-Connectivity/create-sap-s-4hana-live-data-connection-of-type-tunnel-095dbdf.md) \(SAP S/4HANA\)

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
<td valign="top" rowspan="2">

*Security*

</td>
<td valign="top">

*SSL/TLS Certificates*: Upload server certificates to enable secure SSL/TLS-based connections to certain sources.

</td>
<td valign="top">

[Manage Certificates for Connections](Preparing-Connectivity/manage-certificates-for-connections-46f5467.md)

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
<td valign="top" rowspan="2">

*Audit*

</td>
<td valign="top">

*Audit View Enablement*: Configure a space that gets access to audit views and allows you to display the audit logs in that space.

</td>
<td valign="top">

[Logging Read and Change Actions for Audit](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/266553976e1c4db9aaa28a75e2308b77.html "You can enable audit logs for your space so that read and change actions (policies) are recorded. Administrators can then analyze who performed which action at which point in time.") :arrow_upper_right:

</td>
</tr>
<tr>
<td valign="top">

*Audit Log Deletion*:

</td>
<td valign="top">

[Delete Audit Logs](Monitoring-SAP-Datasphere/delete-audit-logs-589fa42.md)

</td>
</tr>
<tr>
<td valign="top">

*Monitoring*

</td>
<td valign="top">

Control which monitoring data is collected and enable access to pre-configured monitoring views prepared by SAP.

</td>
<td valign="top">

[Configure Monitoring](Monitoring-SAP-Datasphere/configure-monitoring-9cd0691.md)

</td>
</tr>
<tr>
<td valign="top" rowspan="2">

*IP Allowlist*

</td>
<td valign="top">

*Trusted IPs*: Control the range of external public IPv4 addresses that get access to the database of your SAP Datasphere by adding them to an allowlist.

</td>
<td valign="top" rowspan="2">

[Manage IP Allowlist](Preparing-Connectivity/manage-ip-allowlist-a3c2145.md)

</td>
</tr>
<tr>
<td valign="top">

*Trusted Cloud Connector IPs*:

</td>
</tr>
<tr>
<td valign="top">

*Tasks*

</td>
<td valign="top">

Clean-up task logs to reduce storage consumption in your SAP Datasphere tenant.

Also allows you to view a list of users whose authorization consent will expire within a given timeframe, by default, four weeks.

</td>
<td valign="top">

[Delete Task Logs to Reduce Storage Consumption](Monitoring-SAP-Datasphere/delete-task-logs-to-reduce-storage-consumption-c690202.md)

[Check Consent Expirations](Monitoring-SAP-Datasphere/check-consent-expirations-58e4bb2.md)

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
<tr>
<td valign="top">

*SAP BW Bridge*

</td>
<td valign="top">

Create a SAP BW bridge tenant.

</td>
<td valign="top">

[Provisioning the SAP BW Bridge Tenant](https://help.sap.com/viewer/e2d2b48377c14490b55466b5f1872640/DEV_CURRENT/en-US/c356f4ce55744aa09ac2d79a5235c300.html "You can provision SAP BW bridge as an optional feature in SAP Datasphere.") :arrow_upper_right:

</td>
</tr>
<tr>
<td valign="top">

*Business Data Products*

</td>
<td valign="top">

Select spaces to which SAP Business Data Cloud data products from an activated data package can be installed.

</td>
<td valign="top">

[Authorize Spaces to Install SAP Business Data Cloud Data Products](Preparing-Connectivity/authorize-spaces-to-install-sap-business-data-cloud-data-products-67ec785.md)

</td>
</tr>
<tr>
<td valign="top">

*AI Services*

</td>
<td valign="top">

Enable Artificial Intelligence services in SAP Datasphere.

</td>
<td valign="top">

[Enable SAP Business AI for SAP Datasphere](Creating-and-Configuring-Your-Tenant/enable-sap-business-ai-for-sap-datasphere-1b3fe45.md)

</td>
</tr>
<tr>
<td valign="top">

*System Information*

</td>
<td valign="top">

Add a visual tenant type indicator to show all users which system they are using, for example a test or production system.

</td>
<td valign="top">

[Display Your System Information](Creating-and-Configuring-Your-Tenant/display-your-system-information-6bdd798.md)

</td>
</tr>
<tr>
<td valign="top">

*Workload Management*

</td>
<td valign="top">

Set a priority for a particular space when querying the database and set limits to the amount of memory and threads that the space can consume.

</td>
<td valign="top">

[Set Priorities and Statement Limits for Spaces](Creating-Spaces-and-Allocating-Storage/set-priorities-and-statement-limits-for-spaces-d66ac1e.md)

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
<td valign="top" rowspan="2">

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
<td valign="top">

*Allow SAP support user creation*: Let SAP create support users based on incidents.

Support users generated by SAP will be deleted after their validity has expired or after the incident has been closed.

</td>
<td valign="top">

[Request Help from SAP Technical Support](request-help-from-sap-technical-support-831a977.md)

</td>
</tr>
<tr>
<td valign="top">

*Tenant Links*

</td>
<td valign="top">

*Product Switch*: Link an SAP Analytics Cloud tenant to your SAP Datasphere tenant to enable the product switch in the top right of the shell bar, and be able to easily navigate between them.

</td>
<td valign="top">

[Review and Manage Links to SAP Analytics Cloud and SAP Business Data Cloud Tenants](Creating-and-Configuring-Your-Tenant/review-and-manage-links-to-sap-analytics-cloud-and-sap-business-data-cloud-t-40db567.md)

</td>
</tr>
<tr>
<td valign="top" rowspan="3">

*Data Source Configuration*

</td>
<td valign="top">

*SAP BTP Core Account*: Get subaccount information for SAP Datasphere. You need the information to configure the Cloud Connector that SAP Datasphere uses to connect to sources for data flows and model import.

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

-   *Version*: Displays the version of the SAP Datasphere tenant.
-   *Build Date*: Displays the date and time when the current version of the SAP Datasphere tenant was built.
-   *Tenant*: Displays the SAP Datasphere tenant id.
-   *Database*: Displays the id of the SAP Datasphere run-time database.
-   *Platform Version*: Displays the version of the SAP Analytics Cloud components used in SAP Datasphere.

Users with the DW Administrator role can open a *More* section to find more details. They can find outbound and database IP addresses that might be required for allowlists in source systems or databases of SAP Datasphere for example \(see [Finding SAP Datasphere IP addresses](Preparing-Connectivity/finding-sap-datasphere-ip-addresses-0934f7e.md)\). Administrators can also upgrade their SAP HANA database patch version. For details, see [Apply a Patch Upgrade to Your SAP HANA Database](Creating-and-Configuring-Your-Tenant/apply-a-patch-upgrade-to-your-sap-hana-database-489dc3b.md).

