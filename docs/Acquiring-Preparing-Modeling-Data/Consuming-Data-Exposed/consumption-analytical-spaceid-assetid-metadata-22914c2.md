<!-- loio22914c214b8449de9f984a7129a141c6 -->

# /consumption/analytical/\{spaceId\}/\{assetId\}/$metadata



<a name="loio22914c214b8449de9f984a7129a141c6__section_o2v_p5h_55b"/>

## GET /consumption/analytical/\{spaceId\}/\{assetId\}/$metadata

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

**Sample Request:**GET https://....cloud.sap/api/v1/dwc/consumption/analytical/SPACE\_A/CollegeEnrollment/$metadata



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

