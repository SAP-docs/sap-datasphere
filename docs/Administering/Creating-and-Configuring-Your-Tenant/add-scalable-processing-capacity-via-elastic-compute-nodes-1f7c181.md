<!-- loio1f7c1811d264462fb0cd03e37da07ad7 -->

# Add Scalable Processing Capacity via Elastic Compute Nodes

If certain views and SAP HANA multi-dimensional services \(MDS\) requests regularly require more resources than are available on your SAP Datasphere tenant, you can now purchase additional on-demand compute and processing memory. You can then create elastic compute nodes, allocate the additional resources to them and schedule them to spin up to handle read peak loads.



<a name="loio1f7c1811d264462fb0cd03e37da07ad7__section_hdj_5g5_3hc"/>

## Prerequisites

To create and manage elastic compute nodes, you must have a global role that grants you the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Spaces* \(`C------M`\) - To create, manage and run elastic compute nodes.
-   *Space Files* \(`-------M`\) - To add spaces and objects to elastic compute nodes.
-   *System Information* \(`-RU-----`\) - To access the tenant settings needed to manage elastic compute nodes.

The *DW Administrator* global role, for example, grants these privileges. For more information, see [Privileges and Permissions](../Managing-Users-and-Roles/privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](../Managing-Users-and-Roles/standard-roles-delivered-with-sap-datasphere-a50a51d.md). 



<a name="loio1f7c1811d264462fb0cd03e37da07ad7__section_btg_vg5_3hc"/>

## Introduction

The elastic compute nodes will take over the read peak loads and support the SAP HANA Cloud database.

> ### Note:  
> Users of SAP Datasphere can consume data via elastic compute nodes only in SAP Analytics Cloud \(via a live connection\) and Microsoft Excel \(via an SAP add-in\).

Using elastic compute nodes can lower the overall cost of ownership: instead of sizing your tenant on the basis of the maximum load, you can use elastic compute nodes to handle short periods of exceptional peak load. For example, you can use an elastic compute node for two months in the year to support end-of-year reporting, or you can use an elastic compute node to cover a specific eight-hour period in the working day.

To identify peak loads, you can look at the following areas in the *System Monitor*: out-of-memory widgets in the *Dashboard* tab, key figures in *Statement Logs*, views used in MDS statements in *Statement Logs*. See [Monitoring SAP Datasphere](../Monitoring-SAP-Datasphere/monitoring-sap-datasphere-28910cd.md).



