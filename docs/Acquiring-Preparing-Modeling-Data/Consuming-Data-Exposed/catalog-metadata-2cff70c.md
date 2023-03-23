<!-- loio2cff70cb3e5e428c9f381b07745a547c -->

# /catalog/$metadata



<a name="loio2cff70cb3e5e428c9f381b07745a547c__section_fzb_2h5_t5b"/>

## GET /catalog/$metadata

Returns the metadata in CSDL XML Representation of the service containing the definitions of spaces and assets.

**Sample Request:**GET https://....cloud.sap/api/v1/dwc/catalog/$metadata



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

Value



</th>
</tr>
<tr>
<td valign="top">

Content-Type



</td>
<td valign="top">

application/xml



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

