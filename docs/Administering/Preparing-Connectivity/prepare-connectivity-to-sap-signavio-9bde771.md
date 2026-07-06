<!-- loio9bde7712a1ef47a18a292484284e2c0a -->

# Prepare Connectivity to SAP Signavio

To be able to successfully validate and use a connection to SAP Signavio, certain preparations have to be made.



<a name="loio9bde7712a1ef47a18a292484284e2c0a__section_y23_vcw_z2c"/>

## Replication Flows

Before you can use the connection to add target objects to a replication flow, the following is required:



### SAP Datasphere

1.  Create a scoped role based on the *DW Integrator* template \(privilege *Data Warehouse Data Integration* with *Read* permission is required\), and add the space in which the SAP Signavio connection will be created to the scoped role.

    For more information, see:

    -   [Create a Scoped Role](../Managing-Users-and-Roles/create-a-scoped-role-to-assign-privileges-to-users-in-spaces-b5c4e0b.md#loiob5c4e0b6c462414783ebbfc053815521__section_z4m_mpj_zyb)
    -   [Add Spaces to a Scoped Role](../Managing-Users-and-Roles/create-a-scoped-role-to-assign-privileges-to-users-in-spaces-b5c4e0b.md#loiob5c4e0b6c462414783ebbfc053815521__section_pr1_5pj_zyb)

2.  Create the connection to the source of the replication flow \(SAP S/4HANA, for example\) in the same space which you will use to create the connection to SAP Signavio.

    For more information, see [Create a Connection](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/c2165842082c43fc85bad9f0c97572bb.html "Create a connection to allow users assigned to a space to use the connected source or target for data modeling and data access in SAP Datasphere.") :arrow_upper_right:.

3.  Create an OAuth 2.0 client with a technical user purpose and assign the scoped integrator role that has been created before.

    The OAuth client is required to set up the required 1:1 mapping between the SAP Datasphere tenant and the SAP Signavio tenant.

    When creating the OAuth client, make a note of the following information that is required to register the OAuth client in SAP Signavio:

    -   OAuth Client ID
    -   OAuth Client Secret

        > ### Note:  
        > Immediately copy the secret. Once you close the OAuth creation dialog, the secret is no longer available, and you will need to create a new client.

    -   Service Root \(URL root of the *App Integration* page where you create the OAuth client\)
    -   OAuth2SAML Token URL

    For more information, see [Create an OAuth2.0 Client with a Technical User Purpose](../Creating-and-Configuring-Your-Tenant/create-an-oauth2-0-client-with-a-technical-user-purpose-88b1346.md).




### SAP Signavio

1.  Register the OAuth 2.0 client by creating a connection with connection type *SAP Datasphere Replication Flow*.

    For more information, see [Synchronizing Data with SAP Datasphere Replication Flow](https://help.sap.com/docs/signavio-process-intelligence/user-guide/synchronizing-data-with-sap-datasphere-replication-flow) in the *SAP Signavio Process Intelligence* documentation.


**Related Information**  


[SAP Signavio Connections](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/4c367de075a44ad7b7a6db576a4a9c82.html "Use the connection to securely integrate SAP systems such as SAP S/4HANA on-premise with SAP Signavio using replication flows for efficient and scalable data replication to SAP Signavio Process Intelligence.") :arrow_upper_right:

