<!-- loioff77002601b1414fa7fb5f01e05a8dcb -->

# /catalog/spaces\('\{spaceId\}'\)



<a name="loioff77002601b1414fa7fb5f01e05a8dcb__section_kxg_dq1_55b"/>

## GET /catalog/spaces\('\{spaceId\}'\)

Returns the properties of the space specified by spaceId parameter.

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
</table>

**Request Query Parameters:**The query parameters $select, $filter and $orderby, $count, $top, $skip are supported, see [Parameters](consume-data-via-an-odata-service-7a45360.md#loio7a453609c8694b029493e7d87e0de60a__section_request_parameters).

**Sample Request:**GET https://....cloud.sap/api/v1/dwc/catalog/spaces\('SPACE\_A'\)



### Successful Response

**Response Code:** 200

**Sample Response Body:**

> ### Sample Code:  
> ```
> {
>   "@odata.context": "https://....cloud.sap/api/v1/dwc/catalog/$metadata#spaces",
>   "name": "SPACE_A",
>   "label": "Space A"
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

Technical name of the SAP Datasphere space



</td>
</tr>
<tr>
<td valign="top">

label



</td>
<td valign="top">

User friendly label of the SAP Datasphere space



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

