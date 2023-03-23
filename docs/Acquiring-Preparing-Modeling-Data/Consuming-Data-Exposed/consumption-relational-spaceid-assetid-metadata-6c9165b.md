<!-- loio6c9165b338524f5ba6572c3551b41da6 -->

# /consumption/relational/\{spaceId\}/\{assetId\}/$metadata



<a name="loio6c9165b338524f5ba6572c3551b41da6__section_lb5_tzh_55b"/>

## GET /consumption/relational/\{spaceId\}/\{assetId\}/$metadata

Returns the metadata in CSDL XML Representation of the service containing the definitions of the specified asset.

**Request Path Parameters**


<table>
<tr>
<th valign="top">

Property Name



</th>
<th valign="top">

Description



</th>
</tr>
<tr>
<td valign="top">

spaceId



</td>
<td valign="top">

Technical title of the space, which is used as space ID.



</td>
</tr>
<tr>
<td valign="top">

assetId



</td>
<td valign="top">

Technical title of the asset, which is used as asset ID.



</td>
</tr>
</table>

**Sample Request:**GET https://....cloud.sap/api/v1/dwc/consumption/relational/SPACE\_A/CollegeEnrollment/$metadata



### Successful Response

**Response Code:** 200

**Response Body:** Follows OData v4 metadata specification in the [OData Common Schema Definition Language \(CSDL\) XML Representation](https://docs.oasis-open.org/odata/odata-csdl-xml/v4.01/odata-csdl-xml-v4.01.html)

**Response Headers**


<table>
<tr>
<th valign="top">

Property Name



</th>
<th valign="top">

Description



</th>
</tr>
<tr>
<td valign="top">

Content-Type



</td>
<td valign="top">

application/json



</td>
</tr>
<tr>
<td valign="top">

odata-version



</td>
<td valign="top">

4



</td>
</tr>
</table>

