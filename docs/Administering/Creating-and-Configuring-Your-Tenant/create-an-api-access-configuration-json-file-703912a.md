<!-- loio703912acd9864627a05a06a4804d28f9 -->

# Create an API Access Configuration JSON File

Use these parameters in a JSON file to authenticate the service instance in SAP Business Technology Platform.



When configuring the service instance in SAP Business Technology Platform, you can create and upload a JSON configuration file with the required parameters to authenticate the service instance. You can use the JSON file when creating a new instance or recovering a deleted instance.

When creating a new instance, use these parameters in the JSON file:

> ### Sample Code:  
> ```
> 
> {
> “first_name”: “”,
> “last_name”: “”,
> “email”: “”,
> “host_name”: “”
> }
> 
> ```


<table>
<tr>
<th valign="top">

Parameter

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

first\_name

</td>
<td valign="top">

The first name of the authorized user.

</td>
</tr>
<tr>
<td valign="top">

last\_name

</td>
<td valign="top">

The last name of the authorized user.

</td>
</tr>
<tr>
<td valign="top">

email

</td>
<td valign="top">

The email address of the authorized user. For example, john.smith@abcde.com.

</td>
</tr>
<tr>
<td valign="top">

host\_name

</td>
<td valign="top">

The unique name of the host or domain on the network.

</td>
</tr>
</table>

When recovering a deleted tenant, use these parameters in a JSON file:

> ### Sample Code:  
> ```
> 
> {
> “tenantUuid”: “”,
> “access_token”: “”,
> }
> 
> ```


<table>
<tr>
<th valign="top">

Parameter

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

tenantUuid

</td>
<td valign="top">

The tenant universally unique identifier \(UUID\) for the source system.

</td>
</tr>
<tr>
<td valign="top">

access\_token

</td>
<td valign="top">

The OAuth string used to authorize the user.

</td>
</tr>
</table>

See SAP note [3455188](https://me.sap.com/notes/3455188).

