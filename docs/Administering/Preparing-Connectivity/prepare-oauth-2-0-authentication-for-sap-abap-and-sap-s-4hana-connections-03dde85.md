<!-- loio03dde8504a4645b08d6e4bb0d246ca19 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Prepare OAuth 2.0 Authentication for SAP ABAP and SAP S/4HANA Connections

You can use OAuth 2.0 authentication with client credentials for SAP ABAP \(on-premise\) and SAP S/4HANA connections, supporting replication flows and data flows. Using OAuth 2.0 authentication requires the set up for technical user propagation with activities in the Cloud Connector, in the ABAP on-premise system, and in SAP Datasphere.



<a name="loio03dde8504a4645b08d6e4bb0d246ca19__section_OAuth_prereq"/>

## Prerequisites

-   You have administrator rights in:
    -   Cloud Connector
    -   the ABAP on-premise system
    -   SAP Datasphere

-   You have installed Cloud Connector and added the SAP Datasphere subaccount to the Cloud Connector \(in SAP Datasphere, the subaccount information is available in <span class="FPA-icons-V3"></span> \(*System*\) ** \> ** <span class="Belize-icons"></span> \(*Administration*\) ** \> *Data Source Configuration*\).

    For more information, see [Preparing Cloud Connector Connectivity](preparing-cloud-connector-connectivity-35141e7.md).

