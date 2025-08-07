<!-- loio947444683e524cfd9169d7671b72ba0c -->

# Create a File Space to Load Data in the Object Store

Create a file space and allocate compute resources to it. File spaces are intended for loading and preparing large quantities of data in an inexpensive inbound staging area and are stored in the SAP Datasphere object store.



<a name="loio947444683e524cfd9169d7671b72ba0c__section_zmp_nbp_hfc"/>

## Prerequisites

To create a file space, you must have a global role that grants you the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Spaces* \(`C-------`\) - To create spaces.
-   *User* \(`-R------`\) - To allow the creation of spaces.
-   *Spaces* \(`-------M`\) - To update all spaces and space properties.

The *DW Administrator* global role, for example, grants these privileges. For more information, see [Privileges and Permissions](../Managing-Users-and-Roles/privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](../Managing-Users-and-Roles/standard-roles-delivered-with-sap-datasphere-a50a51d.md). 



<a name="loio947444683e524cfd9169d7671b72ba0c__section_u3t_mbp_hfc"/>

## Context

> ### Note:  
> For additional information on working with data in the object store, see SAP note [3538038](https://me.sap.com/notes/3538038).

> ### Note:  
> You cannot create or manage a file space via the command line, add a file space to an elastic compute node, or choose a file space as a monitoring space. You cannot monitor, lock, or unlock a file space. You cannot generate time data, enable audit logging, create database users, or associate HDI containers in a file space.
> 
> You can create up to 5 file spaces in a tenant.

Users with an administrator role can create spaces, allocate compute resources and assign users. The remaining space properties can be managed by users with a space administrator role.



<a name="loio947444683e524cfd9169d7671b72ba0c__section_oyn_kbp_hfc"/>

## Procedure

1.  In the side navigation area, click ![](../images/Space_Management_a868247.png) \(*Space Management*\), and click *Create*.

2.  In the *Create Space* dialog, complete the following properties:


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
    
    Space Name
    
    </td>
    <td valign="top">
    
    Enter the business name of the space. Can contain a maximum of 30 characters, and can contain spaces and special characters.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Space ID
    
    </td>
    <td valign="top">
    
    Enter the technical name of the space. Can contain a maximum of 20 uppercase letters or numbers and must not contain spaces or special characters other than `_` \(underscore\). Unless advised to do so, must not contain prefix \_SYS and should not contain prefixes: DWC\_, SAP\_ \(See [Rules for Technical Names](rules-for-technical-names-982f9a3.md)\).As the technical name will be displayed in the Open SQL Schema and in monitoring tools, including SAP internal tools, we recommend that you do not include sensitive business or personal data in the name.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Storage Type
    
    </td>
    <td valign="top">
    
    Select *SAP HANA Data Lake Files*. The option is greyed out if no resources have been allocated to the object store \(see [Configure the Size of Your SAP Datasphere Tenant](../Creating-and-Configuring-Your-Tenant/configure-the-size-of-your-sap-datasphere-tenant-33f8ef4.md)\).
    
    </td>
    </tr>
    </table>
    
3.  Click *Create*. The space page opens. The creation and provisioning of a file space may take several minutes. You must wait for the notification message indicating that the file space is deployed before you can start working with the file space.

4.  Review the following properties in the *General Settings* section:


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
    
    Space ID
    
    </td>
    <td valign="top">
    
    Enter the technical name of the space. Can contain a maximum of 20 uppercase letters or numbers and must not contain spaces or special characters other than `_` \(underscore\). Unless advised to do so, must not contain prefix \_SYS and should not contain prefixes: DWC\_, SAP\_ \(See [Rules for Technical Names](rules-for-technical-names-982f9a3.md)\).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Space Name
    
    </td>
    <td valign="top">
    
    Enter the business name of the space. Can contain a maximum of 30 characters, and can contain spaces and special characters.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Space Status
    
    </td>
    <td valign="top">
    
    \[read-only\] Displays the status of the space. Newly-created spaces are always active.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Space Type
    
    </td>
    <td valign="top">
    
    \[read-only\] Displays the type of the space. You can only create spaces of type SAP Datasphere.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Created By
    
    </td>
    <td valign="top">
    
    \[read-only\] Displays the user that created the space.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Created On
    
    </td>
    <td valign="top">
    
    \[read-only\] Displays the date and time when the space was created.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Deployment Status
    
    </td>
    <td valign="top">
    
    \[read-only\] Displays the deployment status of the space. Newly-created spaces are deployed, but when you make changes, you need to save and re-deploy them before they are available to space users.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Deployed On
    
    </td>
    <td valign="top">
    
    \[read-only\] Displays the date and time when the space was last deployed.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Description
    
    </td>
    <td valign="top">
    
    \[optional\] Enter a description for the space. Can contain a maximum of 4 000 characters.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Storage Type
    
    </td>
    <td valign="top">
    
    \[read-only\] Displays where the space is stored on.
    
    </td>
    </tr>
    </table>
    
5.  *Apache Spark* section - The maximum amount of compute resources that the file space can consume when processing statements are allocated to its Apache Spark instance. The resources allocated for the file space depend on the resources allocated for the object store in the *Tenant Configuration* page \(see [Configure the Size of Your SAP Datasphere Tenant](../Creating-and-Configuring-Your-Tenant/configure-the-size-of-your-sap-datasphere-tenant-33f8ef4.md)\).

    The following applications, which are listed in the *Applications* area, are available for the instance and are used to run the tasks that are listed in the *Task Assignment* area.


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
    
    *Application*
    
    </td>
    <td valign="top">
    
    \[read-only\] Shows the name of the application.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Cluster Size*
    
    </td>
    <td valign="top">
    
    \[read-only\] Qualifies the overall size of resources allocated to the application. For example, micro or medium.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Driver*
    
    </td>
    <td valign="top">
    
    \[read-only\] Shows the amount of resources allocated to the driver for the application.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Executor*
    
    </td>
    <td valign="top">
    
    \[read-only\] Shows the amount of resources allocated to the executor for the application.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Max. Used*
    
    </td>
    <td valign="top">
    
    \[read-only\] Shows the maximum amount of resources that can be used for the application.
    
    </td>
    </tr>
    </table>
    
    You can view which applications are used by default to run which tasks in the *Task Assignment* area.


    <table>
    <tr>
    <th valign="top">

    Object Type
    
    </th>
    <th valign="top">

    Activity
    
    </th>
    <th valign="top">

    Default Application
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    LOCAL\_TABLE
    
    </td>
    <td valign="top">
    
    DELETE\_DATA, MERGE\_FILES, OPTIMIZE\_FILES, TRUNCATE\_FILES, VACUUM\_FILES, FIND\_AND\_REPLACE
    
    </td>
    <td valign="top">
    
    300
    
    </td>
    <td valign="top">
    
    \[read-only\] Indicates the application that is used by default to run all the activities listed via a task chain or the *Local Tables \(File\)* monitor.

    See [Creating a Task Chain](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/d1afbc2b9ee84d44a00b0b777ac243e1.html "Group multiple tasks into a task chain and run them manually once, or periodically, through a schedule.") :arrow_upper_right: and [Monitoring Local Tables (File)](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/6b2d0073a8684ee6a59d6f47d00ec895.html "Monitor your local tables (file). Check how and when they were last updated and if new data has still to be merged.") :arrow_upper_right:.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    TRANSFORMATION\_FLOWS
    
    </td>
    <td valign="top">
    
    EXECUTE
    
    </td>
    <td valign="top">
    
    400
    
    </td>
    <td valign="top">
    
    \[read-only\] Indicates the application that is used by default to run a transformation flow in a file space.

    See [Creating a Transformation Flow in a File Space](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/b917baf0431343bea8381fa37e12eeb8.html "Create transformation flows with local tables (file) as sources, apply various transformations, and store the resulted dataset into another local table (file).") :arrow_upper_right:
    
    </td>
    </tr>
    </table>
    
    To modify the size of the instance at any time, change the amount of memory and click *Update*. You should change the size of your instance based on the resource amounts displayed in the *Max. Used* column of the table. For example, you can see that the application used to run transformation flows is allocated 168 CPU and 672 GB of memory. If you want that 4 transformation flows can be run in parallel, you must enter 2688 in *Memory \(GB\)*. The amount of vCPUs is automatically calculated based on the amount of memory with a ratio of 4:1 \(for example 2688 GB of memory and 672 vCPUs\). The minimum size for the instance is 1632 GB of memory \(and 408 vCPUs\), and its maximum size is 8192 GB of memory \(and 2048 vCPUs\).

6.  Add your space to one or more scoped roles. You can:

    -   Add your space to an existing scoped role \(see [Add Spaces to a Scoped Role](../Managing-Users-and-Roles/create-a-scoped-role-to-assign-privileges-to-users-in-spaces-b5c4e0b.md#loiob5c4e0b6c462414783ebbfc053815521__section_pr1_5pj_zyb)\).

    -   Create a scoped role and add your space and at least one user to the scoped role \(see [Create a Scoped Role](../Managing-Users-and-Roles/create-a-scoped-role-to-assign-privileges-to-users-in-spaces-b5c4e0b.md#loiob5c4e0b6c462414783ebbfc053815521__section_z4m_mpj_zyb)\).


    For more information, see [Create a Scoped Role to Assign Privileges to Users in Spaces](../Managing-Users-and-Roles/create-a-scoped-role-to-assign-privileges-to-users-in-spaces-b5c4e0b.md).

    All users assigned to the space via the scoped roles are automatically displayed in the *Users* area of the space page. In this area, you can add or remove users to/from scoped roles for your space \(see [Control User Access to Your Space](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/9d59fe511ae644d98384897443054c16.html "You can assign users to your space and manage them.") :arrow_upper_right:\). Either a user with an administrator role or a user with a space administrator role can do so.


> ### Note:  
> -   If you've made some changes in the *General Settings* area, such as changing the space name or entering a description, click *Save*.
> 
> -   If your file space and its data lake instance or Apache Spark instance run into communication errors, click *Deploy*.

> ### Note:  
> The total amount of storage consumed by the file space includes: local tables \(files\) \(total storage in MiB + buffer file size in MiB\), logs, and backups of deleted objects \(which are kept for 14 days after deletion\).
> 
> Local tables stored in a space of type *SAP HANA Database \(Disk and In-Memory\)* may have a different size than equivalent local tables \(files\) \(of type *SAP HANA Data Lake Files*\) stored on the object store as the compression rate is different. More importantly, having many previous versions available for your tables, will increase their size. This is why we recommend to do regular permanent data deletion \(vacuum\).
> 
> You can view the total amount of storage consumed by a file space in these areas of the *Space Management*: in the *SAP HANA Data Lake Files* area of the space tile when in tile layout and in the *SAP HANA Data Lake Files* column in the table layout.

For more information about working with data in the object store, see [Acquiring and Preparing Data in the Object Store](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/2a6bc3f6d79b4c39a01b6d58d043fbaf.html "Users with a modeler role can load large quantities of data via replication flows and store them inexpensively in file spaces in the SAP Datasphere object store. You can prepare the data using Apache Spark transformation flows and then share data to a standard space to be used as a source of flows, views, and analytic models.") :arrow_upper_right:.

