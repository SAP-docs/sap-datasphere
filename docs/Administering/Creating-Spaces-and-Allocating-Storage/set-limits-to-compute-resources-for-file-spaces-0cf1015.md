<!-- loio0cf1015768e44324b4088da4c5ebd8ca -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Set Limits to Compute Resources for File Spaces

Set limits to the amount of compute resources that Apache Spark applications can consume when running tasks. You can use the default configurations, which are applied by default to new file spaces, or create your own configurations for a specific file space.

This topic contains the following sections:

-   [Prerequisites](set-limits-to-compute-resources-for-file-spaces-0cf1015.md#loio0cf1015768e44324b4088da4c5ebd8ca__section_prereq_spark_filespace)
-   [Create a Configuration](set-limits-to-compute-resources-for-file-spaces-0cf1015.md#loio0cf1015768e44324b4088da4c5ebd8ca__section_create_config_spark)
-   [Modify Task Assignments](set-limits-to-compute-resources-for-file-spaces-0cf1015.md#loio0cf1015768e44324b4088da4c5ebd8ca__section_view_default_config_spark)
-   [Delete a Custom Configuration](set-limits-to-compute-resources-for-file-spaces-0cf1015.md#loio0cf1015768e44324b4088da4c5ebd8ca__section_delete_config_spark)



<a name="loio0cf1015768e44324b4088da4c5ebd8ca__section_prereq_spark_filespace"/>

## Prerequisites

To set limits to compute resources for file spaces, you must have a global role that grants you the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *System Information* \(`-RU-----`\) - To access the *Configuration* area in the *System* tool.

The *DW Administrator* global role, for example, grants these privileges. For more information, see [Privileges and Permissions](../Managing-Users-and-Roles/privileges-and-permissions-d7350c6.md) and [Standard Application RolesStandard Roles Delivered with SAP Datasphere](../Managing-Users-and-Roles/standard-application-rolesstandard-roles-delivered-with-sap-datasphere-a50a51d.md). 



<a name="loio0cf1015768e44324b4088da4c5ebd8ca__section_create_config_spark"/>

## Create a Configuration

A set of Apache Spark configurations is applied by default to each new file space, and are used to run certain tasks. You can create your own configurations for a specific file space by using a default configuration as a template.

1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(*System*\) ** \> ** :wrench: \(*Configuration*\)** \> *Workload Management* \> *SAP HANA Data Lake Files*, then choose the *Default Configurations* tab.
2.  Select the row of the default configuration that you want to use as a template and choose *Create*.
3.  In the *Create* dialog box, complete the following properties:


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
    
    *Configuration ID*
    
    </td>
    <td valign="top">
    
    Enter an ID of the configuration. The ID can only contain a maximum of 9 numbers above 9999 \(as numbers below are reserved for SAP default configurations\).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Description*
    
    </td>
    <td valign="top">
    
    Enter a description of the configuration. The description can contain a maximum of 64 characters, and can contain letters \(a-z\), numbers \(0-9\), spaces and special characters.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Space*
    
    </td>
    <td valign="top">
    
    Select the space for which you're creating the configuration.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Executor Memory*

    Apache Spark technical name: `spark.executor.memory`
    
    </td>
    <td valign="top">
    
    \[read-only\] Shows the amount of memory in GB allocated per executor.

    > ### Note:  
    > The amount of memory is automatically adjusted based on the number entered in *Executor Cores*, with a ratio of 4:1 \(for example 16 GB of memory and 4 cores\).


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Driver Memory*

    Apache Spark technical name: `spark.driver.memory`
    
    </td>
    <td valign="top">
    
    \[read-only\] Specify the amount of memory in GB allocated to the driver.

    > ### Note:  
    > The amount of memory is automatically adjusted based on the number entered in *Driver Cores*, with a ratio of 4:1 \(for example 16 GB of memory and 4 cores\).


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Number of Executors*

    Apache Spark technical name: `spark.executor.instances`
    
    </td>
    <td valign="top">
    
    Specify the number of executors.

    > ### Note:  
    > Relevant for static allocation only.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Executor Cores*

    Apache Spark technical name: `spark.executor.cores`
    
    </td>
    <td valign="top">
    
    Specify the number of cores per executor.

    > ### Note:  
    > When you change this number, the amount of GB in *Executor Memory* is automatically adjusted, with a ratio of 1:4 \(for example 4 cores and 16 GB\).


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Executor Storage*

    Apache Spark technical name: `spark.kubernetes.executor.volumes`
    
    </td>
    <td valign="top">
    
    Specify the amount of disk size in GB allocated for each executor.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Driver Cores*

    Apache Spark technical name: `spark.driver.cores`
    
    </td>
    <td valign="top">
    
    Specify the number of cores to use for the driver process, only in cluster mode.

    > ### Note:  
    > When you change this number, the amount of GB in *Driver Memory* is automatically adjusted, with a ratio of 1:4 \(for example 4 cores and 16 GB\).


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Max. Driver Result Size*

    Apache Spark technical name: `spark.driver.maxResultSize`
    
    </td>
    <td valign="top">
    
    Specify the intermediate result stored in the driver, which is the maximum amount of serialized data \(in GB\) that the Apache Spark driver program is allowed to receive from executors in a single action, such as operations like sorting or any logic that requires sending results back to the driver.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Min. Number of Executors*

    Apache Spark technical name: `spark.dynamicAllocation.minExecutors`
    
    </td>
    <td valign="top">
    
    Specify the lower bound for the number of executors, if dynamic allocation is enabled.

    > ### Note:  
    > Relevant for dynamic allocation only.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Max. Number of Executors*

    Apache Spark technical name: `spark.dynamicAllocation.maxExecutors`
    
    </td>
    <td valign="top">
    
    Specify the upper bound for the number of executors, if dynamic allocation is enabled.

    > ### Note:  
    > Relevant for dynamic allocation only.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Init. Number Executors*

    Apache Spark technical name: `spark.dynamicAllocation.initialExecutors`
    
    </td>
    <td valign="top">
    
    Specify the initial number of executors to run, if dynamic allocation is enabled.

    > ### Note:  
    > Relevant for dynamic allocation only.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Dynamic Allocation*

    Apache Spark technical name: `spark.dynamicAllocation.enabled`
    
    </td>
    <td valign="top">
    
    By default, dynamic resource allocation is enabled, which scales the number of executors registered with the configuration up and down based on the workload.

    We recommend using dynamic allocation because it allows your application to adjust its resource usage in real time. When your application does not need certain resources, it can release them back to the cluster, and later request them again when demand increases. This feature is particularly useful if multiple applications share resources in your Apache Spark cluster.
    
    </td>
    </tr>
    </table>
    
4.  Choose *Save*.

    The new configuration is displayed in the *Custom Configurations* tab.

5.  Choose *Custom Configurations*. You can view additional properties for the custom configuration you've created, in the table and by clicking the info icon. These properties are available for your information but you cannot change them:


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
    
    *Source ID*
    
    </td>
    <td valign="top">
    
    \[read-only\] ID of the default configuration used as a template to create the custom configuration.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Maximum Cores*
    
    </td>
    <td valign="top">
    
    \[read-only\] Maximum number of vCPUs that can be used for the configuration.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Maximum Memory*
    
    </td>
    <td valign="top">
    
    \[read-only\] Maximum amount of resources in GB that can be used for the configuration.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Shuffle Partitions* 

    Apache Spark technical name: `spark.sql.shuffle.partitions`
    
    </td>
    <td valign="top">
    
    \[read-only\] Default number of partitions to use when shuffling data for joins or aggregations.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Max. Partition Size*

    Apache Spark technical name: `spark.sql.files.maxPartitionBytes`
    
    </td>
    <td valign="top">
    
    \[read-only\] Maximum number of bytes to pack into a single partition when reading files.
    
    </td>
    </tr>
    </table>
    
    > ### Note:  
    > For more information about the Apache Spark configuration properties, refer to the official Apache Spark documentation.


> ### Note:  
> You can modify the properties of a custom configuration at any time in *Custom Configurations* by selecting its row and choosing *Edit*.



<a name="loio0cf1015768e44324b4088da4c5ebd8ca__section_view_default_config_spark"/>

## Modify Task Assignments

For each new space file, default Apache Spark configurations are used by default to run certain tasks. You can assign another configuration to a task, which can either be a default or a custom configuration.

1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(*System*\) ** \> ** :wrench: \(*Configuration*\)** \> *Workload Management* \> *SAP HANA Data Lake Files*, then choose the *Default Task Assignments* tab.
2.  View which configurations are used by default to run which tasks:


    <table>
    <tr>
    <th valign="top">

    Object Type
    
    </th>
    <th valign="top">

    Activity
    
    </th>
    <th valign="top">

    SAP Default Configuration
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top" rowspan="7">
    
    LOCAL\_TABLE
    
    </td>
    <td valign="top">
    
    MERGE\_FILES
    
    </td>
    <td valign="top">
    
    100
    
    </td>
    <td valign="top">
    
    \[read-only\] Shows the configuration that is used by default to run a merge task for a local table \(file\).

    See [Merge or Optimize Your Local Tables (File)](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/e533b154ed3e49ce9a03e4421a5296e7.html "Local Tables (File) can store large quantities of data in the object store. You can manage this file storage with merge or optimize tasks, and allocate the required amount of compute resources that the file space can consume when processing these tasks.") :arrow_upper_right:
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    OPTIMIZE\_FILES
    
    </td>
    <td valign="top">
    
    100
    
    </td>
    <td valign="top">
    
    \[read-only\] Shows the configuration that is used by default to run an optimize task for a local table \(file\).

    See [Merge or Optimize Your Local Tables (File)](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/e533b154ed3e49ce9a03e4421a5296e7.html "Local Tables (File) can store large quantities of data in the object store. You can manage this file storage with merge or optimize tasks, and allocate the required amount of compute resources that the file space can consume when processing these tasks.") :arrow_upper_right:
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    TRUNCATE\_FILES\_WITH\_FILTER
    
    </td>
    <td valign="top">
    
    001
    
    </td>
    <td valign="top">
    
    \[read-only\] Shows the configuration that is used by default to run a deletion task and delete filtered records of a local table \(file\).

    See [Delete Data From Your Local Tables (File)](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/872ad509995a451890bf8b80b73ec0e6.html "Delete records or versions of a local table (File), creating a direct task or using a schedule, and free up storage by allocating the required amount of compute resources that the file space can consume when processing these tasks.") :arrow_upper_right:
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    TRUNCATE\_FILES
    
    </td>
    <td valign="top">
    
    001
    
    </td>
    <td valign="top">
    
    \[read-only\] Shows the configuration that is used by default to run a deletion task and delete filtered records of a local table \(file\).

    See [Delete Data From Your Local Tables (File)](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/872ad509995a451890bf8b80b73ec0e6.html "Delete records or versions of a local table (File), creating a direct task or using a schedule, and free up storage by allocating the required amount of compute resources that the file space can consume when processing these tasks.") :arrow_upper_right:
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    VACUUM\_FILES
    
    </td>
    <td valign="top">
    
    001
    
    </td>
    <td valign="top">
    
    \[read-only\] Shows the configuration that is used by default to run a deletion task and delete previous versions \(vacuum\) of a local table \(file\).

    See [Delete Data From Your Local Tables (File)](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/872ad509995a451890bf8b80b73ec0e6.html "Delete records or versions of a local table (File), creating a direct task or using a schedule, and free up storage by allocating the required amount of compute resources that the file space can consume when processing these tasks.") :arrow_upper_right:
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    DELETE\_INBOUND\_BUFFER
    
    </td>
    <td valign="top">
    
    001
    
    </td>
    <td valign="top">
    
    \[read-only\] Shows the configuration that is used by default to run a deletion task and delete the records of a local table \(file\) that are waiting in the inbound buffer.

    See [Delete Data From Your Local Tables (File)](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/872ad509995a451890bf8b80b73ec0e6.html "Delete records or versions of a local table (File), creating a direct task or using a schedule, and free up storage by allocating the required amount of compute resources that the file space can consume when processing these tasks.") :arrow_upper_right:
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    FIND\_AND\_REPLACE
    
    </td>
    <td valign="top">
    
    001
    
    </td>
    <td valign="top">
    
    \[read-only\] Shows the configuration that is used by default to run a find & replace task in a local table \(file\).

    See [Preview and Edit Local Table (File) Data](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/e57e12d39535439eb078078228c6f7bf.html "You want to preview and edit local table (file) data.") :arrow_upper_right:
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    TRANSFORMATION\_FLOWS
    
    </td>
    <td valign="top">
    
    RUN
    
    </td>
    <td valign="top">
    
    100
    
    </td>
    <td valign="top">
    
    \[read-only\] Shows the configuration that is used by default to run a transformation flow in a local table \(file\).

    See [Creating a Transformation Flow in a File Space](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/cloud/en-US/b917baf0431343bea8381fa37e12eeb8.html "Create transformation flows with local tables (file), shared local tables (file), shared local tables, and shared remote tables on a Delta Share runtime as sources, apply various transformations, and store the resulted dataset into another local table (file).") :arrow_upper_right:
    
    </td>
    </tr>
    </table>
    
3.  To assign another configuration to a task, select the configuration in the drop-down list of the *Default Configuration* column.

    The configuration selected will be used by default to run the task. However, users will be able to choose a different configuration before starting their tasks.

4.  Choose *Save*.

> ### Note:  
> You can revert all task assignments to the default configurations by choosing *Reset*.

> ### Note:  
> To monitor the resources used for a configuration, navigate to the *Task Logs* tab of the *System Monitor*, select *SAP HANA Data Lake Files* in the filter *Space Storage Type*, and display the columns that are related to Apache Spark \(see [Administering SAP Datasphere](../administering-sap-datasphere-70ee87c.md)\). For example, the percentage displayed in the *Apache Spark Peak Memory %* column can indicate if the memory resources allocated to the configuration are sufficient or should be adjusted.



<a name="loio0cf1015768e44324b4088da4c5ebd8ca__section_delete_config_spark"/>

## Delete a Custom Configuration

You can delete a custom configuration that is no longer needed.

1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(*System*\) ** \> ** :wrench: \(*Configuration*\)** \> *Workload Management* \> *SAP HANA Data Lake Files*, then choose the *Custom Configurations* tab.
2.  Select the row of the default configuration that you want to delete and choose *Delete*.
3.  In the confirmation dialog that opens, choose *Delete*.

