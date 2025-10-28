<!-- loioe49785b22ed8454f8ba28edc2dc686c8 -->

# Monitoring Data Provisioning Agent Logs

Access the Data Provisioning Agent adapter framework log and the adapter framework trace log directly in SAP Datasphere.

With the integrated log access, you don’t need to leave SAP Datasphere to monitor the agent and analyze agent issues. Accessing the log data happens via the Data Provisioning Agent File adapter which reads the log files and saves them into the database of SAP Datasphere.

The following logs are available:


<table>
<tr>
<th valign="top">

Log File Name and Location on Data Provisioning Agent Server

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

<code><i class="varname">&lt;DPAgent_root&gt;</i>/log/framework_alert.trc</code>

</td>
<td valign="top">

Data Provisioning Agent adapter framework log. Use this file to monitor data provisioning agent statistics.

</td>
</tr>
<tr>
<td valign="top">

<code><i class="varname">&lt;DPAgent_root&gt;</i>/log/framework.trc</code>

</td>
<td valign="top">

Data Provisioning Agent adapter framework trace log. Use this file to trace and debug data provisioning agent issues.

</td>
</tr>
</table>



<a name="loioe49785b22ed8454f8ba28edc2dc686c8__section_z4g_ww1_xgc"/>

## Procedure

1.  Enable access to the log files for an agent \(see [Enable Access to Data Provisioning Agent Logs](enable-access-to-data-provisioning-agent-logs-9a00dde.md)\).
2.  Review the logs \(see [Review Data Provisioning Agent Logs](review-data-provisioning-agent-logs-0d78ae0.md)\).

