<!-- loio6e5f2255ae8540d5895dcbef4157b82d -->

# Precog Connections

Use a *Precog* connection to extend connectivity beyond SAP Datasphere standard remote connectivity and cover additional data sources that are available with Precog. Precog connections are partner connections and use the Open SQL schema to send data to SAP Datasphere.

> ### Note:  
> The connection type is not supported in spaces with storage type *SAP HANA Data Lake Files* \(file spaces\).

This topic contains the following sections:

-   [Supported Features](precog-connections-6e5f225.md#loio6e5f2255ae8540d5895dcbef4157b82d__Precog_usage)
-   [Prerequisites](precog-connections-6e5f225.md#loio6e5f2255ae8540d5895dcbef4157b82d__Precog_prerequisites)
-   [Configuring the Partner Connection](precog-connections-6e5f225.md#loio6e5f2255ae8540d5895dcbef4157b82d__Precog_connection_properties)



<a name="loio6e5f2255ae8540d5895dcbef4157b82d__Precog_usage"/>

## Supported Features

You can use the connection to send data to SAP Datasphere via an Open SQL schema and local tables which you can add as a source to views \(see [Connections to Partner Tools](connections-to-partner-tools-55da0fa.md)\).



<a name="loio6e5f2255ae8540d5895dcbef4157b82d__Precog_prerequisites"/>

## Prerequisites

Before you can use the connection, the following is required:

-   In Precog, you have added the source for which you want to create the connection.

-   In SAP Datasphere, you have added the necessary Precog IP addresses to the IP allowlist. For more information, see [Manage IP Allowlist](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/a3c214514ef94e899459f68f4c1e2a23.html "Add IP addresses to the IP Allowlist by either directly entering them or importing them from a CSV file. You can also export the IP Allowlist.") :arrow_upper_right:.

    > ### Note:  
    > You can find and copy the relevant IP addresses in the final step of the connection creation wizard.




<a name="loio6e5f2255ae8540d5895dcbef4157b82d__Precog_connection_properties"/>

## Configuring the Partner Connection



Wizard step *Configure partner settings* shows an embedded Precog UI. Here, you log on to the regional Precog server and perform the following steps:

1.  Enter the URL for your regional Precog server.

2.  Choose *Next*.

    > ### Note:  
    > As a prerequisite to proceed to the next step in the wizard, your browser needs to be enabled to store cookies. This is not the case if you run the browser in incognito mode.

3.  Enter your credentials.

4.  Click *Send* to move to the next connection creation wizard step in SAP Datasphere.


For more information, see [Create a Connection](create-a-connection-c216584.md).



<a name="loio6e5f2255ae8540d5895dcbef4157b82d__section_zqm_gpl_mnb"/>

## What happens in Precog after you have created the connection

You can now see the destination with the name of the generated Open SQL schema in Precog and start loading data for the tables available with Precog.

