<!-- loio10891192186c4920b08939a7b46adc79 -->

# Load Types and Connections for Your Replication Flows

Understand which load type is supported by your source or target connection.

Replication flows currently support 3 load types: *Initial Only*, *Initial and Delta*, *Delta Only*. For more information, see [Configure a Replication Flow](configure-a-replication-flow-3f5ba0c.md).

Whenever a connection does not support a load type, it is not available as a selection while configuring your replication flow. The following tables display the compatibility between connections and load types.



<a name="loio10891192186c4920b08939a7b46adc79__section_iyh_5dj_rfc"/>

## Source Connections and Supported Load Types


<table>
<tr>
<th valign="top">

Connection

</th>
<th valign="top">

Load Type: Initial Only

</th>
<th valign="top">

Load Type: Initial and Delta

</th>
<th valign="top">

Load Type: Delta Only

</th>
</tr>
<tr>
<td valign="top">

Local table

</td>
<td valign="top">

Supported

</td>
<td valign="top">

Not Supported

</td>
<td valign="top">

Not Supported

</td>
</tr>
<tr>
<td valign="top">

Local table with delta capture

</td>
<td valign="top">

Supported

</td>
<td valign="top">

Supported

</td>
<td valign="top">

Supported

</td>
</tr>
<tr>
<td valign="top">

Local table \(file\)

</td>
<td valign="top">

Not Supported

</td>
<td valign="top">

Not Supported

</td>
<td valign="top">

Not Supported

</td>
</tr>
<tr>
<td valign="top">

Confluent Kafka

</td>
<td valign="top">

Not Supported

</td>
<td valign="top">

Supported

</td>
<td valign="top">

Not Supported

</td>
</tr>
<tr>
<td valign="top">

Cloud Storage Provider

</td>
<td valign="top">

Supported

</td>
<td valign="top">

Not Supported

</td>
<td valign="top">

Not Supported

</td>
</tr>
<tr>
<td valign="top">

ABAP Sources

</td>
<td valign="top">

Supported

</td>
<td valign="top">

Supported \(When property delta enabled is true\)

</td>
<td valign="top">

Supported \(When property delta enabled is true\)

</td>
</tr>
<tr>
<td valign="top">

ABAP Sources without primary key \(only CDS and ODP\)

</td>
<td valign="top">

Supported

</td>
<td valign="top">

Not Supported

</td>
<td valign="top">

Not Supported

</td>
</tr>
<tr>
<td valign="top">

Microsoft SQL Server

</td>
<td valign="top">

Supported

</td>
<td valign="top">

Supported

</td>
<td valign="top">

Supported

</td>
</tr>
<tr>
<td valign="top">

SAP HANA

</td>
<td valign="top">

Supported

</td>
<td valign="top">

Supported

</td>
<td valign="top">

Supported

</td>
</tr>
<tr>
<td valign="top">

AzureSQL

</td>
<td valign="top">

Supported

</td>
<td valign="top">

Supported

</td>
<td valign="top">

Supported

</td>
</tr>
</table>



<a name="loio10891192186c4920b08939a7b46adc79__section_nvr_plj_rfc"/>

## Target Connections and Supported Load Types


<table>
<tr>
<th valign="top">

Connection

</th>
<th valign="top">

Load Type: Initial Only

</th>
<th valign="top">

Load Type: Initial and Delta

</th>
<th valign="top">

Load Type: Delta Only

</th>
</tr>
<tr>
<td valign="top">

Local table

</td>
<td valign="top">

Supported

</td>
<td valign="top">

Supported

</td>
<td valign="top">

Not Supported

</td>
</tr>
<tr>
<td valign="top">

Local table with delta capture

</td>
<td valign="top">

Not Supported

</td>
<td valign="top">

Supported

</td>
<td valign="top">

Not Supported

</td>
</tr>
<tr>
<td valign="top">

Local table \(file\)

</td>
<td valign="top">

Not Supported

</td>
<td valign="top">

Supported

</td>
<td valign="top">

Not Supported

</td>
</tr>
<tr>
<td valign="top">

Kafka

</td>
<td valign="top">

Supported

</td>
<td valign="top">

Supported

</td>
<td valign="top">

Supported

</td>
</tr>
<tr>
<td valign="top">

Confluent Kafka

</td>
<td valign="top">

Supported

</td>
<td valign="top">

Supported

</td>
<td valign="top">

Supported

</td>
</tr>
<tr>
<td valign="top">

Cloud Storage Provider

</td>
<td valign="top">

Supported

</td>
<td valign="top">

Supported

</td>
<td valign="top">

Supported

</td>
</tr>
<tr>
<td valign="top">

Google BigQuery

</td>
<td valign="top">

Supported

</td>
<td valign="top">

Supported

</td>
<td valign="top">

Supported

</td>
</tr>
<tr>
<td valign="top">

SAP HANA

</td>
<td valign="top">

Supported

</td>
<td valign="top">

Supported

</td>
<td valign="top">

Not Supported

</td>
</tr>
<tr>
<td valign="top">

SAP Signavio

</td>
<td valign="top">

Supported

</td>
<td valign="top">

Supported

</td>
<td valign="top">

Not Supported

</td>
</tr>
</table>

