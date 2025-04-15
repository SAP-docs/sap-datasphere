<!-- loio58588fb42777455695f66b6ec8980ef3 -->

# Publishing Data to SAP Datasphere

You can publish data from SAP BW/4HANA and SAP BW to the SAP Datasphere object store.



<a name="loio58588fb42777455695f66b6ec8980ef3__prereq_smm_vbb_t2c"/>

## Prerequisites

The data product generator for SAP Business Data Cloud is supported for the releases SAP BW/4HANA 2023 SP0 onwards, SAP BW/4HANA 2021 SP4 onwards, and SAP BW in SAP NetWeaver 7.50 SP24 onwards.

For the configuration of the data product generator for SAP Business Data Cloud, see SAP Note [3590400](https://me.sap.com/notes/3590400).

The DW Administrator should create at least one of the following types of scoped roles and assign users to them:

-   DW Space Administrator: to manage users and do monitoring
-   DW Integrator: to monitor data integration in the space
-   DW Modeler: to share the tables to other spaces for consumption



## Context

As data providers, you can use ODP-based sources like DataStore objects, CompositeProviders, Queries as InfoProviders, InfoObjects, InfoCubes, and MultiProviders.

The data product generator for SAP Business Data Cloud accesses the Data Subscriptions Framework, which provides the data from the SAP BW models. The data gets extracted into an SAP Datasphere local table \(file\). You can then incorporate these data into SAP Datasphere models.

You can use a process chain to extract the data or you can run the extraction directly. The data gets then extracted in a specific format and is written into SAP HANA tables. The SAP HANA tables are connected to the local table \(file\).

For SAP BW/4HANA, you can create and maintain the subscription in the SAP BW Cockpit. For SAP NetWeaver, you can create and maintain the subscription in your SAP NetWeaver backend system \(SAP GUI\).



## Procedure

1.  In the SAP BW Cockpit, go to the section *Data Product Generator for SAP Business Data Cloud*. Open the App *Data Subscriptions*.

    > ### Note:  
    > For SAP NetWeaver 7.50:
    > 
    > In your SAP BW system, go to transaction RSDPS to open the Data Subscriptions. Here, you can create and maintain subscription just like in the SAP BW Cockpit.

2.  Choose *Create* to create a new subscription. Enter a description.

3.  Select CompositeProviders, DataStore objects, Queries as InfoProviders, InfoObjects, InfoCubes, or MultiProviders as source. Save your entries.

4.  You can now define the properties of your subscription on the tab pages *Settings* and *Projections*:

    ****


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
    
    Execution Mode
    
    </td>
    <td valign="top">
    
    You can choose between

    -   Full
    -   Delta
    -   Delta and Streaming


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Selections
    
    </td>
    <td valign="top">
    
    You can restrict the data to be extracted by defining conditions.

    By default, everything will be extracted.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Process Chain Variant
    
    </td>
    <td valign="top">
    
    If you want to use a process chain for the extraction, you have to choose a process chain variant. The process type has to be*Load Process and Postprocessing – Data Subscription*.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Status
    
    </td>
    <td valign="top">
    
    When you set the status to *Active* and save, the local table \(file\) in SAP Datasphere will be created.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Projections
    
    </td>
    <td valign="top">
    
    You can restrict the projections. By default, *Full Projection* is selected, then the complete set of data is being provisioned. Or you can select several fields to be provisioned. The key always has to be selected as well.
    
    </td>
    </tr>
    </table>
    
5.  Save your subscription. The local table \(file\) in SAP Datasphere is created, with the subscription ID as its qualified name.

6.  If you don't use a process chain for the extraction, you can run the extraction directly via *Run* in the menu bar of the list of subscriptions.




<a name="loio58588fb42777455695f66b6ec8980ef3__result_zbq_11b_t2c"/>

## Results

The local table \(file\) is stored in a dedicated BW inbound space \(of type SAP HANA Data Lake Files\), and is not editable. Objects in this space are read-only, but data management tasks \(e.g. deleting data\) are possible. See [Working With Local Tables \(File\) Received From the Data Product Generator for SAP Business Data Cloud](working-with-local-tables-file-received-from-the-data-product-generator-for-sap-business-72a055f.md).

> ### Note:  
> You cannot change the structure of the local table \(file\) as long as the subscription exists. This ensures that the data loads via the process chain will continue to work.

For each SAP BW or SAP BW/4HANA system, a dedicated BW inbound space will be created. Except for task chains, you cannot create objects in this space. You can share the local tables in this space to other spaces, where you can use them for modeling.

