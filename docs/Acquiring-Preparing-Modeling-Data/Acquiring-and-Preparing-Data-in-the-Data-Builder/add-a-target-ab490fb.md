<!-- loioab490fb4d083442197e2ba3b92079734 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Add a Target

Select a target \(connection and container\) to define the target environment for your replication flow.



<a name="loioab490fb4d083442197e2ba3b92079734__context_rr5_54f_vvb"/>

## Context

-   Connections are created by your system administration. You can only use a target if a connection has been created for it in your space and if you have the necessary authorizations. For more information about connections and connection types, see [Integrating Data via Connections](https://help.sap.com/docs/SAP_DATASPHERE/be5967d099974c69b77f4549425ca4c0/eb85e157ab654152bd68a8714036e463.html).

-   Containers are the parent objects that hold the data.




## Procedure

1.  Choose <span class="FPA-icons-V3"></span> \(Browse target connections\). A list of available target connections appears.

2.  Select the relevant one for your use case.

3.  If you replicate to the local repository \(SAP Datasphere\), the target container is automatically defined as the space you are in, and the data is replicated to a local table. If you want to use load type *Initial and Delta*, the local table must support delta capturing. For more information, see [Capturing Delta Changes in Your Local Table](capturing-delta-changes-in-your-local-table-154bdff.md).

    For any other target, click *Browse target container*. A list of available containers appears. Select the relevant one for your use case.

    To narrow down the selection, start typing a part of the container name in the *Search* field.

4.  Review the target settings and properties and change or complete them as appropriate.

    For more information, see [Configure Your Replication Flow](configure-your-replication-flow-3f5ba0c.md).


