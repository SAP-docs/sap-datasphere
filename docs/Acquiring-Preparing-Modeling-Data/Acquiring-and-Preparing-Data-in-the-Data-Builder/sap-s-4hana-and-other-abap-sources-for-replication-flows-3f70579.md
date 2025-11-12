<!-- loio3f70579c92434f4f88471bba2bd70893 -->

# SAP S/4HANA and Other ABAP Sources for Replication Flows

Before replicating data from your SAP S/4HANA or other ABAP source, you must ensure that all the appropriate release and security notes for your source system version are applied.

This topic contains the following sections:

-   [Prerequisites](sap-s-4hana-and-other-abap-sources-for-replication-flows-3f70579.md#loio3f70579c92434f4f88471bba2bd70893__section_prerequisites)
-   [Use Note Analyzer to Verify Your ABAP Source System Compliance](sap-s-4hana-and-other-abap-sources-for-replication-flows-3f70579.md#loio3f70579c92434f4f88471bba2bd70893__section_note_analyzer)
-   [ABAP Replication Source Object Types](sap-s-4hana-and-other-abap-sources-for-replication-flows-3f70579.md#loio3f70579c92434f4f88471bba2bd70893__section_source_objects)



<a name="loio3f70579c92434f4f88471bba2bd70893__section_prerequisites"/>

## Prerequisites

These prerequisites are valid for replication flows with sources of the following connection types:

-   [SAP ABAP Connections](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/a75c1aacf951449ba3b740c7e46da3a9.html "Use an SAP ABAP connection to access data from SAP ABAP on-premise systems through RFC or to access data from cloud source systems such as SAP S/4HANA Cloud through Web Socket RFC.") :arrow_upper_right:
-   [SAP S/4HANA Cloud Connections](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/a98e5ffdf47c44d9a845dca01a18bd82.html "Use an SAP S/4HANA Cloud connection to access or import extraction-enabled ABAP Core Data Services views (ABAP CDS views) from SAP S/4HANA Cloud.") :arrow_upper_right:
-   [SAP S/4HANA On-Premise Connections](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/a49a1e3cc50f4af89711d8306bdd8f26.html "Use an SAP S/4HANA On-Premise connection to access data from SAP S/4HANA on-premise systems.") :arrow_upper_right:

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

DMIS 2025 SP00

</td>
<td valign="top">

SAP Note [3667132](https://me.sap.com/notes/3667132)

</td>
<td valign="top">

SAP Note [3100673](https://me.sap.com/notes/3100673)

</td>
<td valign="top">

SAP Note [3658010](https://me.sap.com/notes/3658010)

</td>
</tr>
<tr>
<td valign="top">

DMIS 2018 SP14 /

DMIS 2020 SP10

</td>
<td valign="top">

[3658528](https://me.sap.com/notes/3658528)

</td>
<td valign="top">

[3100673](https://me.sap.com/notes/3100673)

</td>
<td valign="top">

[3657956](https://me.sap.com/notes/3657956)

</td>
</tr>
<tr>
<td valign="top">

DMIS 2018 SP13 /

DMIS 2020 SP09

</td>
<td valign="top">

[3487365](https://me.sap.com/notes/3487365)

</td>
<td valign="top">

[3100673](https://me.sap.com/notes/3100673)

</td>
<td valign="top">

[3487355](https://me.sap.com/notes/3487355)

</td>
</tr>
<tr>
<td valign="top">

DMIS 2018 SP12 /

DMIS 2020 SP08

</td>
<td valign="top">

[3438949](https://me.sap.com/notes/3438949)

</td>
<td valign="top">

[3100673](https://me.sap.com/notes/3100673)

</td>
<td valign="top">

[3438948](https://me.sap.com/notes/3438948)

</td>
</tr>
<tr>
<td valign="top">

DMIS 2018 SP11 /

DMIS 2020 SP07

</td>
<td valign="top">

[3383618](https://me.sap.com/notes/3383618)

</td>
<td valign="top">

[3100673](https://me.sap.com/notes/3100673)

</td>
<td valign="top">

[3383627](https://me.sap.com/notes/3383627)

</td>
</tr>
<tr>
<td valign="top">

DMIS 2018 SP10 /

DMIS 2020 SP06

</td>
<td valign="top">

[3362214](https://me.sap.com/notes/3362214)

</td>
<td valign="top">

[3100673](https://me.sap.com/notes/3100673)

</td>
<td valign="top">

[3314851](https://me.sap.com/notes/3314851)

</td>
</tr>
<tr>
<td valign="top">

DMIS 2011 SP28

</td>
<td valign="top">

[3487273](https://me.sap.com/notes/3487273)

</td>
<td valign="top">

[3100673](https://me.sap.com/notes/3100673)

</td>
<td valign="top">

[3487320](https://me.sap.com/notes/3487320)

</td>
</tr>
<tr>
<td valign="top">

DMIS 2011 SP27

</td>
<td valign="top">

[3439004](https://me.sap.com/notes/3439004)

</td>
<td valign="top">

[3100673](https://me.sap.com/notes/3100673)

</td>
<td valign="top">

[3438985](https://me.sap.com/notes/3438985)

</td>
</tr>
<tr>
<td valign="top">

DMIS 2011 SP26

</td>
<td valign="top">

[3383613](https://me.sap.com/notes/3383613)

</td>
<td valign="top">

[3100673](https://me.sap.com/notes/3100673)

</td>
<td valign="top">

[3383514](https://me.sap.com/notes/3383514)

</td>
</tr>
<tr>
<td valign="top">

DMIS 2011 SP25

</td>
<td valign="top">

[3362249](https://me.sap.com/notes/3362249)

</td>
<td valign="top">

[3100673](https://me.sap.com/notes/3100673)

</td>
<td valign="top">

[3324231](https://me.sap.com/notes/3324231)

</td>
</tr>
<tr>
<td valign="top">

DMIS 2011 SP24

</td>
<td valign="top">

[3254934](https://me.sap.com/notes/3254934)

</td>
<td valign="top">

[3100673](https://me.sap.com/notes/3100673)

</td>
<td valign="top">

[3048369](https://me.sap.com/notes/3048369)

</td>
</tr>
</table>

To connect to other SAP systems including SAP Business Warehouse \(BW\) using ODP \(in combination with the DMIS add-on\), review the DMIS-related information above along with the information provided in SAP Note [2890171](https://me.sap.com/notes/2890171) and SAP Note [2775549](https://me.sap.com/notes/2775549).



<a name="loio3f70579c92434f4f88471bba2bd70893__section_note_analyzer"/>

## Use Note Analyzer to Verify Your ABAP Source System Compliance

You can use *Note Analyzer* to review your ABAP system and ensure that all relevant notes are applied to it:

1.  Run *Note Analyzer* on your ABAP system to verify the status of all required notes.

    *Note Analyzer* returns a list of required notes with an implementation status for each

2.  If any notes are shown as not implemented, show the list to your ABAP administrator and ask her to apply them.
3.  Re-run *Note Analyzer* to ensure that all notes are now implemented.

    > ### Note:  
    > When requesting support, you must include the *Note Analyzer* output to your support ticket.


For more information about *Note Analyzer*, see [Implement and Run SAP Note Analyzer](https://help.sap.com/docs/SUPPORT_CONTENT/datasphere/4457678727.html#HowtocheckrelevantnotecorrectionsinOnpremiseABAPbasedsystemsforDataFlowsandReplicationFlows-ImplementandrunSAPNoteAnalyzer) in the *Expert Content*.



<a name="loio3f70579c92434f4f88471bba2bd70893__section_source_objects"/>

## ABAP Replication Source Object Types

The source object types that are available to you depend on your ABAP system version:


<table>
<tr>
<th valign="top">

Source Object Type

</th>
<th valign="top">

Source System Versions

</th>
<th valign="top">

*Expert Content* Troubleshooting

</th>
</tr>
<tr>
<td valign="top">

CDS Views

</td>
<td valign="top">

-   SAP S/4HANA 1909 and higher



</td>
<td valign="top">

-   [CDS views from S/4HANA On-Premise](https://help.sap.com/docs/SUPPORT_CONTENT/datasphere/4445249362.html)



</td>
</tr>
<tr>
<td valign="top">

SLT Tables

</td>
<td valign="top">

-   DMIS 2020 SP03 and higher
-   DMIS 2018 SP06 and higher



</td>
<td valign="top">

-   [ABAP Tables from On-Premise](https://help.sap.com/docs/SUPPORT_CONTENT/datasphere/4477053691.html)



</td>
</tr>
<tr>
<td valign="top">

ODP Tables

</td>
<td valign="top">

-   SAP S/4HANA 1909 and higher
-   DMIS 2020 SP04 and higher
-   DMIS 2018 SP08 and higher
-   DMIS 2011 SP23 and higher



</td>
<td valign="top">

-   [ODP DataSource with BW Context from On-Premise](https://help.sap.com/docs/SUPPORT_CONTENT/datasphere/4518286134.html)
-   [ODP SAPI Datasources from On-Premise](https://help.sap.com/docs/SUPPORT_CONTENT/datasphere/4518621673.html)



</td>
</tr>
</table>



<a name="loio3f70579c92434f4f88471bba2bd70893__section_e51_fwd_dhc"/>

## Replicating data from source objects without a primary key

If certain conditions are met, you can use objects that do not have a primary key as the source for a replication flow.

This applies to the following types of *source objects*:

-   CDS views

-   ODP artifacts


> ### Caution:  
> If you are replicating source data from Microsoft SQL Server, you can't replicate objects without primary keys.

The objects must have load type *Initial Only*. \(Delta loading is not supported.\)

**Existing tables** can be used as **targets** if they have a column \_\_load\_package\_id \(as explained below\). **Local tables** can only be used as targets if delta capturing is **not** enabled.

For some targets, the system automatically adds a **technical target column**. For SAP HANA and SAP HANA Cloud targets, this column is called "\_\_load\_package\_id" and has data type binary\(256\). For other targets, it is called "\_\_load\_record\_id" and has data type string\(44\). This column provides a unique identifier for each record, which serves as a replacement for the primary key in duplicate handling and for other technical purposes. On the *Projections* tab, this column is always shown at the end and in read only mode. You can't rename it, remove or modify its data type, or reorder it.

The technical target column is not added to a target table for Apache Kafka, as it is sent in a message header. This means it is sent separately from other \(non-technical\) columns placed in a message body.

> ### Note:  
> Multiple replications \(for example due to restarting or undeploying and redeploying a replication flow\) result in different \_\_load\_record\_id values for the same source record.

