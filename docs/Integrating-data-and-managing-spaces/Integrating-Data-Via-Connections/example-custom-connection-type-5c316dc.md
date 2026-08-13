<!-- loio5c316dcec8ac4f108370ab95741918ee -->

# Example Custom Connection Type

A retailer wants to ingest customer order data from an external e-commerce platform into SAP Datasphere for sales analytics. The API provides order details in JSON format, including nested customer and item information.



## Resource


<table>
<tr>
<td valign="top">

*Resource Name*

</td>
<td valign="top">

Orders

</td>
</tr>
<tr>
<td valign="top">

*Method*

</td>
<td valign="top">

`GET`

</td>
</tr>
<tr>
<td valign="top">

*Path*

</td>
<td valign="top">

`/orders`

</td>
</tr>
<tr>
<td valign="top">

*Description*

</td>
<td valign="top">

Retrieves all customer orders.

</td>
</tr>
<tr>
<td valign="top">

*Authentication*

</td>
<td valign="top">

-   **Type:** OAuth2
-   **Fields:** Client ID, Client Secret, Token URL



</td>
</tr>
<tr>
<td valign="top">

*Request Parameters*

</td>
<td valign="top">

-   `page` \(query, integer, required\): for pagination
-   `pageSize` \(query, integer, optional\): number of records per page



</td>
</tr>
<tr>
<td valign="top">

*Response Schema*

</td>
<td valign="top">

> ### Sample Code:  
> ```
> 
> {
>   "title": "Orders",
>   "type": "object",
>   "properties": {
>     "metadata": {
>       "type": "object",
>       "properties": {
>         "requestId": {
>           "type": "string"
>         },
>         "page": {
>           "type": "integer"
>         },
>         "pageSize": {
>           "type": "integer"
>         },
>         "totalPages": {
>           "type": "integer"
>         }
>       }
>     },
>     "orders": {
>       "type": "array",
>       "items": {
>         "type": "object",
>         "properties": {
>           "order_id": {
>             "type": "string"
>           },
>           "order_date": {
>             "type": "string",
>             "format": "date-time"
>           },
>           "order_status": {
>             "type": "string"
>           },
>           "customer": {
>             "type": "object",
>             "properties": {
>               "customer_id": {
>                 "type": "string"
>               },
>               "email": {
>                 "type": "string"
>               }
>             }
>           },
>           "items": {
>             "type": "array",
>             "items": {
>               "type": "object",
>               "properties": {
>                 "item_id": {
>                   "type": "string"
>                 },
>                 "product_id": {
>                   "type": "string"
>                 },
>                 "quantity": {
>                   "type": "integer"
>                 },
>                 "price": {
>                   "type": "number"
>                 },
>                 "discounts": {
>                   "type": "array",
>                   "items": {
>                     "type": "object",
>                     "properties": {
>                       "discount_id": {
>                         "type": "string"
>                       },
>                       "type": {
>                         "type": "string"
>                       }
>                     }
>                   }
>                 }
>               }
>             }
>           }
>         }
>       }
>     },
>     "customers": {
>       "type": "array",
>       "items": {
>         "type": "object",
>         "properties": {
>           "customer_id": {
>             "type": "string"
>           },
>           "name": {
>             "type": "string"
>           }
>         }
>       }
>     }
>   }
> }
> 
> ```

The schema root is an object that contains multiple arrays and nested structures. Only one array can be selected as a records locator per action.

</td>
</tr>
<tr>
<td valign="top">

*Supported Records Locator Selections*

</td>
<td valign="top">

-   `orders`

    Supported because it is a parent-level array of objects. Each element represents one logical business record \(an order\).

-   `orders.items`

    Supported because it is an array of objects nested within an object \(`orders`\), and is not nested within another array of objects. Selecting this records locator ingests order items directly.

-   `customers`

    Supported because it is a parent-level array of objects at the schema root. Selecting this records locator ingests customers independently from orders.




</td>
</tr>
<tr>
<td valign="top">

*Unsupported Records Locator Selections*

</td>
<td valign="top">

-   `orders.items.discounts`

    Not supported because this array is nested within `items`, which is already an array of objects. Arrays nested within other arrays of objects cannot be selected as records locators.

    However, discount attributes can still be extracted as part of a parent entity by defining keys at the appropriate level.

-   `metadata`

    Not supported because it is an object, not an array.

-   Any attribute of type array containing primitive values.

    Arrays of type string, number, integer, or Boolean are not supported as records locators because they do not represent records that can be mapped to entities.




</td>
</tr>
</table>



## Resource Settings


<table>
<tr>
<td valign="top">

*Pagination*

</td>
<td valign="top">

-   Method: `Page`
-   Parameter: `page`



</td>
</tr>
<tr>
<td valign="top">

*Rate Limit*

</td>
<td valign="top">

-   Requests per second: `5`
-   Delay after limit: `2 seconds`



</td>
</tr>
<tr>
<td valign="top">

*Retryable Status Codes*

</td>
<td valign="top">

Range: `500–599` \(server errors\)

</td>
</tr>
</table>



## Action Definition


<table>
<tr>
<td valign="top">

*Type*

</td>
<td valign="top">

Batch ingestion

The action type is set by default and cannot be changed.

</td>
</tr>
<tr>
<td valign="top">

*Business Name*

</td>
<td valign="top">

Load Orders

</td>
</tr>
<tr>
<td valign="top">

*Technical Name*

</td>
<td valign="top">

load\_orders

</td>
</tr>
<tr>
<td valign="top">

*Associated Resource*

</td>
<td valign="top">

Orders

</td>
</tr>
<tr>
<td valign="top">

*Response Schema*

</td>
<td valign="top">

`Orders` response schema defined above

</td>
</tr>
<tr>
<td valign="top">

*Records Locator*

</td>
<td valign="top">

`orders`

</td>
</tr>
<tr>
<td valign="top">

*Keys*

</td>
<td valign="top">

The following keys are defined to uniquely identify records and enable entity creation:

-   `order_id` \(primary key for Orders entity\)
-   `item_id` \(primary key for Items entity\)

    This can only be defined because `order_id` is already defined as a key.

-   `discount_id` \(primary key for Discounts entity\)

    This can only be defined if keys are defined on Orders, Items, and Discounts.

-   `customer_id` \(primary key for Customers entity\)

If a key is missing on any parent level, the corresponding child entity cannot be created.

</td>
</tr>
</table>



## Entities


<table>
<tr>
<td valign="top">

*Order*

</td>
<td valign="top">

-   Attributes: `order_id`,`order_date`, `order_status`
-   Primary Key: `order_id`



</td>
</tr>
<tr>
<td valign="top">

*Customer*

</td>
<td valign="top">

-   Attributes: `customer_id`,`email`
-   Primary Key: `customer_id`



</td>
</tr>
<tr>
<td valign="top">

*Item*

</td>
<td valign="top">

-   Attributes: `item_id`,`product_id`, `quantity`, `price`, `order_id`
-   Primary Key: `item_id`
-   Foreign Key: `order_id` → Orders



</td>
</tr>
<tr>
<td valign="top">

*Discount*

</td>
<td valign="top">

-   Attributes: `discount_id`,`type`, `item_id`
-   Primary Key: `discount_id`
-   Foreign Key: `item_id` → Items



</td>
</tr>
</table>

