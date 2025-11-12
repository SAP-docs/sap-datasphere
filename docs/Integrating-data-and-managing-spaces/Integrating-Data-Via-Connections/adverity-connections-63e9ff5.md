<!-- loio63e9ff5825384a03979666dbc3e715f2 -->

# Adverity Connections

Extend connectivity beyond SAP Datasphere standard remote connectivity and cover additional data sources that are available with Adverity. 

> ### Note:  
> The connection type is not supported in spaces with storage type *SAP HANA Data Lake Files* \(file spaces\).

This topic contains the following sections:

-   -   [Context](adverity-connections-63e9ff5.md#loio63e9ff5825384a03979666dbc3e715f2__Adverity_context)
-   [Supported Features](adverity-connections-63e9ff5.md#loio63e9ff5825384a03979666dbc3e715f2__Adverity_usage)
-   [Configuring the Partner Connection](adverity-connections-63e9ff5.md#loio63e9ff5825384a03979666dbc3e715f2__Adverity_connection_properties)



<a name="loio63e9ff5825384a03979666dbc3e715f2__Adverity_context"/>

## Context

Adverity connections are partner connections and use the Open SQL schema to send data to SAP Datasphere. For more information, see [Connections to Partner Tools](connections-to-partner-tools-55da0fa.md).



<a name="loio63e9ff5825384a03979666dbc3e715f2__Adverity_usage"/>

## Supported Features

The connection type supports creating views and entity-relationship models.



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

