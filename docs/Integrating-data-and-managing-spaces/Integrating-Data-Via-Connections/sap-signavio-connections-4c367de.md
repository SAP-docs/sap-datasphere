<!-- loio4c367de075a44ad7b7a6db576a4a9c82 -->

# SAP Signavio Connections

Use the connection to securely integrate SAP systems such as SAP S/4HANA on-premise with SAP Signavio using replication flows for efficient and scalable data replication to SAP Signavio Process Intelligence.



This topic contains the following sections:

-   [Supported Features](sap-signavio-connections-4c367de.md#loio4c367de075a44ad7b7a6db576a4a9c82__Signavio_usage)
-   [Configuring Connection Properties](sap-signavio-connections-4c367de.md#loio4c367de075a44ad7b7a6db576a4a9c82__Signavio_connection_properties)

For more information about the integration and the required prerequisites to create a valid connection in SAP Datasphere, see:

-   [Synchronizing Data with SAP Datasphere Replication Flow](https://help.sap.com/docs/signavio-process-intelligence/user-guide/synchronizing-data-with-sap-datasphere-replication-flow) in the *SAP Signavio Process Intelligence* documentation
-   [Prepare Connectivity to SAP Signavio](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/9bde7712a1ef47a18a292484284e2c0a.html "To be able to successfully validate and use a connection to SAP Signavio, certain preparations have to be made.") :arrow_upper_right:

> ### Note:  
> SAP Signavio connections require a 1:1 mapping between the SAP Datasphere tenant and an SAP Signavio tenant. When using several connections in different spaces, the connections must all point to the same SAP Signavio endpoint.



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

For more information, see [SAP Signavio Targets](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/b8f5e28d34b44d71a52f6265e4fc245f.html "If you use SAP Signavio as the target for your replication flow, you need to consider the following additional specifics and conditions.") :arrow_upper_right:.

</td>
</tr>
</table>



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

