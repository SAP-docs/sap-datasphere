<!-- loio3f70579c92434f4f88471bba2bd70893 -->

# SAP S/4HANA and Other ABAP Sources for Replication Flows

Before replicating data from your SAP S/4HANA or other ABAP source, you must ensure that all the appropriate release and security notes for your source system version are applied.



<a name="loio3f70579c92434f4f88471bba2bd70893__section_cwy_11q_psb"/>

## Prerequisites

These prerequisites are valid for replication flows with sources of the following connection types:

-   [SAP ABAP Connections](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/a75c1aacf951449ba3b740c7e46da3a9.html "Use an SAP ABAP connection to access data from SAP ABAP on-premise systems through RFC or to access data from cloud source systems such as SAP S/4HANA Cloud through Web Socket RFC.") :arrow_upper_right:
-   [SAP S/4HANA Cloud Connections](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/a98e5ffdf47c44d9a845dca01a18bd82.html "Use an SAP S/4HANA Cloud connection to access or import extraction-enabled ABAP Core Data Services views (ABAP CDS views) from SAP S/4HANA Cloud.") :arrow_upper_right:
-   [SAP S/4HANA On-Premise Connections](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/a49a1e3cc50f4af89711d8306bdd8f26.html "Use an SAP S/4HANA On-Premise connection to access data from SAP S/4HANA on-premise systems.") :arrow_upper_right:

Use this table to consult the appropriate required release versions and security settings for your source system version. You should also review the appropriate SAP Landscape Transformation Replication Server \(SLT\) note, if you are using this technology for your integration.

> ### Note:  
> Whenever possible, install and use the latest versions of the relevant software for your use case.


<table>
<tr>
<th valign="top">

System Version

</th>
<th valign="top">

Required Release Notes

</th>
<th valign="top">

Required Security Settings

</th>
<th valign="top">

SAP Landscape Transformation Replication Server \(SLT\) Notes

</th>
</tr>
<tr>
<td valign="top">

SAP S/4HANA 2025

</td>
<td valign="top">

SAP Note [3383644](https://me.sap.com/notes/3383644)

</td>
<td valign="top">

SAP Note [3100673](https://me.sap.com/notes/3100673)

</td>
<td valign="top">

SAP Note [3383657](https://me.sap.com/notes/3383657)

</td>
</tr>
<tr>
<td valign="top">

SAP S/4HANA 2023

</td>
<td valign="top">

SAP Note [3254953](https://me.sap.com/notes/3254953)

</td>
<td valign="top">

SAP Note [3100673](https://me.sap.com/notes/3100673)

</td>
<td valign="top">

SAP Note [3254917](https://me.sap.com/notes/3254917)

</td>
</tr>
<tr>
<td valign="top">

SAP S/4HANA 2022

</td>
<td valign="top">

SAP Note [3130827](https://me.sap.com/notes/3130827)

</td>
<td valign="top">

SAP Note [3100673](https://me.sap.com/notes/3100673)

</td>
<td valign="top">

SAP Note [3130834](https://me.sap.com/notes/3130834)

</td>
</tr>
<tr>
<td valign="top">

SAP S/4HANA 2021

</td>
<td valign="top">

SAP Note [3085579](https://me.sap.com/notes/3085579)

</td>
<td valign="top">

SAP Note [3100673](https://me.sap.com/notes/3100673) \(and implement TCI 3115128\)

</td>
<td valign="top">

Not Supported

</td>
</tr>
<tr>
<td valign="top">

SAP S/4HANA 2020

</td>
<td valign="top">

SAP Note [2943599](https://me.sap.com/notes/2943599)

</td>
<td valign="top">

SAP Note [3100673](https://me.sap.com/notes/3100673) \(and implement TCI 3105880\)

</td>
<td valign="top">

Not Supported

</td>
</tr>
<tr>
<td valign="top">

SAP S/4HANA 1909

</td>
<td valign="top">

SAP Note [2830276](https://me.sap.com/notes/2830276)

</td>
<td valign="top">

SAP Note [3100673](https://me.sap.com/notes/3100673) \(and implement TCI 3105890\)

</td>
<td valign="top">

Not Supported

</td>
</tr>
</table>

For older SAP systems \(in combination with the DMIS add-on\), use this table to consult the appropriate notes:


<table>
<tr>
<th valign="top">

System Version

</th>
<th valign="top">

Required Release Notes

</th>
<th valign="top">

Required Security Settings

</th>
<th valign="top">

SAP Landscape Transformation Replication Server \(SLT\) Notes

</th>
</tr>
<tr>
<td valign="top">

DMIS 2020

</td>
<td valign="top">

SAP Note [3156672](https://me.sap.com/notes/3156672)

</td>
<td valign="top">

SAP Note [3100673](https://me.sap.com/notes/3100673)

> ### Note:  
> For DMIS 2020 SP02 and lower, upgrade to SP04.



</td>
<td valign="top">

SAP Note [3151041](https://me.sap.com/notes/3151041)

</td>
</tr>
<tr>
<td valign="top">

DMIS 2018

</td>
<td valign="top">

SAP Note [3156672](https://me.sap.com/notes/3156672)

</td>
<td valign="top">

-   DMIS 2018 SP07 and higher: SAP Note [3100673](https://me.sap.com/notes/3100673)
-   DMIS 2018 SP06: SAP Note [3100673](https://me.sap.com/notes/3100673)\(and implement TCI 3110660\)

> ### Note:  
> For DMIS 2018 SP02 and lower, upgrade to the latest available DMIS 2018 SP.



</td>
<td valign="top">

SAP Note [3151041](https://me.sap.com/notes/3151041)

</td>
</tr>
<tr>
<td valign="top">

DMIS 2011

</td>
<td valign="top">

SAP Note [3156649](https://me.sap.com/notes/3156649)

</td>
<td valign="top">

-   DMIS 2011 SP22 and higher: SAP Note [3100673](https://me.sap.com/notes/3100673)

-   DMIS 2011 SP20 and SP21: SAP Note [2981615](https://me.sap.com/notes/2981615)


> ### Note:  
> For DMIS 2011 SP19 and lower, upgrade to the latest available DMIS 2011 SP.



</td>
<td valign="top">

SAP Note [3151142](https://me.sap.com/notes/3151142)

</td>
</tr>
</table>

To connect to older SAP systems including SAP Business Warehouse \(BW\) systems using ODP \(in combination with the DMIS add-on\), review the DMIS-related information above along with the information provided in SAP Note [2890171](https://me.sap.com/notes/2890171) and SAP Note [2775549](https://me.sap.com/notes/2775549).

