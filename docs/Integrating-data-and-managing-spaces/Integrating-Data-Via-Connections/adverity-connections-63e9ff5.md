<!-- loio63e9ff5825384a03979666dbc3e715f2 -->

# Adverity Connections

Use an *Adverity* connection to extend connectivity beyond SAP Datasphere standard remote connectivity and cover additional data sources that are available with Adverity. Adverity connections are partner connections and use the Open SQL schema to send data to SAP Datasphere.

> ### Note:  
> The connection type is not supported in spaces with storage type *SAP HANA Data Lake Files* \(file spaces\).

This topic contains the following sections:

-   [Supported Features](adverity-connections-63e9ff5.md#loio63e9ff5825384a03979666dbc3e715f2__Adverity_usage)
-   [Prerequisites](adverity-connections-63e9ff5.md#loio63e9ff5825384a03979666dbc3e715f2__Adverity_prerequisites)
-   [Configuring the Partner Connection](adverity-connections-63e9ff5.md#loio63e9ff5825384a03979666dbc3e715f2__Adverity_connection_properties)



<a name="loio63e9ff5825384a03979666dbc3e715f2__Adverity_usage"/>

## Supported Features

You can use the connection to send data to SAP Datasphere via an Open SQL schema and local tables which you can add as a source to views \(see [Connections to Partner Tools](connections-to-partner-tools-55da0fa.md)\).



<a name="loio63e9ff5825384a03979666dbc3e715f2__Adverity_prerequisites"/>

## Prerequisites

In Adverity, an administrator must:

-   prepare a datastream in an Adverity workspace. The datastream must connect to the data source for which you want to create the connection.


In SAP Datasphere, a user with an administrator role must:

-   add the necessary Adverity IP addresses to the IP allowlist \(see [Manage IP Allowlist](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/a3c214514ef94e899459f68f4c1e2a23.html "Add IP addresses to the IP Allowlist by either directly entering them or importing them from a CSV file. You can also export the IP Allowlist.") :arrow_upper_right:\).

    > ### Note:  
    > To get the relevant IP addresses, please contact your Adverity Account Manager or the Adverity Support team.




<a name="loio63e9ff5825384a03979666dbc3e715f2__Adverity_connection_properties"/>

## Configuring the Partner Connection



Wizard step *Configure Partner Connection* shows an embedded Adverity UI. Here, you log on to the regional Adverity server and perform the following steps:

1.  Enter the URL for your regional Adverity server.

2.  Choose *Next*.

    > ### Note:  
    > As a prerequisite to proceed to the next step in the wizard, your browser needs to be enabled to store cookies. This is not the case if you run the browser in incognito mode.

3.  Enter your credentials.

4.  Select the Adverity workspace that you want to use to create the destination to the SAP Datasphere Open SQL schema in.

    > ### Note:  
    > If there is no appropriate workspace available yet, you can create a new one.

5.  Click *Save* to move to the next connection creation wizard step in SAP Datasphere.


For more information, see [Create a Connection](create-a-connection-c216584.md).



<a name="loio63e9ff5825384a03979666dbc3e715f2__section_zqm_gpl_mnb"/>

## What happens in Adverity after you have created the connection

You can now see the destination in the Adverity workspace. There, you can define a prefix for the tables created for this destination to more easily find them later on in the SAP Datasphere Data Builder.

