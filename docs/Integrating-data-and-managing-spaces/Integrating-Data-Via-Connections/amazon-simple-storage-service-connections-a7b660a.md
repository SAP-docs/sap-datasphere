<!-- loioa7b660a0a4ef4a4fbee57b44f5b2147d -->

# Amazon Simple Storage Service Connections

Use an *Amazon Simple Storage Service* connection to access data from objects in Amazon S3. 



<a name="loioa7b660a0a4ef4a4fbee57b44f5b2147d__SSS_usage"/>

## Using the Connection

The connection type supports the data flow feature.



<a name="loioa7b660a0a4ef4a4fbee57b44f5b2147d__section_nrb_hcc_x4b"/>

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

 *Endpoint* 



</td>
<td valign="top">

 Enter the endpoint URL of the Amazon S3 server. The protocol prefix is not required. For example, `s3.amazonaws.com`. 



</td>
</tr>
<tr>
<td valign="top">

 *Protocol* 



</td>
<td valign="top">

 Select the protocol. The default value is *HTTPS*. The value that you provide overwrites the value from the endpoint, if already set. 



</td>
</tr>
<tr>
<td valign="top">

 *Root Path* 



</td>
<td valign="top">

 Enter the optional root path name for browsing objects. The value starts with the character slash. For example,`/My Folder/MySubfolder`. 

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

 *Access Key* 



</td>
<td valign="top">

 Enter the access key ID of the user that the application must use to authenticate. 



</td>
</tr>
<tr>
<td valign="top">

 *Secret Key* 



</td>
<td valign="top">

 Enter the secret access key of the user that the application must use to authenticate. 



</td>
</tr>
</table>



### Features

*Data Flows* are enabled without the need to set any additional connection properties.

