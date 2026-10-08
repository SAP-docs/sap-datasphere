<!-- loio5e60730b5b4c45f49e261af6fdaad72b -->

# Controlling Replication Flows via API

You can list and control replication flows and individual replication flow objects via API.

This topic contains the following sections:

-   [Prerequisites](controlling-replication-flows-via-api-5e60730.md#loio5e60730b5b4c45f49e261af6fdaad72b__section_prerequisites)
-   [List Replication Flows](controlling-replication-flows-via-api-5e60730.md#loio5e60730b5b4c45f49e261af6fdaad72b__section_list)
-   [Obtain Replication Flow Run Status](controlling-replication-flows-via-api-5e60730.md#loio5e60730b5b4c45f49e261af6fdaad72b__section_status)
-   [Control Replication Flows and Replication Flow Objects](controlling-replication-flows-via-api-5e60730.md#loio5e60730b5b4c45f49e261af6fdaad72b__section_start_stop)

The API specification is available at the [SAP Business Accelerator Hub](https://api.sap.com/package/sapdatasphere/overview).



<a name="loio5e60730b5b4c45f49e261af6fdaad72b__section_prerequisites"/>

## Prerequisites

To run and manage replication flows, you must have a scoped role granting access to the appropriate spaces with the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Data Warehouse Data Integration* \(`-R------`\) - To view data integration task logs in the *Data Integration Monitor* app.

-   *Data Warehouse Data Integration* \(`--U-----`\) - To manually run data integration tasks.

-   *Data Warehouse Data Integration* \(`----E---`\) - To schedule data integration tasks.

-   *Data Warehouse Data Builder* \(`------S-`\) - To share task chains to other spaces.
-   *User* \(`R-------`\) - To display and add notification recipients from a list of current tenant members, when setting up email notifications.

You must, in addition, obtain access to an appropriate OAuth client:


<table>
<tr>
<th valign="top">

OAuth Purpose

</th>
<th valign="top">

Interactive Usage

</th>
<th valign="top">

Technical User

</th>
</tr>
<tr>
<td valign="top">

Authorization Grant

</td>
<td valign="top">

Authorization Code

Three- Legged \(User-Client-Server\): Manually propagate authorization to another service.

</td>
<td valign="top">

Client Credentials

Two-Legged \(Client-Server\): Service to service communication via APIs.

</td>
</tr>
<tr>
<td valign="top">

Authentication

</td>
<td valign="top">

Manually authenticate to generate the authorization code.

> ### Note:  
> To control a replication flow, you must have authorized consent via the *Authorized Consent Settings* in your profile \(see [Changing SAP Datasphere Settings](https://help.sap.com/viewer/d4f3c5a0bb074d09ae9b42b2b9bd7a08/cloud/en-US/1084796d09464e78870f32cab8584dfc.html "To view and edit your user profile settings, click your user icon in the shell bar and select Settings. You can control various aspects of the user experience of SAP Datasphere and set data privacy and task scheduling consent options.") :arrow_upper_right:\).



</td>
<td valign="top">

None required. The OAuth client contains the necessary credentials and privileges.

</td>
</tr>
<tr>
<td valign="top">

Parameters

</td>
<td valign="top">

-   Client ID
-   Secret
-   Authorization URL
-   Token URL



</td>
<td valign="top">

-   Client ID
-   Secret
-   Token URL



</td>
</tr>
</table>

For more information, see [Create OAuth2.0 Clients to Authenticate Against SAP Datasphere](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/cloud/en-US/3f92b46fe0314e8ba60720e409c219fc.html "Users with an administrator role can create OAuth2.0 clients and provide the client parameters to users who need to connect clients, tools, or apps to SAP Datasphere.") :arrow_upper_right:.



<a name="loio5e60730b5b4c45f49e261af6fdaad72b__section_list"/>

## List Replication Flows

To obtain a list of replication flows in a space, enter the following:

```
GET https://<tenant_id>.api.<regional_host>/api/v1/datasphere/spaces/<space_id>/replicationflows
```



<a name="loio5e60730b5b4c45f49e261af6fdaad72b__section_status"/>

## Obtain Replication Flow Run Status

To obtain the status of a replication flow, enter the following:

```
GET https://<tenant_id>.api.<regional_host>/api/v1/datasphere/spaces/<space_id>/replication-flows/<technical_name>/status
```



<a name="loio5e60730b5b4c45f49e261af6fdaad72b__section_start_stop"/>

## Control Replication Flows and Replication Flow Objects

To start, pause, resume, or stop a replication flow, enter the following, inserting the appropriate *<action\>*:

```
POST https://<tenant_id>.api.<regional_host>/api/v1/datasphere/spaces/<space_id>/replication-flows/<technical_name>/<action>
```

Where *<action\>* is one of:

-   `start`
-   `pause`
-   `resume`
-   `stop`

To pause, resume, or restart an individual replication flow object, enter the following, inserting the appropriate *<action\>*:

```
POST https://<tenant_id>.api.<regional_host>/api/v1/datasphere/spaces/<space_id>/replication-flows/<technical_name>/objects/<object_technical_name><action>
```

Where *<action\>* is one of:

-   `pause-object`
-   `resume-object`
-   `restart-object`

