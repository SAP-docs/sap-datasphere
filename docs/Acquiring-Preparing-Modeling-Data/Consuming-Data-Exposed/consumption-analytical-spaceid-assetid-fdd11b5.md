<!-- loiofdd11b5e7a0a42e0965fe09d775d3843 -->

# /consumption/analytical/\{spaceId\}/\{assetId\}



<a name="loiofdd11b5e7a0a42e0965fe09d775d3843__section_dbb_thb_55b"/>

## GET /consumption/analytical/\{spaceId\}/\{assetId\}

Returns the list of models which are available inside the specified assetId. This is the root OData path for consuming data in analytical \(aggregated\) fashion from one asset. It should be used to configure the OData connection in BI tools, like SAP Analytics Cloud.

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

**Sample Request:**GET https://....cloud.sap/api/v1/dwc/consumption/analytical/SPACE\_A/CollegeEnrollment/



### Successful Response

**Response Code:** 200

**Sample Response Body:**

> ### Sample Code:  
> ```
> {
>   "@odata.context": "https://....cloud.sap/api/v1/dwc/consumption/analytical/SPACE_A/$metadata",
>   "@odata.metadataEtag": "W/\"KrzpeilTY54+InLtcF2T9arfdy9X5p7E+2az8mFUg5o=\"",
>   "value": [
>     {
>       "name": "CollegeEnrollment",
>       "url": "CollegeEnrollment"
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

Name of the entity type of OData service



</td>
</tr>
<tr>
<td valign="top">

url



</td>
<td valign="top">

URL path to be appended to the current path in order to access the entity resource route



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

