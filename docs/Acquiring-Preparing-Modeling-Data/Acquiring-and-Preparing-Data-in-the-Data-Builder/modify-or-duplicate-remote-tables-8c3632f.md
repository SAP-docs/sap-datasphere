<!-- loio8c3632f28dc94e068dbdab8fe9bbeeb9 -->

# Modify or Duplicate Remote Tables

From the remote table editor, you can change the remote table connection and/or the remote table source object. You can also create a copy of an existing remote table.

In some cases, you might need to change the connection of your remote table, or to change the remote table source object. For example, if for performance reasons you have decided to split one connection into several ones, or you have decided to move on remote table from one connection to another. It might be also helpful to create a copy of an existing remote table, if you made changes in your remote table but want to keep the 2 versions of your remote table, or you want to have several identical remote tables with different filter conditions. Note that for remote tables connected via SAP HANA smart data access, only one remote table per source entity of a connection can be in status *Replicated*, though.

> ### Note:  
> The remote table must be in *Data Access* = *Remote* 

From the *Data Builder*, open the remote table in the table editor.



<a name="loio8c3632f28dc94e068dbdab8fe9bbeeb9__section_ozd_5vh_kxb"/>

## Changing the Connection and/or the Remote Table Source Object.

In the *Remote* section of your remote table, click *Change Remote Table Source*. A wizard opens and allows you to change the connection and/or the remote table source object in 3 steps:

1.  *Connections*: Change the connection. All the connections available in your space are displayed. Select the new connection and click *Next Step* to move to the *Source Object* section.

    > ### Note:  
    > If you want to change only the remote table source object, you can ignore this step by reselecting the current connection and click *Next Step*.

2.  *Source Object*: Change the remote table source. If you want to change the remote table source, you can do so by selecting *Change Remote Table Source*. You can then browse through schemas available for the selected connection \(on the right side of the screen\), and their associated tables \(left side of the screen\).

    > ### Note:  
    > Schemas only exist for SAP HANA smart data access-based connections and SAP HANA smart data integration-based database connections.

    Select the relevant schema and table you need and click *Next Step*.

    > ### Note:  
    > If you want to change only the connection, you can ignore this step and click *Next Step*.

3.  *Review*: Review your changes and confirm. When confirming a validation is performed to check any inconsistencies in the remote table structure. You’ll get information in the validation section.

    > ### Note:  
    > If the changes affect the remote source type, additional validation checks are performed, which could block the deployment. For example if you if you switch from an SAP HANA smart data integration connection into an SAP HANA smart data access connection:
    > 
    > -   You must remove the remote table filter conditions as they are not supported by an SAP HANA smart data access connection.
    > 
    > -   You must remove partitioning on non-key columns as they are not supported by an SAP HANA smart data access connection.

    Once you have confirmed your changes, a refresh is automatically done and you can see the changes in the remote table editor. You can then save your changes and redeploy the remote table.




<a name="loio8c3632f28dc94e068dbdab8fe9bbeeb9__section_t1t_jyh_kxb"/>

## Creating a Copy of an Existing Remote Table

Copying your remote table can be helpful in some cases. For example if you made changes in your remote table but want to keep the 2 versions of your remote table. Or you want to have several identical remote tables with different filter condition. Then you can use the Save as option. This option allows you to create a copy of an existing table with a new technical name.

From the *Data Builder*, open the relevant remote table in the table editor. Select*Save As*.

> ### Note:  
> For remote tables connected via SAP HANA smart data access, only one remote table per source entity of one connection can be in status *Replicated* \(Snapshot or Real-Time\). For more information, see [Monitoring Remote Tables](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/4dd95d7bff1f48b399c8b55dbdd34b9e.html "In the Remote Tables monitor, you can find a remote table monitor per space. Here, you can copy data from remote tables that have been deployed in your space into SAP Datasphere, and you can monitor the replication of the data. You can copy or schedule copying the full set of data from the source, or you can set up replication of data changes in real-time via change data capturing (CDC).") :arrow_upper_right:.

