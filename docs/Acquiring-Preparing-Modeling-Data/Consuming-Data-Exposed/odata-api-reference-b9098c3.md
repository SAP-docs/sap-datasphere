<!-- loiob9098c3a706640189bc1d4eb7d5d5c52 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# OData API Reference

The SAP Datasphere OData API provides a catalog service and a service for consuming data.

This topic contains the following sections:

-   [Getting Started with the SAP Datasphere OData APIs](odata-api-reference-b9098c3.md#loiob9098c3a706640189bc1d4eb7d5d5c52__section_getting_started)
-   [Catalog Service](odata-api-reference-b9098c3.md#loiob9098c3a706640189bc1d4eb7d5d5c52__section_catalog_service)
-   [Consumption Service](odata-api-reference-b9098c3.md#loiob9098c3a706640189bc1d4eb7d5d5c52__section_consumption_service)
-   [Parameters](odata-api-reference-b9098c3.md#loiob9098c3a706640189bc1d4eb7d5d5c52__section_request_parameters)
-   [Pagination](odata-api-reference-b9098c3.md#loiob9098c3a706640189bc1d4eb7d5d5c52__section_pagination)
-   [OData Annotation Limitations](odata-api-reference-b9098c3.md#loiob9098c3a706640189bc1d4eb7d5d5c52__section_limitations)
-   [API Rate Limiting](odata-api-reference-b9098c3.md#loiob9098c3a706640189bc1d4eb7d5d5c52__section_rate_limiting)



<a name="loiob9098c3a706640189bc1d4eb7d5d5c52__section_getting_started"/>

## Getting Started with the SAP Datasphere OData APIs

You can use the SAP Datasphere OData API to browse views and consume their data. You must be a member of the space that is exposing the view, and the view must be exposed for consumption \(see [Exposing a View For Consumption](../Modeling-Data-in-the-Data-Builder/exposing-a-view-for-consumption-40ec77e.md)\). The API uses OData v4.0 \(see [OData Version 4.0](http://docs.oasis-open.org/odata/odata/v4.0/odata-v4.0-part1-protocol.html)\) and only the query parameters listed below are supported.

Compose your OData request based on your SAP Datasphere tenant URL in the following format:

```
https://<tenant_url>.cloud.sap/api/v1/dwc/<request>
```

or:

```
https://<tenant_url>.cloud.sap/dwaas-core/odata/v4/<request>
```

For example, to list all the spaces you have access to, use:

```
https://<tenant_url>.cloud.sap/api/v1/dwc/catalog/spaces
```

To list all the views you have access to, use:

```
https://<tenant_url>.cloud.sap/api/v1/dwc/catalog/assets
```

Requests return, by default, the first 10 results and for retrieving more or other pages you should make use of the $top and $skip parameters.

The API specification is available at the [SAP API Business Hub](https://api.sap.com/package/sapdatawarehousecloud/overview).



<a name="loiob9098c3a706640189bc1d4eb7d5d5c52__section_catalog_service"/>

## Catalog Service

Lets you list and query all accessible spaces and views that are exposed for consumption.


<table>
<tr>
<th valign="top">

Endpoint



</th>
<th valign="top">

Description



</th>
</tr>
<tr>
<td valign="top">

/catalog



</td>
<td valign="top">

Returns list of available OData entities \(spaces and assets\). This is the root URL that should be used when creating OData connections that intent to list catalog definitions.



</td>
</tr>
<tr>
<td valign="top">

/catalog/$metadata



</td>
<td valign="top">

Returns the metadata of the service containing the definitions of spaces and assets.



</td>
</tr>
<tr>
<td valign="top">

/catalog/spaces



</td>
<td valign="top">

Returns an array containing the spaces structure the business user has access to.



</td>
</tr>
<tr>
<td valign="top">

/catalog/spaces\('\{spaceId\}'\)



</td>
<td valign="top">

Returns the description of the ***spaceId***.



</td>
</tr>
<tr>
<td valign="top">

/catalog/spaces\('\{spaceId\}'\)/assets



</td>
<td valign="top">

Returns the list of assets in a given ***spaceId***.



</td>
</tr>
<tr>
<td valign="top">

/catalog/spaces\('\{spaceId\}'\)/assets\('\{assetId\}'\)



</td>
<td valign="top">

Returns the description of the ***assetId*** belonging to the spaceId. Contains the link to the consumption service for this asset.



</td>
</tr>
<tr>
<td valign="top">

/catalog/assets



</td>
<td valign="top">

Returns the list of assets that are exposed for consumption in the spaces the user has access to.



</td>
</tr>
<tr>
<td valign="top">

/catalog/assets\(space\_name='\{spaceId\}',name='assetId'\)



</td>
<td valign="top">

Returns the description of the ***assetId*** belonging to the ***spaceId***. Contains the link to the consumption service for this asset.



</td>
</tr>
</table>



<a name="loiob9098c3a706640189bc1d4eb7d5d5c52__section_consumption_service"/>

## Consumption Service

Lets you consume the data exposed by a view either as plain relational tables or as analytical models. Rich metadata definitions about the entity are exposed allowing you to derive detailed information about each column, dimension or measure.

When performing a relational request, all results will be returned as if they were row-by-row, without filters or aggregations. You can use query parameters, such as $select, $filter and $orderby, $count, $top, $skip, that will allow the client to request a specific set of properties for each entity. The usage of those properties should follow the OData version 4.0 standard. For more information, see [OData version 4.0 standard](http://docs.oasis-open.org/odata/odata/v4.0/odata-v4.0-part1-protocol.html).

> ### Note:  
> Views containing input parameters \(see [Create an Input Parameter](../Acquiring-and-Preparing-Data-in-the-Data-Builder/create-an-input-parameter-53fa99a.md)\) are not supported.


<table>
<tr>
<th valign="top">

Endpoint



</th>
<th valign="top">

Description



</th>
</tr>
<tr>
<td valign="top">

/consumption/relational/\{spaceId\}/\{assetId\}



</td>
<td valign="top">

Returns the list of models which are available inside the specified ***assetId***. This is the root OData path for consuming data row by row from one asset. It should be used to configure the OData connection in BI tools, like SAP Analytics Cloud.



</td>
</tr>
<tr>
<td valign="top">

/consumption/relational/\{spaceId\}/\{assetId\}/$metadata



</td>
<td valign="top">

Returns the metadata of the service containing the definitions of spaces and assets.



</td>
</tr>
<tr>
<td valign="top">

/consumption/relational/\{spaceId\}/\{assetId\}/\{assetId\}



</td>
<td valign="top">

Returns the ResultSet in a relational fashion. Supports all $ operands from OData.



</td>
</tr>
<tr>
<td valign="top">

/consumption/analytical/\{spaceId\}/\{assetId\}



</td>
<td valign="top">

Returns the list of models which are available inside the specified assetId. This is the root OData path for consuming data in analytical fashion from one asset. It should be used to configure the OData connection in BI tools, like SAP Analytics Cloud.



</td>
</tr>
<tr>
<td valign="top">

/consumption/analytical/\{spaceId\}/\{assetId\}/$metadata



</td>
<td valign="top">

Returns the metadata of the service containing the definitions of spaces and assets.



</td>
</tr>
<tr>
<td valign="top">

/consumption/analytical/\{spaceId\}/\{assetId\}/\{assetId\}



</td>
<td valign="top">

Returns the ResultSet in an analytical fashion. Supports $select, $filter, $orderby and $count operands from OData.



</td>
</tr>
</table>



<a name="loiob9098c3a706640189bc1d4eb7d5d5c52__section_request_parameters"/>

## Parameters


<table>
<tr>
<th valign="top">

Parameter



</th>
<th valign="top">

Description



</th>
</tr>
<tr>
<td valign="top">

$select



</td>
<td valign="top">

Requests that the service returns only the specified properties. For more information, see [OData Version 4.0](http://docs.oasis-open.org/odata/odata/v4.0/errata03/os/complete/part1-protocol/odata-v4.0-errata03-os-part1-protocol-complete.html#_System_Query_Option_3).



</td>
</tr>
<tr>
<td valign="top">

$filter



</td>
<td valign="top">

Request the service to restrict returned results according to the provided criteria:

-   `eq` - Equals
-   `ne` - Not equal
-   `gt` - Greater Than
-   `ge` - Greater Than or Equal To
-   `lt` - Less Than
-   `le` - Less Than or Equal To
-   `and` - And
-   `or` - Or
-   `not` - Not
-   `()` - Grouping



</td>
</tr>
<tr>
<td valign="top">

$orderby



</td>
<td valign="top">

Specifies the order in which items are returned from the service. For more information, see [OData Version 4.0](http://docs.oasis-open.org/odata/odata/v4.0/errata03/os/complete/part1-protocol/odata-v4.0-errata03-os-part1-protocol-complete.html#_The_$orderby_System).



</td>
</tr>
<tr>
<td valign="top">

$top



</td>
<td valign="top">

Specifies a value N that limits the number of items returned from a collection. For more information, see [OData Version 4.0](http://docs.oasis-open.org/odata/odata/v4.0/errata03/os/complete/part1-protocol/odata-v4.0-errata03-os-part1-protocol-complete.html#_The_$top_System_1).



</td>
</tr>
<tr>
<td valign="top">

$skip



</td>
<td valign="top">

Specifies a value N that excludes the first N items of the selected collection. For more information, see [OData Version 4.0](http://docs.oasis-open.org/odata/odata/v4.0/errata03/os/complete/part1-protocol/odata-v4.0-errata03-os-part1-protocol-complete.html#_The_$skip_System).



</td>
</tr>
</table>



<a name="loiob9098c3a706640189bc1d4eb7d5d5c52__section_pagination"/>

## Pagination

Client side pagination can be performed via the usage of the $top and $skip query parameters. Combining both parameters allow the API consumer to retrieve an specific batch of results from the consuming OData Service.

In some cases, the full response cannot be returned in one page due to the page size query option or the response size limit enforced by the service.

In this case, a next link annotated by the ***@odata.nextLink*** is provided at the end of the response, which allows you to move to the next page. There will be no next link when client side pagination is applied or at the final page.


<table>
<tr>
<th valign="top">

Request Service



</th>
<th valign="top">

Default Page Size



</th>
</tr>
<tr>
<td valign="top">

Catalog



</td>
<td valign="top">

500 records



</td>
</tr>
<tr>
<td valign="top">

Consumption



</td>
<td valign="top">

Varies according to the amount of fields in the model. Maximum document size of 20MB.



</td>
</tr>
</table>



<a name="loiob9098c3a706640189bc1d4eb7d5d5c52__section_limitations"/>

## OData Annotation Limitations

Annotations in the metadata of a specific service might restrict the query options. Some of the CDS data types are partially or not supported by the SAP Datasphere Consumption API.


<table>
<tr>
<th valign="top">

Data Type



</th>
<th valign="top">

Writable



</th>
<th valign="top">

Sortable



</th>
<th valign="top">

Filterable



</th>
<th valign="top">

Overwritten EDM Type



</th>
</tr>
<tr>
<td valign="top">

cds.hana.ST\_GEOMETRY



</td>
<td valign="top">

:x:



</td>
<td valign="top">

:x:



</td>
<td valign="top">

:heavy_check_mark:



</td>
<td valign="top">

Edm.String



</td>
</tr>
<tr>
<td valign="top">

cds.hana.ST\_POINT



</td>
<td valign="top">

:x:



</td>
<td valign="top">

:x:



</td>
<td valign="top">

:heavy_check_mark:



</td>
<td valign="top">

Edm.String



</td>
</tr>
<tr>
<td valign="top">

cds.Binary



</td>
<td valign="top">

 



</td>
<td valign="top">

:x:



</td>
<td valign="top">

:x:



</td>
<td valign="top">

\-



</td>
</tr>
<tr>
<td valign="top">

cds.LargeBinary



</td>
<td valign="top">

:x:



</td>
<td valign="top">

:x:



</td>
<td valign="top">

:x:



</td>
<td valign="top">

\-



</td>
</tr>
<tr>
<td valign="top">

cds.hana.BINARY



</td>
<td valign="top">

:x:



</td>
<td valign="top">

:x:



</td>
<td valign="top">

:x:



</td>
<td valign="top">

\-



</td>
</tr>
<tr>
<td valign="top">

cds.LargeString



</td>
<td valign="top">

:heavy_check_mark:



</td>
<td valign="top">

:x:



</td>
<td valign="top">

:heavy_check_mark:



</td>
<td valign="top">

\-



</td>
</tr>
<tr>
<td valign="top">

cds.UUID



</td>
<td valign="top">

:heavy_check_mark:



</td>
<td valign="top">

:heavy_check_mark:



</td>
<td valign="top">

:x:



</td>
<td valign="top">

\-



</td>
</tr>
</table>



<a name="loiob9098c3a706640189bc1d4eb7d5d5c52__section_rate_limiting"/>

## API Rate Limiting

Authenticated requests are associated either with the authenticated username, tenant ID or with the OAuth client ID. Unauthenticated requests are associated with the originating IP address, and not the user.

When the rate limit is exceeded, the client receives the ***HTTP 429 Too Many Requests*** response status code.

