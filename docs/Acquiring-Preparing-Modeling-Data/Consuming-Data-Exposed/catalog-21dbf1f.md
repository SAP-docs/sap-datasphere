<!-- loio21dbf1ff57a14380bb4e6718d9b402cb -->

# /catalog

OData root route for listing the OData entities types available in the catalog service.



<a name="loio21dbf1ff57a14380bb4e6718d9b402cb__section_jzm_tvm_t5b"/>

## GET /catalog

Returns list of available OData entities \(spaces and assets\). This is the root URL that should be used when creating OData connections that intent to list catalog definitions.

**Sample Request:**GET https://....cloud.sap/api/v1/dwc/catalog



### Successful Response

**Response Code:** 200

**Sample Response Body:**

> ### Sample Code:  
> ```
> {
>   "@odata.context": "https://....cloud.sap/api/v1/dwc/catalog/$metadata",
>   "@odata.metadataEtag": "W/\"We3BXvSz8NmBywBCybcHOtp8ds+m9Hcm8yd/7g1KSKM=\"",
>   "value": [
>     {
>       "name": "assets",
>       "url": "assets"
>     },
>     {
>       "name": "spaces",
>       "url": "spaces"
>     }
>   ]
> }
> ```

**Response Body Value Array Properties:**


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

**Response Headers:**


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

