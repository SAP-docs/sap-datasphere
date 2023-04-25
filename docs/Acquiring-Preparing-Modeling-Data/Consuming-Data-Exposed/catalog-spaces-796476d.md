<!-- loio796476d4548949a4a664e3c5e54be1b6 -->

# /catalog/spaces



<a name="loio796476d4548949a4a664e3c5e54be1b6__section_pfz_qk1_55b"/>

## GET /catalog/spaces

Returns an array containing the spaces properties to which the signed in business user has access to.

**Request Query Parameters:**The query parameters $select, $filter and $orderby, $count, $top, $skip are supported, see [Parameters](consume-data-via-an-odata-service-7a45360.md#loio7a453609c8694b029493e7d87e0de60a__section_request_parameters).

**Sample Request:**GET https://....cloud.sap/api/v1/dwc/catalog/spaces



### Successful Response

**Response Code:** 200

**Sample Response Body:**

> ### Sample Code:  
> ```
> {
>   "@odata.context": "https://....cloud.sap/api/v1/dwc/catalog/$metadata#spaces",
>   "value": [
>     {
>       "name": "SPACE_A",
>       "label": "Space A"
>     },
>     {
>       "name": "SPACE_B",
>       "label": "Space B"
>     },
>     {
>       "name": "BW4_HYB_D2T",
>       "label": "BW4_HYB_D2T"
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

