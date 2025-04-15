<!-- loioa3c214514ef94e899459f68f4c1e2a23 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Manage IP Allowlist

Add IP addresses to the IP Allowlist by either directly entering them or importing them from a CSV file. You can also export the IP Allowlist.

<a name="task_i41_kqg_zdc"/>

<!-- task\_i41\_kqg\_zdc -->

## Add IP Address to IP Allowlist

Clients in your local network need an entry in the appropriate IP allowlist in SAP Datasphere. Cloud Connectors in your local network only require an entry if you want to use them for federation and replication with remote tables from on-premise systems.



<a name="task_i41_kqg_zdc__context_ftc_qsx_clb"/>

## Context

To secure your environment, you can control the range of IPv4 addresses that get access to the database of your SAP Datasphere by adding them to an allowlist.

You need to provide the **external \(public\) IPv4 address \(range\)** of the client directly connecting to the database of SAP Datasphere. This client might be an SAP HANA smart data integration Data Provisioning Agent on a server, a 3rd party ETL or analytics tool, or any other JDBC-client. If you're using a network firewall with a proxy, you need to provide the public IPv4 address of your proxy.

Internet Protocol version 4 addresses \(IPv4 addresses\) have a size of 32 bits and are represented in dot-decimal notation, *192.168.100.1* for example. The external IPv4 address is the address that the internet and computers outside your local network can use to identify your system.

