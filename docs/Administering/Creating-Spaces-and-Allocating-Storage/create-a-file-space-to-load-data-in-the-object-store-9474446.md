<!-- loio947444683e524cfd9169d7671b72ba0c -->

# Create a File Space to Load Data in the Object Store

Create a space with SAP HANA data lake files storage in the object store, allocate compute resources and assign one or more users to allow them to start acquiring and preparing data. File spaces are intended for loading and preparing large quantities of data in an inexpensive inbound staging area.

> ### Note:  
> The object store is not enabled by default in SAP Datasphere tenants. To enable it in your tenant, see SAP note [3525760](https://me.sap.com/notes/3525760).
> 
> For additional information on working with data in the object store, see SAP Note [3538038](https://me.sap.com/notes/3538038).
> 
> The object store cannot be enabled in SAP Datasphere tenants provisioned prior to version 2021.03. To request the migration of your tenant, see SAP note [3268282](https://me.sap.com/notes/3268282).

> ### Note:  
> You cannot create or manage a file space via the command line, add a file space to an elastic compute node, or choose a file space as a monitoring space. You cannot monitor, lock, or unlock a file space. You cannot generate time data, enable audit logging, create database users, or associate HDI containers in a file space.
> 
> You can create up to 5 file spaces in a tenant.

Users with an administrator role can create spaces, allocate compute resources and assign users. The remaining space properties can be managed by the space administrators that the administrator assigns to the space via a scoped role.

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
    
    Select *SAP HANA Data Lake Files*.
    
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
    
5.  *Workload Management* section - The maximum amount of compute resources that the file space can consume when processing statements are allocated to its Apache Spark instance. The resources allocated for the file space are based on the resources allocated for the SAP Datasphere tenant in the *Tenant Configuration* page \(see [Configure the Size of Your SAP Datasphere Tenant](../Creating-and-Configuring-Your-Tenant/configure-the-size-of-your-sap-datasphere-tenant-33f8ef4.md)\).

    Several applications are available for the instance and are used to run tasks.


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

    > ### Note:  
    > Applications 100, 200 and 500 are currently not in use.


    
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
    <tr>
    <td valign="top">
    
    *Transformation Flow Default*
    
    </td>
    <td valign="top">
    
    \[read-only\] The checkbox indicates the application that is used by default to run a transformation flow in a file space.

    See [Creating a Transformation Flow in a File Space](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/b917baf0431343bea8381fa37e12eeb8.html "Create transformation flows with local tables (file) as sources, apply various transformations, and store the resulted dataset into another local table (file).") :arrow_upper_right:
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Merge Default*
    
    </td>
    <td valign="top">
    
    \[read-only\] The checkbox indicates the application that is used by default to run a merge activity via a task chain.

    See [Creating a Task Chain](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/d1afbc2b9ee84d44a00b0b777ac243e1.html "Group multiple tasks into a task chain and run them manually once, or periodically, through a schedule.") :arrow_upper_right:
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Optimize Default*
    
    </td>
    <td valign="top">
    
    \[read-only\] The checkbox indicates the application that is used by default to run an optimize activity via a task chain.

    See [Creating a Task Chain](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/d1afbc2b9ee84d44a00b0b777ac243e1.html "Group multiple tasks into a task chain and run them manually once, or periodically, through a schedule.") :arrow_upper_right:
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Local Table \(File\) Deployment*
    
    </td>
    <td valign="top">
    
    \[read-only\] The checkbox indicates the application that is used by default to deploy a local table \(file\).

    See [Creating a Local Table (File)](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/d21881b121bc4703861be6ead4aea2ab.html "Create a local table (file) to store data in the object store. Load data to your local table (file) via replication flows and transform the data with transformation flows.") :arrow_upper_right:
    
    </td>
    </tr>
    </table>
    
    To modify the size of the instance at any time, change the number of vCPUs and click *Update*. You should change the size of your instance based on the resource amounts displayed in the *Max. Used* column of the table. For example, you can see that the application used to run a transformation flow is allocated 168 CPU and 672 GB of memory. If you want that 4 transformation flows can be run in parallel, you must enter the number of 672 in *vCPUs*. The amount of memory is automatically calculated based on the number of vCPUs with a ratio of 1:4 \(for example 672 vCPUs, 2688 GB of memory\). The minimum size for the instance is 408 vCPUs \(and 1632 GB of memory\), and the maximum size is 2048 vCPUs \(and 8192 GB of memory\).

6.  Add your space to one or more scoped roles by doing one of the following actions:

    -   Add your space to an existing scoped role \(see [Add Spaces to a Scoped Role](../Managing-Users-and-Roles/create-a-scoped-role-to-assign-privileges-to-users-in-spaces-b5c4e0b.md#loiob5c4e0b6c462414783ebbfc053815521__section_pr1_5pj_zyb)\).

    -   Create a scoped role and add your space and at least one user to the scoped role \(see [Create a Scoped Role](../Managing-Users-and-Roles/create-a-scoped-role-to-assign-privileges-to-users-in-spaces-b5c4e0b.md#loiob5c4e0b6c462414783ebbfc053815521__section_z4m_mpj_zyb)\).


    For more information, see [Create a Scoped Role to Assign Privileges to Users in Spaces](../Managing-Users-and-Roles/create-a-scoped-role-to-assign-privileges-to-users-in-spaces-b5c4e0b.md).

    All users assigned to the space via the scoped roles are automatically displayed in the *Users* area of the space page. In this area, you can add or remove users to/from scoped roles for your space \(see [Control User Access to Your Space](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/9d59fe511ae644d98384897443054c16.html "You can assign users to your space and manage them.") :arrow_upper_right:\). Either a user with an administrator role or a user with a space administrator role can do so.


> ### Note:  
> -   If you've made some changes in the *General Settings* area, such as changing the space name or entering a description, click *Save*.
> 
> -   If your file space and its data lake instance or Apache Spark instance run into communication errors, click *Deploy*.

For more information about working with data in the object store, see [Acquiring and Preparing Data in the Object Store](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/2a6bc3f6d79b4c39a01b6d58d043fbaf.html "Users with a modeler role can load large quantities of data via replication flows and store them inexpensively in file spaces in the object store. You can prepare the data using transformation flows and then share data to a standard space to be used as a source of flows, views, and analytic models.") :arrow_upper_right:.

