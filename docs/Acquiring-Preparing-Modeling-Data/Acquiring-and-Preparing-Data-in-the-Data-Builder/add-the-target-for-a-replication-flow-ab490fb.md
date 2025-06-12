<!-- loioab490fb4d083442197e2ba3b92079734 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Add the Target for a Replication Flow

Select a target \(connection and container\) to define the target environment for your replication flow.



<a name="loioab490fb4d083442197e2ba3b92079734__context_rr5_54f_vvb"/>

## Context

-   Connections are created by your system administration. You can only use a target if a connection has been created for it in your space and if you have the necessary authorizations. For more information about connections and connection types, see [Integrating Data via Connections](https://help.sap.com/docs/SAP_DATASPHERE/be5967d099974c69b77f4549425ca4c0/eb85e157ab654152bd68a8714036e463.html).

-   Containers are the parent objects that hold the data. For more information, see the documentation for the individual target types.




## Procedure

1.  Choose <span class="FPA-icons-V3"></span> \(Browse target connections\). A list of available target connections appears.

2.  Select the relevant one for your use case.

    > ### Note:  
    > Even if several replication flows can reuse the same source object, you can’t have the same target object in several replication flows.

3.  For some types of targets, the container is predefined and cannot be changed. For any other target, click *Browse target container*. A list of available containers appears. Select the relevant one for your use case. To narrow down the selection, start typing a part of the container name in the *Search* field.

    For more information, see the documentation for your target type, for example [SAP Datasphere Targets](sap-datasphere-targets-12c45eb.md).

4.  Review the target settings and properties and change or complete them as appropriate.

    For more information, see [Configure a Replication Flow](configure-a-replication-flow-3f5ba0c.md).




<a name="loioab490fb4d083442197e2ba3b92079734__postreq_hmd_mmf_jdc"/>

## Next Steps



### Handling Target Columns That Don't Exist in the Source

If you are using an existing table as the target object, this table may contain columns that don't exist in the corresponding source object \(for example due to version differences\). Previously, you had to create a mapping entry for each of these columns before you were able to run the replication flow. Now you can choose between the following options:

-   If you activate the property *Skip Unmapped Columns*, the system ignores the unmapped target columns during the replication flow. Their existing content remains as-is.

    The way these additional columns will appear when you perform a data preview depends on your target type:


    <table>
    <tr>
    <th valign="top">

    Target
    
    </th>
    <th valign="top">

    How Additional Columns are Displayed
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    SAP Datasphere \(SAP HANA space\)
    
    </td>
    <td valign="top">
    
    Additional columns will appear with configured default value or null.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    SAP Datasphere \(File Space\)
    
    </td>
    <td valign="top">
    
    Additional columns will not appear
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Confluent / Kafka
    
    </td>
    <td valign="top">
    
    Additional columns will not appear
    
    </td>
    </tr>
    </table>
    
    > ### Note:  
    > Changing the toggle on an active replication flow will have no effect.

-   If you deactivate it, you get an error message for each unmapped target column when saving the replication flow. However, you can still manually map each column in the *Mapping* tab.


For replication flows created before version 2025.01 of SAP Datasphere, the property is deactivated by default, but you can activate it as required. For replication flows created with version 2025.02 or later, this property is activated by default, and you can deactivate it as required.

If a projection is defined for a target column that doesn't exist in the source, this projection takes precedence over the skipping setting. If there are no unmapped columns in the target, activating or deactivating this property is of no effect.

> ### Note:  
> Skipping is **not** possible for the following column types:
> 
> -   Columns with the property *Not Null* without default value \(For background information, see [Columns](columns-8f0f40d.md).\)
> 
> -   CDC columns
> 
> -   Key columns

