<!-- loio2267a9f6a5724ec0ae5632db4f9f70e5 -->

# Using an Object Without Primary Key As the Source

If certain conditions are met, you can use objects that do not have a primary key as the source for a replication flow.

This applies to the following types of **source objects**:

-   CDS views

-   ODP artifacts


The objects must have load type *Initial Only*. \(Delta loading is not supported.\)

**Existing tables** can be used as **targets** if they have a column \_\_load\_package\_id \(as explained below\). **Local tables** can only be used as targets if delta capturing is **not** enabled.

For some targets, the system automatically adds a **technical target column**. For HANA and HANA Cloud targets, this column is called "\_\_load\_package\_id" and has data type binary\(\>=256\). For other targets, it is called "\_\_load\_record\_id" and has data type string\(44\). This column provides a unique identifier for each record, which serves as a replacement for the primary key in duplicate handling and for other technical purposes. On the *Projections* tab, this column is always shown at the end and in read only mode. You can't rename it, remove or modify its data type, or reorder it.

For Kafka tables, no technical target column is created because the target table always gets newly created.

> ### Note:  
> Multiple replications \(for example due to restarting or undeploying and redeploying a replication flow\) result in different \_\_load\_record\_id values for the same source record.

