<!-- loioaa3627f987d04b5f95fec1c45083dde9 -->

# Allow Your Space to Write to Your HDI Container

To allow data flows in your SAP Datasphere space to use tables in your HDI container as targets, you must set the appropriate roles and add the container to your space.



## Procedure

1.  Define the roles `DWC_WRITE_ROLE` and `DWC_WRITE_ROLE³` \(with grant option\) in your HDI container \(see [Prepare Your HDI Project for Exchanging Data with Your Space](prepare-your-hdi-project-for-exchanging-data-with-you-a94e163.md)\).

2.  Add the container to your space \(see [Add an HDI Container and Access its Objects in Your Space](add-an-hdi-container-and-access-its-objects-in-your-s-5d55da5.md)\).

3.  Create a data flow and select a table in the container as the target for your data flow \(see [Add or Create a Target Table](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/0fa780568975458dbd90d11d1d81f2d9.html "Add a target table to write data to. You can only have one target table in a data flow.") :arrow_upper_right:\).


