<!-- loio4c367de075a44ad7b7a6db576a4a9c82 -->

# SAP Signavio Connections

Use the connection to securely integrate SAP systems such as SAP S/4HANA on-premise with SAP Signavio using replication flows for efficient and scalable data replication to SAP Signavio Process Intelligence.



This topic contains the following sections:

-   [Supported Features](sap-signavio-connections-4c367de.md#loio4c367de075a44ad7b7a6db576a4a9c82__Signavio_usage)
-   [Prerequisites](sap-signavio-connections-4c367de.md#loio4c367de075a44ad7b7a6db576a4a9c82__Signavio_prerequisites)
-   [Configuring Connection Properties](sap-signavio-connections-4c367de.md#loio4c367de075a44ad7b7a6db576a4a9c82__Signavio_connection_properties)



<a name="loio4c367de075a44ad7b7a6db576a4a9c82__Signavio_usage"/>

## Supported Features


<table>
<tr>
<th valign="top">

Feature

</th>
<th valign="top">

Additional Information

</th>
</tr>
<tr>
<td valign="top">

Replication Flows

</td>
<td valign="top">

You can use the connection to add target objects to a replication flow.

For more information, see [SAP Signavio Targets for Replication Flows](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/b8f5e28d34b44d71a52f6265e4fc245f.html "If you use SAP Signavio as the target for your replication flow, you need to consider the following additional specifics and conditions.") :arrow_upper_right:.

</td>
</tr>
</table>



<a name="loio4c367de075a44ad7b7a6db576a4a9c82__Signavio_prerequisites"/>

## Prerequisites

> ### Note:  
> SAP Signavio connections require a 1:1 mapping between the SAP Datasphere tenant and an SAP Signavio tenant. When using several connections in different spaces, the connections must all point to the same SAP Signavio endpoint.



### SAP Datasphere

1.  Create a scoped role based on the *DW Integrator* template \(privilege *Data Warehouse Data Integration* with *Read* permission is required\), and add the space in which the SAP Signavio connection will be created to the scoped role.

    For more information, see [Create a Scoped Role to Assign Privileges to Users in Spaces](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/b5c4e0b6c462414783ebbfc053815521.html "A scoped role inherits a set of scoped privileges from a standard or custom role and grants these privileges to users for use in the assigned spaces.") :arrow_upper_right:.

2.  Create the connection to the source of the replication flow \(SAP S/4HANA, for example\) in the same space which you will use to create the connection to SAP Signavio.

    For more information, see [Create a Connection](create-a-connection-c216584.md).

3.  Create an OAuth 2.0 client with a technical user purpose and assign the scoped integrator role that has been created before.

    The OAuth client is required to set up the required 1:1 mapping between the SAP Datasphere tenant and the SAP Signavio tenant.

    When creating the OAuth client, make a note of the following information that is required to register the OAuth client in SAP Signavio:

    -   OAuth Client ID
    -   OAuth Client Secret

        > ### Note:  
        > Immediately copy the secret. Once you close the OAuth creation dialog, the secret is no longer available, and you will need to create a new client.

    -   Service Root \(URL root of the *App Integration* page where you create the OAuth client\)
    -   OAuth2SAML Token URL

    For more information, see [Create an OAuth2.0 Client with a Technical User Purpose](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/88b13468fc3c4ebd972bcb8faa6cafbf.html "Users with an administrator role can create OAuth2.0 clients with a technical user purpose and provide the client parameters to users, giving them limited privileges and permissions when connecting clients, tools, or apps to SAP Datasphere.") :arrow_upper_right:.




### SAP Signavio

1.  Register the OAuth 2.0 client by creating a connection with connection type *SAP Datasphere Replication Flow*.

    For more information, see [Synchronizing Data with SAP Datasphere Replication Flow](https://help.sap.com/docs/signavio-process-intelligence/user-guide/synchronizing-data-with-sap-datasphere-replication-flow) in the *SAP Signavio Process Intelligence* documentation.




<a name="loio4c367de075a44ad7b7a6db576a4a9c82__Signavio_connection_properties"/>

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

*URL*  

</td>
<td valign="top">

Enter the API gateway endpoint of the SAP Signavio tenant. 

For more information about SAP Signavio URLs, see [Regions, IP Addresses, and URLs](https://help.sap.com/docs/signavio-process-intelligence/user-guide/regions-ip-addresses-and-urls) in the *SAP Signavio Process Intelligence* documentation.

</td>
</tr>
</table>



### Features


<table>
<tr>
<th valign="top">

Feature

</th>
<th valign="top">

Description

</th>
</tr>
<tr>
<td valign="top">

*Replication Flows*

</td>
<td valign="top">

*Replication Flows* are enabled without the need to set any additional connection properties. 

</td>
</tr>
</table>

