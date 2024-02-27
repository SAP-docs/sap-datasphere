<!-- loioa3c214514ef94e899459f68f4c1e2a23 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Add IP address to IP Allowlist

Clients in your local network need an entry in the appropriate IP allowlist in SAP Datasphere. Cloud Connectors in your local network only require an entry if you want to use them for federation and replication with remote tables from on-premise systems.



<a name="loioa3c214514ef94e899459f68f4c1e2a23__context_ftc_qsx_clb"/>

## Context

To secure your environment, you can control the range of IPv4 addresses that get access to the database of your SAP Datasphere by adding them to an allowlist.

You need to provide the **external \(public\) IPv4 address \(range\)** of the client directly connecting to the database of SAP Datasphere. This client might be an SAP HANA smart data integration Data Provisioning Agent on a server, a 3rd party ETL or analytics tool, or any other JDBC-client. If you're using a network firewall with a proxy, you need to provide the public IPv4 address of your proxy.

Internet Protocol version 4 addresses \(IPv4 addresses\) have a size of 32 bits and are represented in dot-decimal notation, *192.168.100.1* for example. The external IPv4 address is the address that the internet and computers outside your local network can use to identify your system.

The address can either be a single IPv4 address or a range specified with a Classless Inter-Domain Routing suffix \(CIDR suffix\). An example for a CIDR suffix is **/24** which represents 256 addresses and is typically used for a large local area network \(LAN\). The CIDR notation for the IPv4 address above would be: *192.168.100.1/24* to denote the IP addresses between *192.168.100.0* and *192.168.100.255* \(the leftmost 24 bits of the address in binary notation are fixed\). The external \(public\) IP address \(range\) to enter into the allowlist will be outside of the range *192.168.0.0/16*. You can find more information on Classless Inter-Domain Routing on [Wikipedia](https://en.wikipedia.org/wiki/Classless_Inter-Domain_Routing).

> ### Note:  
> The number of entries in the allowlist is limited. Once the limit has been reached, you won't be able to add entries. Therefore, please consider which IP addresses should be added and whether the number of allowlist entries can be reduced by using ranges to request as few allowlist entries as possible.



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




<a name="loioa3c214514ef94e899459f68f4c1e2a23__postreq_nsp_xz4_smb"/>

## Next Steps

You can also select and edit an entry from the list if an IP address has changed, or you can delete IPs if they are not required anymore to prevent them from accessing the database of SAP Datasphere. To update the allowlist in the database with any change you made, click *Save* and be reminded that the update in the database might take some time.

