<!-- loio788b2721d7c44147afa38038059aade1 -->

# /catalog/assets



<a name="loio788b2721d7c44147afa38038059aade1__section_ltd_w35_t5b"/>

## GET /catalog/assets

Returns an array containing the assets properties belonging to any space to which the signed in business user has access to.

**Request Query Parameters:**The query parameters $select, $filter and $orderby, $count, $top, $skip are supported, see [Parameters](odata-api-reference-b9098c3.md#loiob9098c3a706640189bc1d4eb7d5d5c52__section_request_parameters).

**Sample Request:**GET https://....cloud.sap/api/v1/dwc/catalog/assets



### Successful Response

**Response Code:** 200

**Sample Response Body:**

> ### Sample Code:  
> ```
> {
>   "@odata.context": "https://....cloud.sap/api/v1/dwc/catalog/$metadata#assets/$entity",
>   "value": [  
>     {
>       "name": "CollegeEnrollment",
>       "label": "CollegeEnrollment",
>       "spaceName": "SPACE_A",
>       "assetRelationalMetadataUrl": "https://....cloud.sap/api/v1/dwc/consumption/relational/SPACE_A/CollegeEnrollment/$metadata",
>       "assetRelationalDataUrl": "https://....cloud.sap/api/v1/dwc/consumption/relational/SPACE_A/CollegeEnrollment",
>       "assetAnalyticalMetadataUrl": "https://....cloud.sap/api/v1/dwc/consumption/analytical/SPACE_A/CollegeEnrollment/$metadata",
>       "assetAnalyticalDataUrl": "https://....cloud.sap/api/v1/dwc/consumption/analytical/SPACE_A/CollegeEnrollment",
>       "supportsAnalyticalQueries": true
>     },     {
>       "name": "SAP.TIME.VIEW_DIMENSION_DAY",
>       "label": "Time Dimension - Day",
>       "spaceName": "SPACE_A",
>       "assetRelationalMetadataUrl": "https://....cloud.sap/api/v1/dwc/consumption/relational/SPACE_A/SAP.TIME.VIEW_DIMENSION_DAY/$metadata",
>       "assetRelationalDataUrl": "https://....cloud.sap/api/v1/dwc/consumption/relational/SPACE_A/SAP.TIME.VIEW_DIMENSION_DAY",
>       "assetAnalyticalMetadataUrl": null,
>       "assetAnalyticalDataUrl": null,
>       "supportsAnalyticalQueries": false
>     },
>     {
>       "name": "Currency_View",
>       "label": "Currency View",
>       "spaceName": "SPACE_B",
>       "assetRelationalMetadataUrl": "https://....cloud.sap/api/v1/dwc/consumption/relational/SPACE_B/Currency_View/$metadata",
>       "assetRelationalDataUrl": "https://....cloud.sap/api/v1/dwc/consumption/relational/SPACE_B/Currency_View",
>       "assetAnalyticalMetadataUrl": null,
>       "assetAnalyticalDataUrl": null,
>       "supportsAnalyticalQueries": false
>     }
>   ]
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

