<!-- loio8390855d227547c284bee71eda281459 -->

# Ingestion Spaces and Other SAP Business Data Cloud Spaces

The following special space types may be present in your SAP Datasphere tenant when it is part of an SAP Business Data Cloud formation:


<table>
<tr>
<th valign="top">

Space Type

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

Ingestion

</td>
<td valign="top">

Created automatically when a data product is installed from a connection and named after the connection.

Each data product installed from the connection is created once in the connection's ingestion space and then is shared to the modeling space requesting it. Subsequent installations of the data product in other modeling spaces will simply share the data product in the ingestion space to the requesting space.

Each connection that has one or more data products installed has its own ingestion space. Data products created from SAP BW via the Data Product Generator for SAP Business Data Cloud and any other data products created in your SAP Datasphere tenant all pass through a single "local" ingestion space with a name derived from the SAP Datasphere tenant URL.

Restrictions:

-   Administrators can modify only the space quota.
-   Users assigned to the space with the appropriate roles can monitor the tables .

Storage Type: *SAP HANA Database \(Disk and In-Memory\)*

</td>
</tr>
<tr>
<td valign="top">

SAP BW

</td>
<td valign="top">

Created automatically and populated with data pushed from SAP BW via the Data Product Generator for SAP Business Data Cloud.

Restrictions:

-   Administrators can modify only the space quota.
-   Users assigned to the space with the appropriate roles can monitor the tables and create task chains to automate merge tasks.

Storage Type: *SAP HANA Data Lake Files*

See [Integrating Data from SAP BW and SAP BW∕4HANA with the Data Product Generator for SAP Business Data Cloud](integrating-data-from-sap-bw-and-sap-bw-4hana-with-the-data-product-generator-for-sap-bus-cca4744.md).

</td>
</tr>
<tr>
<td valign="top">

SAP IBP

</td>
<td valign="top">

Created automatically and populated with data pushed from SAP IBP.

Restrictions:

-   Administrators can modify only the space quota.
-   Users assigned to the space with the appropriate roles can monitor the tables and create task chains to automate merge tasks.

Storage Type: *SAP HANA Data Lake Files*

See [Integrating Data From SAP Integrated Business Planning](integrating-data-from-sap-integrated-business-planning-a0b3a6e.md).

</td>
</tr>
</table>

> ### Note:  
> In addition to the ingestion space, further SAP-managed preparation and application spaces containing modeling content are automatically created when an SAP Business Data Cloud intelligent applications is installed:
> 
> -   By default, no users are granted access to these spaces, but a SAP Datasphere administrator can add users to the spaces to review the content.
> -   No user can create any objects in these SAP-managed spaces.
> -   All the delivered content is SAP-managed, read-only, and cannot be modified as it is protected by a namespace \(see [Namespaces](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/7094f24d272c4ae4893b726095ab969e.html "Content managed by SAP and partners and delivered through SAP Business Data Cloud is protected by namespaces. Any object whose technical name is preceded by a namespace and a dot (for example, sap.s4h.Entity) cannot be edited.") :arrow_upper_right:\). For information about copying this content in order to modify it, see [Extending Intelligent Applications](extending-intelligent-applications-3c15868.md).

