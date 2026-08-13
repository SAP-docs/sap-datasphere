<!-- loioc9b19156c417409b8d563cc4b56c5dc0 -->

# Prepare Connectivity to SAP SuccessFactors

To be able to successfully validate and use a connection to SAP SuccessFactors for remote tables or data flows certain preparations have to be made.

Before you can use the connection, the following is required:

-   A DW administrator has uploaded the server certificate to SAP Datasphere.

    Example for Certificate Download Site: `https://performancemanager4.successfactors.com`

    For more information, see [Manage Certificates](manage-certificates-46f5467.md).

-   When using OAuth 2.0 for authentication, a SAML assertion for requesting an OAuth access token is required for accessing SAP SuccessFactors. You have two options to generate the SAML assertion and provide it to the connection:

    -   \(Recommended\) You can let SAP Datasphere dynamically generate and fetch the SAML assertion, and automatically rotate SAML assertions when they expire. This requires an initial configuration of the necessary components including Identity Authentication in SAP Cloud Identity Services and SAP SuccessFactors. The configuration provides you with information required when creating the connection.

        For more information, see [Configuring Dynamic Generation of SAML Assertions for SAP SuccessFactors Connections](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/63c8260a7f574e6e8e3c386656c93b00.html "Configure automated, dynamic generation and rotation of Security Assertion Markup Language (SAML) assertions for accessing SAP SuccessFactors APIs. For the generation of SAML assertions, SAP Datasphere is using the Identity Authentication service of SAP Cloud Identity Services as identity provider. Configuration steps are required in Identity Authentication and SAP SuccessFactors.") :arrow_upper_right:.

    -   You can manually generate a SAML assertion, for example using an SAP-provided offline tool or an external identity provider, and manually enter it in the connection configuration. The lifetime of SAML assertions generated in this way typically is short, and you need to ensure that whenever you validate or use the connection, you have entered a valid SAML assertion in the connection configuration.

        Manual generation of SAML assertion requires registering SAP Datasphere as OAuth2 client application in SAP SuccessFactors.

        For more information, see the *SAP SuccessFactors platform* documentation:

        -   [Generating a SAML Assertion](https://help.sap.com/docs/SAP_SUCCESSFACTORS_PLATFORM/d599f15995d348a1b45ba5603e2aba9b/4e27e8f6ae2748ab9f23228dd6a31b06.html)
        -   [Registering Your OAuth2 Client Application](https://help.sap.com/viewer/d599f15995d348a1b45ba5603e2aba9b/latest/en-US/6b3c741483de47b290d075d798163bc1.html)


-   In SAP SuccessFactors IP restriction management, you have added the externally facing SAP HANA IP addresses and the outbound IP address for SAP Datasphere to the list of IP restrictions. IP restrictions are a specified list of IP addresses from which users can access your SAP SuccessFactors system.

    For more information, see:

    -   [IP Restrictions](https://help.sap.com/docs/SAP_SUCCESSFACTORS_PLATFORM/bf014ed11dae45ecae6f8c6e42fa68bb/a356e2c66c7443ceb15f8592318b5dcf.html) in the *SAP SuccessFactors platform* documentation

    -   [Obtain SAP Datasphere IP addresses For Allowlisting in Remote Systems](obtain-sap-datasphere-ip-addresses-for-allowlisting-in-remote-systems-0934f7e.md)



**Related Information**  


[SAP SuccessFactors Connections](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/39df02030d4b411487bacecf9afea4e8.html "Use an SAP SuccessFactors connection to access employee-related data in SAP SuccessFactors.") :arrow_upper_right:

