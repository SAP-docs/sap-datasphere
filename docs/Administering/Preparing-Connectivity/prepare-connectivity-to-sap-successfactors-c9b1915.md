<!-- loioc9b19156c417409b8d563cc4b56c5dc0 -->

# Prepare Connectivity to SAP SuccessFactors

To be able to successfully validate and use a connection to SAP SuccessFactors for remote tables or data flows certain preparations have to be made.

Before you can use the connection, the following is required:

-   A DW administrator has uploaded the server certificate to SAP Datasphere.

    For more information, see [Upload Certificates \(Required for Remote Tables\)](upload-certificates-required-for-remote-tables-46f5467.md).

-   When using OAuth 2.0 authorization, SAP Datasphere must be registered in SAP SuccessFactors.

    For more information, see [Registering Your OAuth2 Client Application](https://help.sap.com/viewer/d599f15995d348a1b45ba5603e2aba9b/latest/en-US/6b3c741483de47b290d075d798163bc1.html) in the *SAP SuccessFactors platform* documentation.

-   In SAP SuccessFactors IP restriction management, you have added the externally facing SAP HANA IP addresses and the outbound IP address for SAP Datasphere to the list of IP restrictions. IP restrictions are a specified list of IP addresses from which users can access your SAP SuccessFactors system.

    For more information, see:

    -   [IP Restrictions](https://help.sap.com/docs/SAP_SUCCESSFACTORS_PLATFORM/bf014ed11dae45ecae6f8c6e42fa68bb/a356e2c66c7443ceb15f8592318b5dcf.html) in the *SAP SuccessFactors platform* documentation

    -   [Finding SAP Datasphere IP addresses](finding-sap-datasphere-ip-addresses-0934f7e.md)