-   You have set up Secure Network Commuications \(SNC\) between Cloud Connector and the ABAP system.

    For more information about configuring SNC, see [Initial Configuration \(RFC\)](https://help.sap.com/viewer/DRAFT/cca91383641e40ffbe03bdc78f00f681/Validation/en-US/f09eefe71d1e4d4484e1dd4b121585fb.html) in the *SAP BTP Connectivity* documentation.




<a name="loio03dde8504a4645b08d6e4bb0d246ca19__section_OAuth_client"/>

## Create an OAuth Client in SAP Datasphere

In SAP Datasphere, create an OAuth2.0 client with *Technical User* purpose.

1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(*System*\) ** \> ** <span class="Belize-icons"></span> \(*Administration*\) ** \> *App Integration*.
2.  Under *OAuth Clients* \> *Configured Clients*, select :heavy_plus_sign: *Add a New OAuth Client*.
3.  When creating the OAuth client:
    -   Select a suitable scoped role \(based on the DW Integrator role\) for accessing the data.
    -   After the client has been created and before closing the dialog, copy the secret and save it securely.
    -   > ### Note:  
        > You won't be able to copy the secret again. If you lose it, you will need to create a new client.


4.  You will require the following information later:
    -   OAuth client ID
    -   OAuth client secret
    -   Token URL \(available under <span class="FPA-icons-V3"></span> \(*System*\) ** \> ** <span class="Belize-icons"></span> \(*Administration*\) ** \> *App Integration*** \> ***OAuth Clients*\).


For more information, see [Create an OAuth2.0 Client with a Technical User Purpose](../Creating-and-Configuring-Your-Tenant/create-an-oauth2-0-client-with-a-technical-user-purpose-88b1346.md).



<a name="loio03dde8504a4645b08d6e4bb0d246ca19__section_OAuth_CC"/>

## Configure Technical User Propagation in the Cloud Connector

In the Cloud Connector Administration:

-   Establish trust to the identity provider that issues tokens for technical propagation.
-   Define a pattern identifying the user for the subject of a generated X.509 certificate, based on a specified condition.



### Establish Trust to Your Identity Provider

1.  In the Cloud Connector Administration side navigation area for your SAP Datasphere subaccount, click *Cloud To On-Premise* \> *Principal Propagation* \> ** and then click :arrows_clockwise: to add an entry for your identity provider.
2.  The *Trusted* column indicates whether the entry is trusted for technical propagation.

For more information, see [Configure Trusted Entities in the Cloud Connector](https://help.sap.com/docs/connectivity/sap-btp-connectivity-cf/set-up-trust-for-principal-propagation?version=Cloud#configure-trusted-entities-in-the-cloud-connector) in the *SAP BTP Connectivity* documentation.



### Define a Subject Pattern

1.  In the Cloud Connector Administration side navigation area, click *Configuration* \> *On-Premises* \> *Principal Propagation* \> *Subject Patterns* and click :heavy_plus_sign:.
2.  In the dialog, specify the *Condition* by selecting the following values from the dropdown: `${user_type}` `is` `Technical`
3.  In the *Subject Pattern* details, enter `${client_id}` in the *Common Name \(CN\)* field.
4.  After you have saved your subject pattern, select the pattern from the list and in the *Actions* column, click <span class="SAP-icons-V5"></span> \(Create a sample certificate\). You will use this certificate to create the user mapping in your ABAP system.
5.  Enter the OAuth client ID that you have created in SAP Datasphere, click *Generate* and save the sample certificate.

For more information, see [Configure Subject Patterns](https://help.sap.com/docs/connectivity/sap-btp-connectivity-cf/configure-subject-patterns-for-principal-propagation?version=Cloud) in the *SAP BTP Connectivity* documentation.

> ### Note:  
> Any changes to a subject pattern could affect all principle and technical user propagation via the Cloud Connector.



<a name="loio03dde8504a4645b08d6e4bb0d246ca19__section_OAuth_matching_SNC_names"/>

## Check for Matching SNC Names in Cloud Connector and in the ABAP System

Make sure that the SNC name in Cloud Connector matches the SNC name in the ABAP system. The following fields must display the same value:

-   In the Cloud Connector Administration: the *My Name* field under *Configuration* \> *On-Premises* \> *SNC*.
-   In the ABAP system: the *SNC name* field in an ACL entry in the *SNC: Access Control List \(ACL\) for Systems* \(transaction `SNC0`\). The ACL entry must have the *Entry for RFC activated* and *Entry for certificate activated* selected.



<a name="loio03dde8504a4645b08d6e4bb0d246ca19__section_OAuth_map_certificate"/>

## Map a Sample Certificate to a User in Your ABAP System

In the ABAP system, map the sample certificate to a user in your ABAP system to allow authenticating the user with a short-lived X.509 certificate issued by the Cloud Connector.

1.  In the ABAP system, open *Rule-based Certificate Mapping* \(transaction `CERTRULE`\).
2.  Upload the sample certificate that you have generated in Cloud Connector.

    For more information, see [Checking Certificates for Rule Coverage](https://help.sap.com/docs/ABAP_PLATFORM_NEW/e815bb97839a4d83be6c4fca48ee5777/1fd1aa687d1d403cb80f89eb15d2c155.html) in the *User Authentication and Single Sign-On* documentation.

3.  Create an explicit mapping to the user in your SAP ABAP system.

    For more information, see [Creating Explicit Mappings for Certificates](https://help.sap.com/docs/ABAP_PLATFORM_NEW/e815bb97839a4d83be6c4fca48ee5777/8f1aa732c9614eae91b52b836c1fb885.html) in the *User Authentication and Single Sign-On* documentation.


For more information, see:

-   [Rule-Based Mapping of Certificates](https://help.sap.com/docs/connectivity/sap-btp-connectivity-cf/rule-based-mapping-of-certificates) in the *SAP BTP Connectivity* documentation
-   [Rule-Based Certificate Mapping](https://help.sap.com/docs/ABAP_PLATFORM_NEW/e815bb97839a4d83be6c4fca48ee5777/c830fd902dc8473b9e59db1576cc784b.html) in the *User Authentication and Single Sign-On* documentation



<a name="loio03dde8504a4645b08d6e4bb0d246ca19__section_OAuth_system_mapping"/>

## Add a System Mapping to Your ABAP System in the Cloud Connector

In the Cloud Connector Administration, specify the ABAP system that you want to access from SAP Datasphere and limit the accessible resources.

1.  In the Cloud Connector Administration side navigation area for your SAP Datasphere subaccount, click *Cloud To On-Premise* \> *Access Control* \> *Mapping Virtual To Internal System* and then :heavy_plus_sign:.
2.  In the *Add System Mapping* dialog, consider the following when adding the system mapping information:
    -   In the *Back-end Type* field, select *ABAP System*.
    -   In the *Protocol* field, select *RFC SNC*.
    -   In the *Principal Type* field, select *X.509 Certificate*.
    -   In the *SNC Partner Name* field, enter the ABAP system's SNC identity name \(for example, `p:CN=SID, O=Trust Community, C=DE`\). The SNC partner name needs to contain the correct SNC identification of the ABAP system. The value can typically be found in the ABAP system instance profile parameter `snc/identity/as` \(and hence is provided per application server\).

3.  From the *Mapping Virtual To Internal System* list, select the system host you just added, and for each resource that you want to allow to be invoked on that host, click :heavy_plus_sign: in the *Resources Of *<virtual host\>** and add the required resources.

For more information, see:

-   [Configure Cloud Connector](configure-cloud-connector-f289920.md)
-   [Configure Access Cotrol \(RFC\)](https://help.sap.com/docs/connectivity/sap-btp-connectivity-cf/configure-access-control-rfc) in the *SAP BTP Connectivity* documentation



<a name="loio03dde8504a4645b08d6e4bb0d246ca19__section_OAuth_results"/>

## Results

You can now use OAuth 2.0 authentication for an *SAP ABAP* or *SAP S/4HANA* connection to the ABAP system that you have prepared with the steps above.

For more information, see:

-   [SAP ABAP Connections](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/a75c1aacf951449ba3b740c7e46da3a9.html "Use an SAP ABAP connection to access data from SAP ABAP on-premise systems through RFC or to access data from cloud source systems such as SAP S/4HANA Cloud through Web Socket RFC.") :arrow_upper_right:
-   [SAP S/4HANA On-Premise Connections](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/a49a1e3cc50f4af89711d8306bdd8f26.html "Use an SAP S/4HANA On-Premise connection to access data from SAP S/4HANA on-premise systems.") :arrow_upper_right:

