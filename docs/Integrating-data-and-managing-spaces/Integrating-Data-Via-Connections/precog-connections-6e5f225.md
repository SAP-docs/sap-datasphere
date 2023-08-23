<!-- loio6e5f2255ae8540d5895dcbef4157b82d -->

# Precog Connections

Extend connectivity beyond SAP Datasphere standard remote connectivity and cover additional data sources that are available with Precog. 

Precog provides connectivity to a variety of data sources, including marketing data sources, databases and others.

When creating a connection to a partner tool, an Open SQL schema is generated in SAP Datasphere. To be able to send data to the Open SQL schema, the IP addresses of the partner tool need to be added to the SAP Datasphere IP allowlist, and during connection creation the partner tool on their side needs to establish a connection to the schema.

For more information, see [Connections to Partner Tools](connections-to-partner-tools-55da0fa.md).



<a name="loio6e5f2255ae8540d5895dcbef4157b82d__section_j1b_byq_spb"/>

## Prerequisites

See: [Prepare Connectivity to Precog](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/ad13c31e33ab498a9d014b766bd5eea2.html "To be able to successfully validate and use a connection to Precog for view building certain preparations have to be made.") :arrow_upper_right: 



<a name="loio6e5f2255ae8540d5895dcbef4157b82d__Precog_usage"/>

## Using the Connection

The connection type supports creating views and entity-relationship models.



<a name="loio6e5f2255ae8540d5895dcbef4157b82d__section_nrb_hcc_x4b"/>

## Configuring Partner Connection



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

