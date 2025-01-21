<!-- loio2ace657356d54199b0b87d2327b1a70b -->

# Creating Spaces and Allocating Storage

Users with an administrator role can create spaces, allocate disk and memory storage to them, and set their priorities and workload limits for statements.

All data acquisition, preparation, and modeling in SAP Datasphere happens inside spaces. A space is a secure area - space data cannot be accessed outside the space unless it is shared to another space or exposed for consumption.

An administrator must create one or more spaces. They allocate disk and memory storage to the space, set its priority, and can limit how much memory and how many threads its statements can consume.

> ### Note:  
> You can also create a file space \(a space with SAP HANA data lake files storage\) in the object store, allocate compute resources and assign one or more users to allow them to start acquiring and preparing data. File spaces are intended for loading and preparing large quantities of data in an inexpensive inbound staging area. See [Create a File Space to Load Data in the Object Store](create-a-file-space-to-load-data-in-the-object-store-9474446.md).

If the administrator assigns one or more space administrators via a scoped role, they can then manage users, create connections to source systems, secure data with data access controls, and manage other aspects of the space \(see [Managing Your Space](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/268ea7e3e8d448deaab420219477064d.html "Users with a space administrator role are responsible for controlling user access to their space, and monitoring and otherwise managing the space.") :arrow_upper_right:\).

