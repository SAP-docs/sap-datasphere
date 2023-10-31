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

You can review the logs in SAP Datasphere after log access has been enabled for the agent in question. We display the actual log files as well as up to ten archived log files that follow the naming convention <code>framework.trc.<i class="varname">&lt;x&gt;</i></code> respectively <code>framework_alert.trc.<i class="varname">&lt;x&gt;</i></code> with *<x\>* being a number between one and ten.

**Related Information**  


[Enable Access to Data Provisioning Agent Logs](enable-access-to-data-provisioning-agent-logs-9a00dde.md "Enable accessing an agent’s log files before you can view them in SAP Datasphere.")

[Review Data Provisioning Agent Logs](review-data-provisioning-agent-logs-0d78ae0.md "Use the logs to monitor the agent and analyze issues with the agent.")

