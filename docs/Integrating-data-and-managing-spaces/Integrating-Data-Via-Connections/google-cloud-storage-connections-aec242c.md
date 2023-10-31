<!-- loioaec242c29188408c9ebe1a3ab63ce28b -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Google Cloud Storage Connections

Use the connection to access objects from Google Cloud Storage.



<a name="loioaec242c29188408c9ebe1a3ab63ce28b__GCS_usage"/>

## Using the Connection

The connection type supports the data flow feature.



<a name="loioaec242c29188408c9ebe1a3ab63ce28b__section_nrb_hcc_x4b"/>

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

Choose <span class="SAP-icons"></span> \(Browse\) and select the file from your download location.

</td>
</tr>
</table>



### Features

*Data Flows* are enabled without the need to set any additional connection properties.

