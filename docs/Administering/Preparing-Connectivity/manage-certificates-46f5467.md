<!-- loio46f5467adc5242deb1f6b68083e72994 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Manage Certificates 

Upload certificates and select their purpose: Choose *TLS Server* to secure connections or *X.509 Client \(Open SQL\)* to enable X.509 client certificate-based authentication for Open SQL database users.



<a name="loio46f5467adc5242deb1f6b68083e72994__prereq_d3y_chy_1nb"/>

## Prerequisites

To manage certificates, you must have a global role that grants you the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *System Information* \(`-RU-----`\) - To access the *Configuration* area in the *System* tool.

The *DW Administrator* global role, for example, grants these privileges. For more information, see [Privileges and Permissions](../Managing-Users-and-Roles/privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](../Managing-Users-and-Roles/standard-roles-delivered-with-sap-datasphere-a50a51d.md). 



## Context

You can upload certificates for the following purposes:

-   *TLS Server* purpose: For connections secured by leveraging HTTPS as the underlying transport protocol \(using SSL/TLS transport encryption\), the server certificate must be trusted.
-   *X.509 Client \(Open SQL\)* purpose: For Open SQL database users with X.509 client certificate-based authentication, upload the X.509 root certificate \(root CA\) from your organization's certificate authority. A space administrator can then create a database user with this authentication type. For more information, see [Create a Database User](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/STABI/en-US/798e3fd6707940c3bd2219b2d1ebaac2.html "Users with a space administrator role can create database users, granting them privileges to read from and/or write to an Open SQL schema with restricted access to the space schema.") :arrow_upper_right:.

To import a certificate into the SAP Datasphere trust chain, obtain the certificate from the target endpoint and upload it to SAP Datasphere:

-   *TLS Server* purpose: Download the required certificate from an appropriate website. As one option for downloading, common browsers provide functionality to export these certificates.
-   *X.509 Client \(Open SQL\)* purpose: Obtain the required root CA from your organization's internal public key infrastructure \(PKI\) or certificate authority \(CA\).

For the certificates, consider the following:

-   Only X.509 Base64-encoded certificates enclosed between "-----BEGIN CERTIFICATE-----" and "-----END CERTIFICATE-----" are supported. The common filename extension for the certificates is .pem \(privacy-enhanced mail\). We also support filename extensions .crt and .cer.

-   Remember that all certificates can expire.

-   If you have a problem with a certificate, please contact your cloud company for assistance.

-   *TLS Server* purpose:
    -   A server certificate used in one region might differ from those used in other regions. Also, some sources, such as Amazon Athena, might require more than one certificate.

    -   You can create connections to remote systems which require a certificate upload without having uploaded the necessary certificate. Validating a connection without valid server certificate will fail though, and you won't be able to use the connection.


-   *X.509 Client \(Open SQL\)* purpose:
    -   The X.509 root certificate \(root CA\) requires the extension `Basic Constraints: CA:TRUE` to let SAP HANA recognize it as a certificate authority. If the extension is missing or set to false, database user authentication will fail.


In addition to managing TLS server certificates in the *Configuration* app, you can also:

-   List, upload, and delete them using the `datasphere` command line interface \(see [Managing TLS Server Certificates via the Command Line](https://help.sap.com/viewer/7e55516989bd4d04a4c461a0e55fefc9/DEV/en-US/6306da2bbeb04e4fbd944c2dce08629f.html "You can use the datasphere command line interface to list, upload, and delete TLS server certificates.") :arrow_upper_right:\).
-   List, upload, and delete them using a REST API \(see [Managing Connections via the REST API](https://help.sap.com/viewer/7e55516989bd4d04a4c461a0e55fefc9/DEV/en-US/5aafe32418b14f7e99528b49f48bd3ac.html "You can manage connections via the Connections REST API. Creating and editing connections via the API is supported for SAP SuccessFactors connections only.") :arrow_upper_right:\).



## Procedure

1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(*System*\) ** \> ** :wrench: \(*Configuration*\) ** \> *Security*.

2.  In the *Certificates* section, click <span class="FPA-icons-V3"></span> Add Certificate.

3.  In the *Upload Certificate* dialog, provide the following and choose *Upload*:

    1.  Browse your local directory and select the certificate.

    2.  Select the purpose for which the certificate is required.

    3.  Enter a description to provide intelligible information on the certificate, for example to point out to which connection type the certificate applies.





<a name="loio46f5467adc5242deb1f6b68083e72994__result_fxs_jrt_bnb"/>

## Results

In the overview, you can see the certificate with its purpose and its creation and expiry date. From the overview, you can delete certificates if required.

