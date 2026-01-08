<!-- loiod570eee0045a4b9ab5d47ac70140d60a -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Reusing Objects as Source or Target in Several Replication Flows

You can reuse certain objects as sources or targets in multiple replication flows, but you need to consider the following information:

-   If a local table is already used as a source in a replication flow \(with or without delta capture enabled\), it cannot be used as a target in another replication flow. However, a table that is used as a target can be reused as a source in another replication flow.

-   Multiple replication flows targeting the same table are not supported.
-   Replicating data from SAP Datasphere to SAP Datasphere is not supported.




<a name="loiod570eee0045a4b9ab5d47ac70140d60a__section_idp_vhh_vgc"/>

## Replicating a Single Source Object to Multiple Targets

You can replicate one source object to the same or different target systems.

> ### Restriction:  
> -   You must create one replication flow per replication.
> -   You can't deploy a replication flow that is reusing objects from:
>     -   SAP HANA Cloud, data lake files.
>     -   ABAP SLT source. For ABAP SLT, only one SLT mass transfer ID per replication can be used. If the SLT source is reused for another replication, another mass transfer ID is required. For more information, see [2329159.](https://me.sap.com/notes/2329159.)



<a name="loiod570eee0045a4b9ab5d47ac70140d60a__section_rpd_5lh_vgc"/>

## Reusing a Target Table of a Replication Flow as a Source Table in Another Replication Flow

You can reuse a target local table \(with or without delta capture enabled\) from one replication flow as the source table in another replication flow.



## Example

You have created a replication flow “RF1”, which has a table “XY” as source table and table “ABC” as target table. Once RF1 is successfully run and deployed, you create a replication flow “RF2”, which has the table “ABC” \(target of replication 1\) as source table and table ZZZ as target table.

As a consequence:

-   Table ABC is used as target by RF1 and as source by RF2.
-   RF1 has a "Dependent Replication Flow", which is RF2.

> ### Caution:  
> RF2 \(dependent replication flow\) cannot be run until RF1 \(source replication flow\) run is complete.

You can display if a replication flow has a dependent replication flow in 2 ways:

-   At the replication flow level: From the replication flow editor, click <span class="SAP-icons-V5"></span> \(View Dependent Replication Flows\) in the toolbar.

-   At an object level: Select the replication object and click "View Dependent Replication Flows".

    > ### Note:  
    > Dependent replication flows that have been stopped are not displayed.


