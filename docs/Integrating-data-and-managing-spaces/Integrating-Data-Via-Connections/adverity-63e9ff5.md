<!-- loio63e9ff5825384a03979666dbc3e715f2 -->

# Adverity

Extend connectivity beyond SAP Datasphere standard remote connectivity and cover additional data sources that are available with Adverity. 

Adverity provides connectivity to a variety of data sources, including marketing data sources, databases and others.

When creating a connection to a partner tool, an Open SQL schema is generated in SAP Datasphere. To be able to send data to the Open SQL schema, the IP addresses of the partner tool need to be added to the SAP Datasphere IP allowlist, and during connection creation the partner tool on their side needs to establish a connection to the schema.

For more information, see [Connections to Partner Tools](connections-to-partner-tools-55da0fa.md).



<a name="loio63e9ff5825384a03979666dbc3e715f2__section_j1b_byq_spb"/>

## Prerequisites

See: [Prepare Connectivity to Adverity](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/internal/en-US/a37a758eba3340f7a021d7e04af62c4c.html "To be able to successfully validate and use a connection to Adverity for view building certain preparations have to be made.") :arrow_upper_right: 



<a name="loio63e9ff5825384a03979666dbc3e715f2__Adverity_usage"/>

## Using the Connection

The connection type supports creating views and entity-relationship models.



<a name="loio63e9ff5825384a03979666dbc3e715f2__section_nrb_hcc_x4b"/>

## Configuring Partner Connection



Wizard step *Configure partner settings* shows an embedded Adverity UI. Here, you log on to the regional Adverity server and perform the following steps:

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

