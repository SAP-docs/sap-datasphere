<!-- loio46f5467adc5242deb1f6b68083e72994 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Upload Certificates \(Required for Remote Tables\)

To enable a secure SSL/TLS-based connection for a connection type that supports remote tables but doesn't use a Data Provisioning Agent, you need to upload a server certificate to SAP Datasphere.



<a name="loio46f5467adc5242deb1f6b68083e72994__prereq_d3y_chy_1nb"/>

## Prerequisites

If you want to create a connection to any of the following sources, you have downloaded the required SSL certificate from an appropriate website. As one option for downloading, common browsers provide functionality to export these certificates. Examples for HTTPS secured websites offering certificates for secure communication are:


<table>
<tr>
<th valign="top">

Source

</th>
<th valign="top">

Via

</th>
<th valign="top">

Examples for Certificate Download Sites

</th>
</tr>
<tr>
<td valign="top">

Amazon Athena

</td>
<td valign="top">

SAP HANA Smart Data Access \(using HTTP-based REST APIs\)

</td>
<td valign="top">

`https://aws.amazon.com/`

<code>https://s3.<i class="varname">&lt;region&gt;</i>.amazonaws.com</code>

> ### Note:  
> For Amazon Athena, two certificates are required, one for Amazon Athena and one for Amazon Simple Storage Service. Region-specific certificates might be required for Amazon Athena.
> 
> Alternatively, if the common root CA certificate contains trust for both endpoints, Amazon Athena and Amazon Simple Storage Service \(API/Athena and the Data/S3\), you can upload the root certificate.



</td>
</tr>
<tr>
<td valign="top">

Google BigQuery

</td>
<td valign="top">

SAP HANA Smart Data Access \(using HTTP-based REST APIs\)

</td>
<td valign="top">

`https://www.google.com/`

</td>
</tr>
<tr>
<td valign="top">

SAP HANA Cloud

</td>
<td valign="top">

SAP HANA Smart Data Access \(using the ODBC protocol\)

</td>
<td valign="top">

In your command line interface, enter the following command to download the DigiCert SSL certificate:

```
curl -O https://cacerts.digicert.com/DigiCertGlobalRootCA.crt.pem
```



</td>
</tr>
<tr>
<td valign="top">

SAP HANA \(on-premise\)

</td>
<td valign="top">

SAP HANA Smart Data Access \(using the ODBC protocol\)

</td>
<td valign="top">

not applicable

</td>
</tr>
<tr>
<td valign="top">

Generic OData

</td>
<td valign="top">

SAP HANA Smart Data Integration \(using the OData protocol for direct connection toSAP Datasphere\)

</td>
<td valign="top">

not applicable

</td>
</tr>
<tr>
<td valign="top">

SAP SuccessFactors for Analytical Dashboards

</td>
<td valign="top">

SAP HANA Smart Data Integration\(using the OData protocol for direct connection toSAP Datasphere\)

</td>
<td valign="top">

`https://performancemanager4.successfactors.com`

</td>
</tr>
</table>

> ### Note:  
> -   Only X.509 Base64-encoded certificates enclosed between "-----BEGIN CERTIFICATE-----" and "-----END CERTIFICATE-----" are supported. The common filename extension for the certificates is .pem \(Privacy-enhanced Electronic Mail\). We also support filename extensions .crt and .cer.
> 
> -   A certificate used in one region might differ from those used in other regions. Also, some sources, such as Amazon Athena, might require more than one certificate.
> 
> -   Remember that all certificates can expire.
> 
> -   If you have a problem with a certificate, please contact your cloud company for assistance.



<a name="loio46f5467adc5242deb1f6b68083e72994__context_l34_gwt_bnb"/>

## Context

You can create connections for sources which require a certificate without having uploaded the necessary certificate. Validating a connection without valid server certificate will fail though, and you won't be able to use the connection.



## Procedure

1.  In the side navigation area, click <span class="FPA-icons"></span> \(*System*\) ** \> ** :wrench: \(*Configuration*\) ** \> *Security*.

2.  Click <span class="FPA-icons"></span> Add Certificate.

3.  In the *Upload Certificate* dialog, browse your local directory and select the certificate.

4.  Enter a description to provide intelligible information on the certificate, for example to point out to which connection type the certificate applies.

5.  Choose *Upload*.




<a name="loio46f5467adc5242deb1f6b68083e72994__result_fxs_jrt_bnb"/>

## Results

In the overview, you can see the certificate with its creation and expiry date. From the overview, you can delete certificates.

