<!-- loiobfb51914340448f6acb51b70058aa28f -->

# Capturing Delta Changes in Your Local Table \(File\)

Enable *Delta Capture* in your local table \(file\) to automatically track all inserts, updates, and deletions of its records via *Change Date* and *Change Type* columns. You can use Replication Flows and Transformation Flows to write to these tables and to read from them, extracting only delta changes for each run.



## Prerequisites

To enable Delta Capture:

-   You table must have a status *Not Deployed*.
-   You must define one or more key columns.



## Switching Delta Capture On

Local tables \(files\) can be used as source data or target data by SAP Datasphere apps. For some business scenarios, you might need to keep an eye on changes that will be made after you have deployed your local table \(file\). For example, after you run a merge task or a transformation flow, you might want to know which data is updated or deleted. When creating a local table \(file\), you can switch on a toggle that will capture the future updates made in your table.

> ### Restriction:  
> The delta capture table is an internal view whose structure can incompatibly change at any time. It is not permitted for external data access and is only consumed by the above SAP Datasphere internal apps. Using the internal delta capture columns \(*Change Date* or *Change Type*\) or their content directly or indirectly for external delta replication outside the Premium Outbound Integration is also not permitted. For more information, see [Premium Outbound Integration](https://blogs.sap.com/2023/11/16/replication-flow-blog-series-part-2-premium-outbound-integration/).

In a local table \(file\), the data is stored in a Delta Lake table in the *SAP HANA Data Lake Files* storage. The columnar parquet files in the table's directory belong to different versions of the data. If delta capture is switched on, versions are tracked in a folder "\_delta\_log", which allows for time travel to historic data versions. Every 10 versions, a checkpoint file is stored in this folder, which represents a full snapshot of the version. Those checkpoint files are required to load the data changes in this version and the subsequent 9 versions for which no checkpoint file is created.

> ### Restriction:  
> The log retention time in the *SAP HANA Data Lake Files* storage is 30 days. Checkpoint files that are older than 30 days are automatically cleaned up when a new version is created. Make sure to process data changes in a transformation flow before the required checkpoint files get deleted. As best practices, we recommend not to let more than 3 days between a merge task and a flow run.
> 
> > ### Example:  
> > Let's say that today is January 27, 2026, and the latest version of your local table \(file\) is in version 13, last updated on January 26. You now want to run a transformation flow that needs to access versions 7 to 13:
> > 
> > -   SAP Datasphere will first identify the latest checkpoint that is less than or equal to version 7 \(in our example, it would be version 0\).
> > -   If a checkpoint exists at version 0, it will use it as a reference, reapplying the changes from transaction log files 1 to 7, and reconstructing the table state as of version 0.
> > -   If log files have been deleted \(in our example, files containing versions 0,1,2,3,4 have been deleted because they were older than 30 days\), then the information is no longer available, and versions from 0 to 9 cannot be recovered.
> > 
> > **Retention Logs and Checkpoints**
> > 
> > 
> > <table>
> > <tr>
> > <th valign="top">
> > 
> > Table Version
> > 
> > </th>
> > <th valign="top">
> > 
> > Table Last Updated On
> > 
> > </th>
> > <th valign="top">
> > 
> > Checkpoint
> > 
> > </th>
> > <th valign="top">
> > 
> > Log Files
> > 
> > </th>
> > <th valign="top">
> > 
> > Recovery
> > 
> > </th>
> > </tr>
> > <tr>
> > <td valign="top">
> > 
> > 0
> > 
> > </td>
> > <td valign="top">
> > 
> > December 6
> > 
> > </td>
> > <td valign="top">
> > 
> > 0
> > 
> > </td>
> > <td valign="top">
> > 
> > Deleted as older than 30 days
> > 
> > </td>
> > <td valign="top">
> > 
> > Not Available
> > 
> > </td>
> > </tr>
> > <tr>
> > <td valign="top">
> > 
> > 1
> > 
> > </td>
> > <td valign="top">
> > 
> > December 10
> > 
> > </td>
> > <td valign="top">
> > 
> >  
> > 
> > </td>
> > <td valign="top">
> > 
> > Deleted as older than 30 days
> > 
> > </td>
> > <td valign="top">
> > 
> > Not Available
> > 
> > </td>
> > </tr>
> > <tr>
> > <td valign="top">
> > 
> > 2
> > 
> > </td>
> > <td valign="top">
> > 
> > December 14
> > 
> > </td>
> > <td valign="top">
> > 
> >  
> > 
> > </td>
> > <td valign="top">
> > 
> > Deleted as older than 30 days
> > 
> > </td>
> > <td valign="top">
> > 
> > Not Available
> > 
> > </td>
> > </tr>
> > <tr>
> > <td valign="top">
> > 
> > 3
> > 
> > </td>
> > <td valign="top">
> > 
> > December 16
> > 
> > </td>
> > <td valign="top">
> > 
> >  
> > 
> > </td>
> > <td valign="top">
> > 
> > Deleted as older than 30 days
> > 
> > </td>
> > <td valign="top">
> > 
> > Not Available
> > 
> > </td>
> > </tr>
> > <tr>
> > <td valign="top">
> > 
> > 4
> > 
> > </td>
> > <td valign="top">
> > 
> > December 20
> > 
> > </td>
> > <td valign="top">
> > 
> >  
> > 
> > </td>
> > <td valign="top">
> > 
> > Deleted as older than 30 days
> > 
> > </td>
> > <td valign="top">
> > 
> > Not Available
> > 
> > </td>
> > </tr>
> > <tr>
> > <td valign="top">
> > 
> > 5
> > 
> > </td>
> > <td valign="top">
> > 
> > January 2
> > 
> > </td>
> > <td valign="top">
> > 
> >  
> > 
> > </td>
> > <td valign="top">
> > 
> > Available
> > 
> > </td>
> > <td valign="top">
> > 
> > Available \(checkpoint 0, version 5 can be reapplied\)
> > 
> > </td>
> > </tr>
> > <tr>
> > <td valign="top">
> > 
> > 6
> > 
> > </td>
> > <td valign="top">
> > 
> > January 3
> > 
> > </td>
> > <td valign="top">
> > 
> >  
> > 
> > </td>
> > <td valign="top">
> > 
> > Available
> > 
> > </td>
> > <td valign="top">
> > 
> > Available \(checkpoint 0, versions 5 and 6 can be reapplied\)
> > 
> > </td>
> > </tr>
> > <tr>
> > <td valign="top">
> > 
> > 7
> > 
> > </td>
> > <td valign="top">
> > 
> > January 6
> > 
> > </td>
> > <td valign="top">
> > 
> >  
> > 
> > </td>
> > <td valign="top">
> > 
> > Available
> > 
> > </td>
> > <td valign="top">
> > 
> > Available \(checkpoint 0, versions 5, 6 and 7 can be reapplied\)
> > 
> > </td>
> > </tr>
> > <tr>
> > <td valign="top">
> > 
> > 8
> > 
> > </td>
> > <td valign="top">
> > 
> > January 8
> > 
> > </td>
> > <td valign="top">
> > 
> >  
> > 
> > </td>
> > <td valign="top">
> > 
> > Available
> > 
> > </td>
> > <td valign="top">
> > 
> > Available \(checkpoint 0, versions 5 to 8 can be reapplied\)
> > 
> > </td>
> > </tr>
> > <tr>
> > <td valign="top">
> > 
> > 9
> > 
> > </td>
> > <td valign="top">
> > 
> > January 10
> > 
> > </td>
> > <td valign="top">
> > 
> >  
> > 
> > </td>
> > <td valign="top">
> > 
> > Available
> > 
> > </td>
> > <td valign="top">
> > 
> > Available \(checkpoint 0, versions 5 to 9 can be reapplied\)
> > 
> > </td>
> > </tr>
> > <tr>
> > <td valign="top">
> > 
> > 10
> > 
> > </td>
> > <td valign="top">
> > 
> > January 14
> > 
> > </td>
> > <td valign="top">
> > 
> > 10
> > 
> > </td>
> > <td valign="top">
> > 
> > Available
> > 
> > </td>
> > <td valign="top">
> > 
> > Not available. Versions before 10 can't be recovered with checkpoint 10
> > 
> > </td>
> > </tr>
> > <tr>
> > <td valign="top">
> > 
> > 11
> > 
> > </td>
> > <td valign="top">
> > 
> > January 18
> > 
> > </td>
> > <td valign="top">
> > 
> >  
> > 
> > </td>
> > <td valign="top">
> > 
> > Available
> > 
> > </td>
> > <td valign="top">
> > 
> > Available \(checkpoint 10, versions 10 to 11 can be reapplied\)
> > 
> > </td>
> > </tr>
> > <tr>
> > <td valign="top">
> > 
> > 12
> > 
> > </td>
> > <td valign="top">
> > 
> > January 20
> > 
> > </td>
> > <td valign="top">
> > 
> >  
> > 
> > </td>
> > <td valign="top">
> > 
> > Available
> > 
> > </td>
> > <td valign="top">
> > 
> > Available \(checkpoint 10, versions 10 to 12 can be reapplied\)
> > 
> > </td>
> > </tr>
> > <tr>
> > <td valign="top">
> > 
> > 13
> > 
> > </td>
> > <td valign="top">
> > 
> > January 26
> > 
> > </td>
> > <td valign="top">
> > 
> >  
> > 
> > </td>
> > <td valign="top">
> > 
> > Available
> > 
> > </td>
> > <td valign="top">
> > 
> > Available \(checkpoint 10, versions 10 to 13 can be reapplied\)
> > 
> > </td>
> > </tr>
> > </table>

You enable *Delta Capture* while creating a local table. See [Creating a Local Table \(File\)](creating-a-local-table-file-d21881b.md).

When *Delta Capture* is switched on:

-   *Delta Capture Table* field is added and a default name for the delta capture table is defined \(Technical name + Delta\).

    > ### Example:  
    > I define the business name "My Employee Data" for my local table with delta capture enabled, the technical name is "My\_Employee\_Data". The default delta capture table name will be "My\_Employee\_Data\_Delta".

-   2 additional columns are automatically created in my table:


    <table>
    <tr>
    <th valign="top">

    Column
    
    </th>
    <th valign="top">

    Description
    
    </th>
    <th valign="top">

    Possible Values
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Change Date 
    
    </td>
    <td valign="top">
    
    The column will track the last date and time of the last change to an individual record.
    
    </td>
    <td valign="top">
    
    Current UTC timestamp. 
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Change Type
    
    </td>
    <td valign="top">
    
    This column will track the type of last change made to a record.
    
    </td>
    <td valign="top">
    
    This column will track the type of last change made to a record.When a record is inserted or updated corresponding change types are used: "*I*" for insert \(a new record is added\), "*U*" for update \(an existing record gets an updated value\). When an existing record is deleted other specific change types are used \(for example "*D*"\). Note that deleting a record will not physically delete it, so that the changes can be propagated to the different objects that consume it in delta mode. It is however filtered out when accessing the Local Table \(using the Active Records Table\). For more information on records deletion, see [Deleting Local Table \(File\) Records](deleting-local-table-file-records-6ec9b8a.md)
    
    </td>
    </tr>
    </table>
    

You can change both the business name and technical name, but you can't change the data type \(read-only\).

> ### Note:  
> -   The delta capture columns can't be set as key columns.
> 
> -   They can't be deleted if the toggle is switched on.
> -   Once the table is deployed, the toggle can't be switched off.



## Deployment and Consumption of Local Table \(File\) With Delta Capture

When a local table \(file\) with delta capture is deployed, the following objects are created and stored in the repository:

-   The table that contains the delta capture columns. The technical name ends with "Delta".

    > ### Note:  
    > This table is saved in the repository, but is deployed as a view in the database.

-   The table that contains only the active records. It excludes both the delta capture columns and the historical data versions.

The 2 objects are consumed differently by SAP Datasphere apps:

-   Most SAP Datasphere apps consume a local table with delta capture through the *Active Records* table only. In these cases, local tables behave the same way independent of whether *Delta Capture* is set to "*On*" or "*Off*". For examples in Graphical Views, SQL Views, E/R Modeler or Business Builder.
-   The following SAP Datasphere apps also interact with the Delta Capture Table that contains the delta columns:
    -   *Transformation Flow*: The delta capture table can be used by both source and target. See[Creating a Transformation Flow in a File Space](creating-a-transformation-flow-in-a-file-space-b917baf.md) 
    -   *Replication Flow*: The delta capture table can be used as target but with some restrictions, see [SAP Datasphere Targets for Replication Flows](sap-datasphere-targets-for-replication-flows-12c45eb.md).
    -   *Table Editor*: See [Preview and Edit Local Table \(File\) Data](preview-and-edit-local-table-file-data-e57e12d.md) 


> ### Note:  
> If the table is used as source or target in an object, for example in a flow, you can see it in the table editor under dependent objects. For more information, see [Review the Objects That Depend on Your Table or View](../review-the-objects-that-depend-on-your-table-or-view-ecac5fd.md).

