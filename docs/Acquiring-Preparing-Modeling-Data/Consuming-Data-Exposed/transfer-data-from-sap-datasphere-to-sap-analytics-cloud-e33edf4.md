<!-- loioe33edf495fd740c88a8b90537eea68cb -->

# Transfer Data from SAP Datasphere to SAP Analytics Cloud

The SAP Datasphere Public APIs can be used to replicate fact and master data from SAP Datasphere into SAP Analytics Cloud for planning purposes.



<a name="loioe33edf495fd740c88a8b90537eea68cb__prereq_nfx_g3g_dvb"/>

## Prerequisites

In SAP Datasphere, you have created an OAuth Client. In SAP Analytics Cloud, you have created an OData Service connection. For more information, see [Prerequisites for Consuming Data from SAP Datasphere in SAP Analytics Cloud via the OData Services Connection](prerequisites-for-consuming-data-from-sap-datasphere-in-sap-analytics-cloud-via-the-odata-044fe8e.md).



## Context

By using this API, you can authenticate against SAP Datasphere and get access to its data.



## Procedure

1.  In SAP Analytics Cloud, go to the modeler, and create a new data source of type ODATA Services. For more information, see [OData Services](https://help.sap.com/docs/SAP_ANALYTICS_CLOUD/00f68c2e08b941f081002fd3691d86a7/4c002a6b954d43f18f3712cb10ac3cdc.html?q=planning#concept_rdl_ztv_ktb__section_jtv_13w_ktb).

2.  Select a connection that is pointing to a specific view in SAP Datasphere. For more information, see [Import Data Connection to OData Services](https://help.sap.com/docs/SAP_ANALYTICS_CLOUD/00f68c2e08b941f081002fd3691d86a7/1c1e36eeb99e420aa20ebe6e39af2b65.html).

3.  Select the fields of the view you want to import.

4.  Once the data is uploaded, you can move it into your SAC model.

5.  Map the fields of the imported data to the fields of the model.




<a name="loioe33edf495fd740c88a8b90537eea68cb__result_zqw_vjg_dvb"/>

## Results

Now you can do the planning: In the story on top of your model, enter the plan data and publish it.

