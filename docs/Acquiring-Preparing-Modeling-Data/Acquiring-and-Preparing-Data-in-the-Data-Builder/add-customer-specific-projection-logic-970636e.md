<!-- loio970636e38ce44a10ab0a8734a284c7c9 -->

# Add Customer-Specific Projection Logic

Use a BAdI implementation to add your own projection logic for replication of CDS view data.



## Context

This topic is relevant for you if the following applies:

-   You want to replicate data from CDS views in an ABAP-based system.

-   You have defined your own additional logic for projections, such as more complex filters, additional lookups, or triggering additional processes, and want to use it in your replication flow.

-   You know how to create a BAdI implementation.


> ### Note:  
> You can only use this feature if it's supported for your source system release. Currently it is available with SAP S/4HANA Cloud 2408.



## Procedure

1.  In the ABAP-based system, create an implementation of the BAdI called BADI\_DHAPE\_RMS\_EVENTS and include your additional logic. For more information, see the BAdI documentation in the system and the sample implementation in class cl\_dhape\_badi\_rms\_events\_exmpl.

2.  Define a value for the BAdI filter EXIT\_NAME. You need this name to find your BAdI implementation in SAP Datasphere.

3.  In SAP Datasphere, either create a new replication flow and enter the necessary data for the source \(including replication objects\), or open the existing replication flow for which you want to add the BAdI implementation.

4.  Select the replication object for which you want to use the additional projection logic.

5.  In the side panel, under *ABAP: Source Settings*, select the name of your BAdI implementation.


