<!-- loio0cf11ede362b4f4186c459097464943d -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Stop a Running Statement With a Database Analysis User

Using a database analysis user, you can stop a statement that is currently running.

You may for example want to stop a statement that has been running for a long time and is causing performance issues.

You can only stop a statement that has been run by space users, analysis users, user group users and Data Provisioning Agent users.

In SAP HANA Database Explorer, run a database procedure using the following syntax:

```
CALL "DWC_GLOBAL"."STOP_RUNNING_STATEMENT"('<ACTION>', '<CONNECTION_ID>')
```

Complete the parameters as follows:


<table>
<tr>
<th valign="top">

Parameter

</th>
<th valign="top">

Value

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top" rowspan="2">

ACTION

</td>
<td valign="top">

CANCEL

</td>
<td valign="top">

Enter CANCEL to run the statement ALTER SYSTEM CANCEL \[WORK IN\] SESSION \(see [ALTER SYSTEM CANCEL \[WORK IN\] SESSION Statement \(System Management\)](https://help.sap.com/docs/HANA_CLOUD_DATABASE/c1d3f60099654ecfb3fe36ac93c121bb/20d0eb287519101498c4ecb8114cab17.html) in the *SAP HANA Cloud, SAP HANA Database SQL Reference Guide*.\)

</td>
</tr>
<tr>
<td valign="top">

DISCONNECT

</td>
<td valign="top">

Enter DISCONNECT to run the statement ALTER SYSTEM DISCONNECT SESSION \(see [ALTER SYSTEM DISCONNECT SESSION Statement \(System Management\)](https://help.sap.com/docs/HANA_CLOUD_DATABASE/c1d3f60099654ecfb3fe36ac93c121bb/20d1524e751910148706e0aab4063a0f.html) in the *SAP HANA Cloud, SAP HANA Database SQL Reference Guide*.\)

</td>
</tr>
<tr>
<td valign="top">

CONNECTION\_ID

</td>
<td valign="top">

 

</td>
<td valign="top">

Enter the ID of the connection to the database, which corresponds to the statement that you want to stop.

> ### Note:  
> You can find the connection ID in <span class="FPA-icons-V3"></span> \(*System Monitor*\)** \> *Statement Logs*, then the column *Connection ID*.



</td>
</tr>
</table>

For more information on database explorer, [Getting Started With the SAP HANA Database Explorer](https://help.sap.com/docs/SAP_HANA_COCKPIT/e8d0ddfb84094942a9f90288cd6c05d3/7fa981c8f1b44196b243faeb4afb5793.html).

