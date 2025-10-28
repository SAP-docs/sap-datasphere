<!-- loio46f5467adc5242deb1f6b68083e72994 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Manage Certificates for Connections

For connections secured by leveraging HTTPS as the underlying transport protocol \(using SSL/TLS transport encryption\), the server certificate must be trusted. To import a certificate into the SAP Datasphere trust chain, obtain the certificate from the target endpoint and upload it to SAP Datasphere.



<a name="loio46f5467adc5242deb1f6b68083e72994__prereq_d3y_chy_1nb"/>

## Prerequisites

In addition, download the required SSL/TLS certificate from an appropriate website. As one option for downloading, common browsers provide functionality to export these certificates.

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



## Procedure

1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(*System*\) ** \> ** :wrench: \(*Configuration*\) ** \> *Security*.

2.  Click <span class="FPA-icons-V3"></span> Add Certificate.

3.  In the *Upload Certificate* dialog, browse your local directory and select the certificate.

4.  Enter a description to provide intelligible information on the certificate, for example to point out to which connection type the certificate applies.

5.  Choose *Upload*.




<a name="loio46f5467adc5242deb1f6b68083e72994__result_fxs_jrt_bnb"/>

## Results

In the overview, you can see the certificate with its creation and expiry date. From the overview, you can delete certificates if required.

