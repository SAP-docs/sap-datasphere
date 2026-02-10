<!-- loio24aebd7222ab4d3386c5c280f61baa6e -->

# Space Types

While a user with an administrator role can create spaces in your SAP Datasphere tenant, certain other spaces can be created automatically to support specific features.

This table lists the various types of spaces that can be created:


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

SAP Datasphere

</td>
<td valign="top">

The default space type, created by an administrator for standard modeling tasks.

No restrictions:

-   Administrators can create, modify, and delete the space freely.
-   Users assigned to the space with the appropriate roles can create, edit, and delete objects freely.

Storage Type:

-   *SAP HANA Database \(Disk and In-Memory\)* - See [Create a Space](create-a-space-bbd41b8.md).
-   *SAP HANA Data Lake Files* - See [Create a File Space to Load Data in the Object Store](create-a-file-space-to-load-data-in-the-object-store-9474446.md).



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

See [Integrating Data from SAP BW and SAP BW∕4HANA with the Data Product Generator for SAP Business Data Cloud](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/cca4744c85b14788babe7cb6b77c9973.html "In the SAP Datasphere component of SAP Business Data Cloud, you can work with data and objects received from SAP BW and SAP BW∕4HANA systems via the Data Product Generator for SAP Business Data Cloud.") :arrow_upper_right:.

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

See [Integrating Data From SAP Integrated Business Planning](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/a0b3a6e9c3f94f0bb06b81722fc5cb2b.html "Data from SAP Integrated Business Planning can be pushed to SAP Datasphere object store to be used for further modeling activities.") :arrow_upper_right:.

</td>
</tr>
<tr>
<td valign="top">

SAP BW Bridge

</td>
<td valign="top">

Created automatically and populated with data pushed from SAP BW bridge.

Restrictions:

-   Administrators can modify only the space quota.
-   Users assigned to the space with the appropriate roles can monitor the tables .

Storage Type: *SAP HANA Database \(Disk and In-Memory\)*

See [Getting Started With SAP Datasphere, SAP BW Bridge](https://help.sap.com/viewer/ecce5bb08ae24ed089497fc00c2320d8/cloud/en-US/32b4861ce7d94ebd9f5abd854691582f.html "SAP Datasphere, SAP BW bridge enables you to use SAP BW functionality in the public cloud, and to import SAP BW bridge data models into SAP Datasphere.") :arrow_upper_right:.

</td>
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

See [Ingestion Spaces and Other SAP Business Data Cloud Spaces](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/8390855d227547c284bee71eda281459.html "") :arrow_upper_right:.

</td>
</tr>
</table>

