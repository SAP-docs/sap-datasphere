<!-- loio46f5467adc5242deb1f6b68083e72994 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Manage Certificates for Connections 

For connections secured by leveraging HTTPS as the underlying transport protocol \(using SSL/TLS transport encryption\), the server certificate must be trusted. To import a certificate into the SAP Datasphere trust chain, obtain the certificate from the target endpoint and upload it to SAP Datasphere.



<a name="loio46f5467adc5242deb1f6b68083e72994__prereq_d3y_chy_1nb"/>

## Prerequisites

To manage certificates, you must have a global role that grants you the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *System Information* \(`-RU-----`\) - To access the *Configuration* area in the *System* tool.

The *DW Administrator* global role, for example, grants these privileges. For more information, see [Privileges and Permissions](../Managing-Users-and-Roles/privileges-and-permissions-d7350c6.md) and [Standard Roles Delivered with SAP Datasphere](../Managing-Users-and-Roles/standard-roles-delivered-with-sap-datasphere-a50a51d.md). 

In addition, download the required TLS certificate from an appropriate website. As one option for downloading, common browsers provide functionality to export these certificates.

> ### Note:  
> -   Only X.509 Base64-encoded certificates enclosed between "-----BEGIN CERTIFICATE-----" and "-----END CERTIFICATE-----" are supported. The common filename extension for the certificates is .pem \(privacy-enhanced mail\). We also support filename extensions .crt and .cer.
> 
> -   A certificate used in one region might differ from those used in other regions. Also, some sources, such as Amazon Athena, might require more than one certificate.
> 
> -   Remember that all certificates can expire.
> 
> -   If you have a problem with a certificate, please contact your cloud company for assistance.
> 
>     You can create connections to remote systems which require a certificate upload without having uploaded the necessary certificate. Validating a connection without valid server certificate will fail though, and you won't be able to use the connection.



## Context

In addition to manage TLS server certificates in the *Configuration* app, you can also:

-   List, upload, and delete them using the `datasphere` command line interface \(see [Manage TLS Server Certificates via the Command Line](https://help.sap.com/viewer/d0ecd6f297ac40249072a44df0549c1a/cloud/en-US/6306da2bbeb04e4fbd944c2dce08629f.html "Users with a DW Administrator role (or equivalent privileges) can list, upload, and delete TLS server certificates via the command line.") :arrow_upper_right:\).
-   List, upload, and delete them using a REST API \(see [Manage Connectivity via REST APIs](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/5aafe32418b14f7e99528b49f48bd3ac.html "You can manage TLS server certificates and connections via the Certificates and Connections REST APIs. Creating and editing connections via the API is supported for SAP SuccessFactors connections only.") :arrow_upper_right:\).



## Procedure

1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(*System*\) ** \> ** :wrench: \(*Configuration*\) ** \> *Security*.

2.  Click <span class="FPA-icons-V3"></span> Add Certificate.

3.  In the *Upload Certificate* dialog, browse your local directory and select the certificate.

4.  Enter a description to provide intelligible information on the certificate, for example to point out to which connection type the certificate applies.

5.  Choose *Upload*.




<a name="loio46f5467adc5242deb1f6b68083e72994__result_fxs_jrt_bnb"/>

## Results

In the overview, you can see the certificate with its creation and expiry date. From the overview, you can delete certificates if required.

