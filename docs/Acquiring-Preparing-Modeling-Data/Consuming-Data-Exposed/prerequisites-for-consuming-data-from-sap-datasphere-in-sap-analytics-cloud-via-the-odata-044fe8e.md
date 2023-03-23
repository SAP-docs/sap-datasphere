<!-- loio044fe8eaf6d043168ab20923178c1a93 -->

# Prerequisites for Consuming Data from SAP Datasphere in SAP Analytics Cloud via the OData Services Connection

You can access data, which has been searched using the SAP Datasphere OData APIs, via the OData Services Connection in SAP Analytics Cloud.



## Context

To access data from this service via the OData Services Connection in SAP Analytics Cloud, you must follow these steps.



### Restrictions

The data in question should either be replicated \(via remote table replication or data flow in SAP Datasphere\) or there should be a snapshot of the respective view’s data in SAP Datasphere.



## Procedure

1.  Set up an OAuth client in SAP Datasphere. For more information, see [Set up Authentication for the SAP Datasphere Consumption API](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/internal/en-US/68a268723c014510808bde279f4386fa.html "To use the SAP Datasphere Consumption API you must configure a OAuth client to work with your application.") :arrow_upper_right:.

2.  In SAP Analytics Cloud, create an OData Service connection with the following specifications:

    -   Data Service URL: ***https://<your-dwc-tenant-url\>.cloud.sap/api/v1/dwc/consumption/relational/<space-id\>/<asset-id\>/*** 

    -   Authentication Type: *OAuth 2.0 Authorization Code*

    -   OAuth Client ID, Secret, Token URL and Authentication URL: Need to be filled with the OAuth Client information from step 1.


    > ### Note:  
    > Currently, on SAC side, one OData Service connection needs to be set up for each SAP Datasphere view that you want to connect to.




<a name="loio044fe8eaf6d043168ab20923178c1a93__result_nxy_kx2_cvb"/>

## Results

Now that the connection is successfully established, there are multiple options for acquiring the data into SAP Analytics Cloud:

-   Option1: Load data into an existing model
-   Option 2: Create a model from scratch via the OData Service connection

> ### Note:  
> Currently, on SAP Analytics Cloud side, one OData Service connection needs to be set up for each SAP Datasphere view that you want to connect to.

