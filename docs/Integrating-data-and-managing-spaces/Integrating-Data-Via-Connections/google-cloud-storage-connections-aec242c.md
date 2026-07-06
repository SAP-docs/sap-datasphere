<!-- loioaec242c29188408c9ebe1a3ab63ce28b -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Google Cloud Storage Connections

Use the connection to connect to and access objects from Google Cloud Storage.



This topic contains the following sections:

-   [Supported Features](google-cloud-storage-connections-aec242c.md#loioaec242c29188408c9ebe1a3ab63ce28b__GCS_usage)
-   [Configuring Connection Properties](google-cloud-storage-connections-aec242c.md#loioaec242c29188408c9ebe1a3ab63ce28b__connection_properties)



<a name="loioaec242c29188408c9ebe1a3ab63ce28b__GCS_usage"/>

## Supported Features

> ### Note:  
> In file spaces, data flows are not supported.


<table>
<tr>
<th valign="top">

Feature

</th>
<th valign="top">

Additional Information

</th>
</tr>
<tr>
<td valign="top">

Replication Flows

</td>
<td valign="top">

You can use the connection to add source and target objects to a replication flow \(see [Select Source and Target Connections for Replication Flows](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/10891192186c4920b08939a7b46adc79.html "Select the source connection you want to read data from and the target connection you want to replicate data to.") :arrow_upper_right:\).

For more information, see:

-   [Cloud Storage Provider Sources for Replication Flows](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/4d481a2c620f4b52ba65b360299d7719.html "If you use a cloud storage provider as the source for your replication flow, you need to consider additional specifics and conditions.") :arrow_upper_right:

-   [Cloud Storage Provider Targets for Replication Flows](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/43d93a27150a4a218e3df14e3abdf456.html "If you use a cloud storage provider as the target for your replication flow, you need to consider additional specifics and conditions.") :arrow_upper_right:


> ### Note:  
> You can only use a non-SAP target for a replication flow if your admin has assigned capacity units to Premium Outbound Integration. For more information, see [Premium Outbound Integration](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/4e9c6acb5d6a43fa9a6471837399e71c.html "To use a non-SAP target in a replication flow, you need premium outbound integration.") :arrow_upper_right: and [Configure the Size of Your SAP Datasphere Tenant](https://help.sap.com/docs/SAP_DATASPHERE/9f804b8efa8043539289f42f372c4862/33f8ef4ec359409fb75925a68c23ebc3.html).



</td>
</tr>
<tr>
<td valign="top">

Data Flows

</td>
<td valign="top">

You can use the connection to add source objects to a data flow \(see [Creating a Data Flow](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/e30fd1417e954577baae3246ea470c3f.html "Create a data flow to move and transform data in an intuitive graphical interface. You can drag and drop sources from the Source Browser, join them as appropriate, add other operators to remove or create columns, aggregate data, and do Python scripting, before writing the data to the target table.") :arrow_upper_right:\).

</td>
</tr>
</table>



<a name="loioaec242c29188408c9ebe1a3ab63ce28b__connection_properties"/>

## Configuring Connection Properties



### Connection Details


<table>
<tr>
<th valign="top">

Property

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Project* 

</td>
<td valign="top">

Enter the ID of the Google Cloud Storage project to which you want to connect. 

</td>
</tr>
<tr>
<td valign="top">

*Root Path*

</td>
<td valign="top">

\[optional\] Enter the root path name for browsing objects. The value starts with the character slash. For example, `/My Folder/MySubfolder`. 

If you have specified the root path, then any path used with this connection is prefixed with the root path.

</td>
</tr>
</table>



### Credentials


<table>
<tr>
<th valign="top">

Property

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Key* 

</td>
<td valign="top">

Enter the content of the json key file that is used for authentication. 

Choose <span class="SAP-icons-V5"></span> \(Browse\) and select the file from your download location.

</td>
</tr>
</table>



### Features


<table>
<tr>
<th valign="top">

Feature

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Replication Flows*

</td>
<td valign="top">

*Replication Flows* are enabled without the need to set any additional connection properties. 

</td>
</tr>
<tr>
<td valign="top">

*Data Flows*

</td>
<td valign="top">

*Data Flows* are enabled without the need to set any additional connection properties.

> ### Note:  
> In file spaces, data flows are not supported.



</td>
</tr>
</table>