The address can either be a single IPv4 address or a range specified with a Classless Inter-Domain Routing suffix \(CIDR suffix\). An example for a CIDR suffix is **/24** which represents 256 addresses and is typically used for a large local area network \(LAN\). The CIDR notation for the IPv4 address above would be: *192.168.100.1/24* to denote the IP addresses between *192.168.100.0* and *192.168.100.255* \(the leftmost 24 bits of the address in binary notation are fixed\). The external \(public\) IP address \(range\) to enter into the allowlist will be outside of the range *192.168.0.0/16*. You can find more information on Classless Inter-Domain Routing on [Wikipedia](https://en.wikipedia.org/wiki/Classless_Inter-Domain_Routing).

> ### Note:  
> -   Private IP ranges are not relevant to be included in the allowlist.
> 
> -   The number of entries in the allowlist is limited. Once the limit has been reached, you won't be able to add entries. Therefore, please consider which IP addresses should be added and whether the number of allowlist entries can be reduced by using ranges to request as few allowlist entries as possible.



<a name="task_i41_kqg_zdc__steps_b5t_nqg_zdc"/>

## Procedure

1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(*System*\) ** \> ** :wrench: \(*Configuration*\) ** \> *IP Allowlist*.

2.  From the *IP Allowlist* dropdown, select the appropriate list:

    -   *Trusted IPs*: For clients such as an Data Provisioning Agent on a server, 3rd party ETL or analytics tools, or any other JDBC-client
    -   *Trusted Cloud Connector IPs*: For Cloud Connectors that you want to use for federation and replication with remote tables from on-premise systems such as SAP HANA

    The selected list shows all IP addresses that are allowed to connect to the SAP Datasphere database.

3.  Click *Add* to open the *Allow IP Addresses* dialog.

    > ### Note:  
    > Once the number of entries in the allowlist has reached its limit, the *Add* button will be disabled.

4.  In the *CIDR* field of the dialog, either provide a single IPv4 address or a range specified with a CIDR suffix.

    > ### Note:  
    > Please make sure that you provide the **external** IPv4 address of your client respectively proxy when using a network firewall. The IP you enter needs to be your public internet IP.

5.  \[optional\] You can add a description of up to 120 characters to better understand your IP entries.

6.  In the dialog, click *Add* to return to the list.

7.  To save your newly added IP to the allowlist on the database, click *Save* in the pushbutton bar of your list.

    > ### Note:  
    > Updating the allowlist in the database requires some time. To check if your changes have been applied, click *Refresh*.




<a name="task_i41_kqg_zdc__postreq_nsp_xz4_smb"/>

## Next Steps

You can also select and edit an entry from the list if an IP address has changed, or you can delete IPs if they are not required anymore to prevent them from accessing the database of SAP Datasphere. To update the allowlist in the database with any change you made, click *Save* and be reminded that the update in the database might take some time.

<a name="task_yss_tpg_zdc"/>

<!-- task\_yss\_tpg\_zdc -->

## Import or Export IP Allowlist

Importing or exporting IP addresses from SAP Datasphere using a CSV file simplifies the process of managing large lists of IP addresses. This method saves time and reduces the risk of errors compared to manual entry.



<a name="task_yss_tpg_zdc__context_ajh_ypg_zdc"/>

## Context

You could find yourself in a situation where you need many IP addresses added to your current list of IP addresses. Rather than manually entering them, an easier way to move IP addresses is to import or export a list from SAP Datasphere. When importing, the file should be a CSV type using a semicolon, comma, tab, or pipe as the value that separates the IP addresses and their descriptions. The column headings must include *CIDR* \(Classless Inter-Domain Routing\) and *Description*. Here is an example of a basic comma-separated CSV file:


<table>
<tr>
<th valign="top">

CIDR

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

1.1.1.1

</td>
<td valign="top">

Computer1

</td>
</tr>
<tr>
<td valign="top">

1.1.1.1/1

</td>
<td valign="top">

Computer 2

</td>
</tr>
</table>

Here is a more complex CSV:


<table>
<tr>
<th valign="top">

CIDR

</th>
<th valign="top">

From

</th>
<th valign="top">

To

</th>
<th valign="top">

Total Amount

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

3.123.345.56

</td>
<td valign="top">

3.123.345.56

</td>
<td valign="top">

3.123.345.56

</td>
<td valign="top">

3.123.345.56

</td>
<td valign="top">

Computer 1

</td>
</tr>
<tr>
<td valign="top">

155.12.0.0/16

</td>
<td valign="top">

155.12.0.0

</td>
<td valign="top">

155.12.255.255

</td>
<td valign="top">

65534

</td>
<td valign="top">

Range 1

</td>
</tr>
</table>

You can use a file produced in the same or on a different SAP Datasphere tenant.



<a name="task_yss_tpg_zdc__steps_bjh_ypg_zdc"/>

## Procedure

1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(*System*\) ** \> ** :wrench: \(*Configuration*\) ** \> *IP Allowlist*.

2.  From the *IP Allowlist* dropdown, select the appropriate list:

    -   *Trusted IPs*: For clients such as a Data Provisioning Agent on a server, third-party ETL or analytics tools, or any other JDBC-client
    -   *Trusted Cloud Connector IPs*: For Cloud Connectors that you want to use for federation and replication with remote tables from on-premise systems such as SAP HANA

    The selected list shows all IP addresses that are allowed to connect to the SAP Datasphere database.

3.  Choose one of these options:


    <table>
    <tr>
    <th valign="top">

    Option
    
    </th>
    <th valign="top">

    Action
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    **Import IP Allowlist**
    
    </td>
    <td valign="top">
    
    1.  Click <span class="SAP-icons-V5"></span> \(Import IP Allowlist\).
    2.  Click *Select Source File*, and choose the allowlist file. Click *Open*.
    3.  Choose one of the following:
        -   *Append new IPs*: Add the unique IP addresses to the current list or update existing IP descriptions.
        -   *Overwrite existing IPs*: Remove the old IP addresses and add only those addresses in this file.

    4.  Click *Import*.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    **Export IP Allowlist**
    
    </td>
    <td valign="top">
    
    1.  Click <span class="SAP-icons-V5"></span> \(Export IP Allowlist\).
    2.  Choose a comma-separated value \(CSV\) from the list.
    3.  Click *Export*.


    
    </td>
    </tr>
    </table>
    

