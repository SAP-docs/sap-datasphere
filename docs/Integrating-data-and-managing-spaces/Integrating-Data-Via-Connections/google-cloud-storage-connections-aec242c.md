<!-- loioaec242c29188408c9ebe1a3ab63ce28b -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Google Cloud Storage Connections

Use the connection to connect to and access objects from Google Cloud Storage.



This topic contains the following sections:

-   [Supported Features](google-cloud-storage-connections-aec242c.md#loioaec242c29188408c9ebe1a3ab63ce28b__GCS_usage)
-   [Configuring Connection Properties](google-cloud-storage-connections-aec242c.md#loioaec242c29188408c9ebe1a3ab63ce28b__connection_properties)



<a name="loioaec242c29188408c9ebe1a3ab63ce28b__GCS_usage"/>

## Supported Features


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

Data Flows

</td>
<td valign="top">

You can use the connection to add source objects to a data flow.

</td>
</tr>
<tr>
<td valign="top">

Replication Flows

</td>
<td valign="top">

You can use the connection to add source and target objects to a replication flow.

For more information, see:

-   [Using a Cloud Storage Provider As the Source](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/4d481a2c620f4b52ba65b360299d7719.html "If you use a cloud storage provider as the source for your replication flow, you need to consider additional specifics and conditions.") :arrow_upper_right:

-   [Using a Cloud Storage Provider As the Target](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/43d93a27150a4a218e3df14e3abdf456.html "If you use a cloud storage provider as the target for your replication flow, you need to consider additional specifics and conditions.") :arrow_upper_right:


> ### Note:  
> You can only use a non-SAP target for a replication flow if your admin has assigned capacity units to Premium Outbound Integration. For more information, see [Configure the Size of Your SAP Datasphere Tenant](https://help.sap.com/docs/SAP_DATASPHERE/9f804b8efa8043539289f42f372c4862/33f8ef4ec359409fb75925a68c23ebc3.html).



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

*Data Flows*

</td>
<td valign="top">

*Data Flows* are enabled without the need to set any additional connection properties. 

</td>
</tr>
<tr>
<td valign="top">

*Replication Flows*

</td>
<td valign="top">

*Replication Flows* are enabled without the need to set any additional connection properties. 

</td>
</tr>
</table>

