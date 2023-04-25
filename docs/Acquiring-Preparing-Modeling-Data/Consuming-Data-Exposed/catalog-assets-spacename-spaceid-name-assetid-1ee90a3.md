<!-- loio1ee90a3426cd4592857cbb589a9bc42a -->

# /catalog/assets\(spaceName='\{spaceId\}',name='\{assetId\}'\)

Returns the description of the assetId belonging to the spaceId. Contains the link to the consumption service for this asset.



<a name="loio1ee90a3426cd4592857cbb589a9bc42a__section_f3h_vk5_t5b"/>

## GET /catalog/assets\(spaceName='\{spaceId\}',name='\{assetId\}'\)

Returns the properties of the asset specified by spaceId parameter and assetId parameter.

**Request Path Parameters**


<table>
<tr>
<th valign="top">

Property Name



</th>
<th valign="top">

Property Placeholder



</th>
<th valign="top">

Description



</th>
</tr>
<tr>
<td valign="top">

spaceName



</td>
<td valign="top">

spaceId



</td>
<td valign="top">

Technical title of the space, which is used as space ID.



</td>
</tr>
<tr>
<td valign="top">

name



</td>
<td valign="top">

assetId



</td>
<td valign="top">

Technical title of the asset, which is used as asset ID.



</td>
</tr>
</table>

**Request Query Parameters:**The query parameters $select, $filter and $orderby, $count, $top, $skip are supported, see [Parameters](consume-data-via-an-odata-service-7a45360.md#loio7a453609c8694b029493e7d87e0de60a__section_request_parameters).

**Sample Request:**GET https://....cloud.sap/api/v1/dwc/catalog/assets\(space\_name='SPACE\_A', name='CollegeEnrollment'\)



### Successful Response

**Response Code:** 200

**Sample Response Body:**

> ### Sample Code:  
> ```
> {
>   "@odata.context": "https://....cloud.sap/api/v1/dwc/catalog/spaces('SPACE_A')/../$metadata#assets/$entity",
>   "name": "CollegeEnrollment",
>   "label": "CollegeEnrollment",
>   "spaceName": "GKATH",
>   "assetRelationalMetadataUrl": "https://....cloud.sap/api/v1/dwc/consumption/relational/SPACE_A/CollegeEnrollment/$metadata",
>   "assetRelationalDataUrl": "https://....cloud.sap/api/v1/dwc/consumption/relational/SPACE_A/CollegeEnrollment",
>   "assetAnalyticalMetadataUrl": "https://....cloud.sap/api/v1/dwc/consumption/analytical/SPACE_A/CollegeEnrollment/$metadata",
>   "assetAnalyticalDataUrl": "https://....cloud.sap/api/v1/dwc/consumption/analytical/SPACE_A/CollegeEnrollment",
>   "supportsAnalyticalQueries": true
> }
> ```

**Response Body Value Array Properties:**


<table>
<tr>
<th valign="top">

Porperty Name



</th>
<th valign="top">

Description



</th>
</tr>
<tr>
<td valign="top">

name



</td>
<td valign="top">

Technical name of the SAP Datasphere asset



</td>
</tr>
<tr>
<td valign="top">

label



</td>
<td valign="top">

User friendly label of the SAP Datasphere asset



</td>
</tr>
<tr>
<td valign="top">

spaceName



</td>
<td valign="top">

Technical name of the SAP Datasphere space to which the asset belongs to



</td>
</tr>
<tr>
<td valign="top">

assetRelationalMetadataUrl



</td>
<td valign="top">

URL to the asset metadata information for relational \(row-by-row\) access pattern



</td>
</tr>
<tr>
<td valign="top">

assetRelationalDataUrl



</td>
<td valign="top">

URL to the OData service which exposes the asset information for relational \(row-by-row\) access pattern



</td>
</tr>
<tr>
<td valign="top">

assetAnalyticalMetadataUrl



</td>
<td valign="top">

URL to the asset metadata information for analytical \(aggregated\) access pattern. Null if analytical consumption is not available



</td>
</tr>
<tr>
<td valign="top">

assetAnalyticalDataUrl



</td>
<td valign="top">

URL to the OData service which exposes the asset information for analytical \(aggregated\) access pattern. Null if analytical consumption is not available



</td>
</tr>
<tr>
<td valign="top">

supportsAnalyticalQueries



</td>
<td valign="top">

Boolean value which indicates that this asset supports access in analytical consumption mode



</td>
</tr>
</table>

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

