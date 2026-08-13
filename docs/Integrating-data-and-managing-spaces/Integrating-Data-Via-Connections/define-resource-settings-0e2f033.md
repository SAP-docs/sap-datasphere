<!-- loio0e2f0330da8d487ba1f8e69e8b52c2d6 -->

# Define Resource Settings

For each resource you can configure the resource settings including pagination, rate limits, and retryable status codes.



## Context

You can define a single set of resource settings for each resource in your custom connection type. More specifically, the following settings are available:

-   If you expect to receive multiple records when calling an endpoint, you can define pagination for each of the resource's response schemas in order to handle the records gracefully.

    Pagination needs to be defined for each response schema and the following pagination methods are available: *Page*, *Offset*, *Next URL* and *Cursor*.

-   Define the following parameters related to rate limit:
    -   *Requests per second*: The maximum number of requests allowed per second. This is the core rate limit and sets the maximum number of requests that the endpoint can handle per second before throttling kicks in.
    -   *Rate limit for response HTTP codes*: Defines which HTTP response codes should count toward the rate limit. For example, you might only want to limit successful responses \(200\) or include errors \(4xx, 5xx\).
    -   *Delay after limit \(in seconds\)*: Specifies how long the system should wait before allowing new requests after the limit is reached.

-   Define the range of error codes returned from activation call failures. Requests returning codes within this range are treated as failed.



## Procedure

1.  In the *Resources Settings* section of the custom connection type dialog, select the resource you wish to edit the resource settings for.

    Under *Endpoints* you can see the defined method and path for the selected resource. From here, you can switch between all the resources you defined under *Resources*, and configure their resource settings accordingly.

2.  Configure the necessary resource settings:


    <table>
    <tr>
    <th valign="top">

    Property
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Pagination*
    
    </td>
    <td valign="top">
    
    Before configuring pagination, you should define the request parameters that will be used for pagination, for example `page` and `pageSize`. Their type must be set to number or integer and they are defined under *Resources* in the *Request Parameters* section. For more information, see step 3 in [Define Resources](define-resources-f22b258.md).

    To apply pagination, choose the response schema you wish to apply pagination to, set the *Pagination* toggle to ON and choose a pagination method.

    There are four supported types of pagination:

    -   *Page*: This pagination method starts with the lowest page number and increments to receive the next batch of records. To use this method, assign the field in the request that will act as the "page" parameter. This field must be of type integer or number. Its initial value is 1 and increases by 1 with each subsequent call, until the response is empty. For example, the "page" field starts at 1, then increases to 2, then 3 and so on.
    -   *Offset*: Offset uses both a page number and page size for pagination. After retrieving the maximum number of records for a given page, the next page is called. To use this method, assign the field in the request that acts as the "offset" parameter. This field must be of type integer or number. Its initial value is 0 and increases by the value in the "page size" field with each subsequent call, until the response is empty. For example, for a "page size " of 10 the offset starts at 0, then increases to 10, then 20 and so on.
    -   *Next URL*: Some systems return a next URL from which to fetch the next set of results in their response. To use this method, assign the field in the response that contains the URL for fetching the next page of results. This field must be of type string.

        > ### Note:  
        > The next URL value must be located in a single response field. Extracting the next URL from an object array within the response is not supported.

    -   *Cursor*: Use cursor-based pagination to retrieve large result sets efficiently. Select the response schema field that contains the cursor ID, choose where to include it in subsequent requests \(for example, as a query parameter\), and specify any parameters that should only be sent in the first request. The absence of a cursor in the response indicates the end of the results.

        > ### Note:  
        > The cursor value must be located in a single response field. Extracting a cursor from an object array within the response is not supported.



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Rate Limit*
    
    </td>
    <td valign="top">
    
    Set the *Rate Limit* toggle to ON and enter the information in the fields:

    -   *Requests per second*: Use the arrows in the selection box to increase or decrease the number of requests per second.
    -   *Rate limit for response HTTP codes*: Enter a n HTTP code manually or choose one from the value help and hit *Enter*.
    -   *Delay after limit \(in seconds\)*: Use the arrows in the selection box to increase or decrease the number of seconds for the cool down period.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Retryable Status Codes*
    
    </td>
    <td valign="top">
    
    Set the *Retryable Status Codes* toggle to ON and enter the minimum and maximum value for each range.

    You can add new ranges by selecting *New Range of Status Codes*.

    Requests returning codes within this range trigger a retry.
    
    </td>
    </tr>
    </table>
    

