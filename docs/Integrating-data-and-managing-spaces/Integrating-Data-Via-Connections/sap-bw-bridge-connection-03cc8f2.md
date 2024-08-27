<!-- loio03cc8f27d3a44aabad3debaa79be0216 -->

# SAP BW Bridge Connection

In the SAP BW bridge space, a SAP BW bridge connection is being generated.

Technically, it comprises two connections:

-   An HTTP ABAP connection to retrieve metadata from the SAP BW bridge
-   A SAP HANA smart data access connection to retrieve the data from the SAP BW bridge

You can only display the connection. Here, you can copy the SAP BW service key, which you will need to enter when you create an SAP BW bridge project in the SAP BW Bridge Modeling Tools. For more information, see [Copy the SAP BW Service Key](https://help.sap.com/viewer/e2d2b48377c14490b55466b5f1872640/DEV_CURRENT/en-US/ddee32782c3a4b3cb7ee2fcee716d984.html "You need the SAP BW service key for creating a SAP BW bridge project or an ABAP Cloud project in the SAP BW Bridge Modeling Tools.") :arrow_upper_right:.



<a name="loio03cc8f27d3a44aabad3debaa79be0216__section_vbh_qws_1rb"/>

## Restrictions

The connection type SAP BW bridge connection doesn’t show up in any other space, it cannot be modified, and you cannot create such a connection yourself.

SAP BW bridge connections only support remote tables and model import. Data flows and replication flows are not supported.

