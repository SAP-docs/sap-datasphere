<!-- loiob9b5579054df48c39381d5b17286bf21 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Upload Third-Party ODBC Drivers \(Required for Data Flows\)

To enable access to a non-SAP database via ODBC to use it as a source for data flows, you need to upload the required ODBC driver files to SAP Datasphere.



<a name="loiob9b5579054df48c39381d5b17286bf21__section_tqp_kfh_2mb"/>

## Prerequisites

In addition, prepare the driver files:

-   Search for the required driver files in the internet, make sure you have selected the correct driver files \(identified by their SHA256-formatted fingerprint\) and download them from an appropriate web page \(see below\).

-   Ensure you have a valid license for the driver files.




<a name="loiob9b5579054df48c39381d5b17286bf21__section_k3n_hzn_tsb"/>

## Context

Drivers are required for the following connection types \(if several driver versions are supported, we recommend to use the newest supported version mentioned below\):


<table>
<tr>
<th valign="top">

Connection Type

</th>
<th valign="top">

Driver to be uploaded

</th>
<th valign="top">

Download Site

</th>
</tr>
<tr>
<td valign="top" rowspan="2">

[Amazon Redshift Connections](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/8b132061d4e149d9a16b3576dda1f613.html "Use an Amazon Redshift connection to access data from Amazon Redshift 8.x databases.") :arrow_upper_right:

</td>
<td valign="top">

AmazonRedshiftODBC-64-bit-1.4.11.1000-1.x86\_64.rpm \(SHA256 fingerprint: 6d811e2f198a030274bf9f099d4c828b1b071b78e99432eee1531d4988768a22\)

</td>
<td valign="top" rowspan="2">

`https://docs.aws.amazon.com` 

</td>
</tr>
<tr>
<td valign="top">

AmazonRedshiftODBC-64-bit-1.4.65.1000-1.x86\_64.rpm \(SHA256 fingerprint: ee79a8d41760a90b6fa2e1a074e33b0518e3393afd305f0bee843b5393e10df0\)

</td>
</tr>
<tr>
<td valign="top">

[Oracle Connections](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/c73ae0601d364f47830d339b6e86b7e8.html "Use the connection to connect to and access data from an Oracle database (on-premise).") :arrow_upper_right:

</td>
<td valign="top">

instantclient-basiclite-linux.x64-19.17.0.0.0dbru.zip \(SHA256 fingerprint: ea4a9557c6355f5b56b648b7dff47db79a1403b7e9f7abeca9e1a0e952498e13\)

> ### Note:  
> -   Make sure to select the *Basic Light* package zip file. The package applies to all versions supported by the Oracle connection type \(Oracle 12c, Oracle 18c, and Oracle 19c\).
> 
> -   Additional files are required if SSL is used:
> 
>     -   oraclepki.jar \(SHA256 fingerprint: e408e7ae67650917dbce3ad263829bdc6c791d50d4db2fd59aeeb5503175499b\)
>     -   osdt\_cert.jar \(SHA256 fingerprint: 6b152d4332bd39f258a88e58b9215a926048d740e148971fe1628b09060176a8\)
>     -   osdt\_core.jar \(SHA256 fingerprint: c25e30184bb94c6da1227c8256f0e1336acb97b29229edb4aacf27167b96075e\)
> 
> -   Before uploading the files, you must rename them following the names already indicated: oraclepki.jar, osdt\_cert.jar, osdt\_core.jar.



</td>
<td valign="top">

Driver: `https://download.oracle.com/otn_software/linux/instantclient/1917000/instantclient-basiclite-linux.x64-19.17.0.0.0dbru.zip`

Additional files if SSL is used:

-   `https://repo1.maven.org/maven2/com/oracle/database/security/oraclepki/19.17.0.0/oraclepki-19.17.0.0.jar`
-   `https://repo1.maven.org/maven2/com/oracle/database/security/osdt_core/19.17.0.0/osdt_core-19.17.0.0.jar`
-   `https://repo1.maven.org/maven2/com/oracle/database/security/osdt_cert/19.17.0.0/osdt_cert-19.17.0.0.jar`



</td>
</tr>
<tr>
<td valign="top" rowspan="2">

[Google BigQuery Connections](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/30ed77de13864368bdc596099b37ed70.html "Use the connection to connect to and access data from Google BigQuery.") :arrow_upper_right:

</td>
<td valign="top">

SimbaODBCDriverforGoogleBigQuery\_2.3.1.1001-Linux.tar.gz \(SHA256 fingerprint: abf4551d621c26f4fa30539e7ece2a47daaf6e1d67c59e5b7e79c43a3335018f\)

</td>
<td valign="top">

`https://storage.googleapis.com/simba-bq-release/odbc/SimbaODBCDriverforGoogleBigQuery_2.3.1.1001-Linux.tar.gz`

</td>
</tr>
<tr>
<td valign="top">

SimbaODBCDriverforGoogleBigQuery\_3.0.0.1001-Linux.tar.gz \(SHA256 fingerprint: 58d3c9acfb93f0d26c081a230ff664a16c8544d567792ebc5436beb31e9e28e4\)

</td>
<td valign="top">

`https://storage.googleapis.com/simba-bq-release/odbc/SimbaODBCDriverforGoogleBigQuery_3.0.0.1001-Linux.tar.gz`

</td>
</tr>
</table>

When uploading the drivers, they are identified by their SHA256-formatted fingerprint. You can verify the fingerprint with the following command:

-   Windows 10: In PowerShell, run the following command:

    `Get-Filehash <driver file> -Algorithm SHA256`

-   Linux/MacOS: In a unix-compliant shell, run the following command:

    `shasum -a 256 <driver file>`




<a name="loiob9b5579054df48c39381d5b17286bf21__section_ihl_rfh_2mb"/>

## Upload a Driver

Perform the following steps before creating the first Amazon Redshift, Oracle, or Google BigQuery connection that you want to use for data flows.

1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(*System*\) ** \> ** :wrench: \(*Configuration*\) ** \> *Data Integration*.

2.  Go to *Third-Party Drivers* and choose <span class="FPA-icons-V3"></span> Upload.

3.  In the following dialog box, choose *Browse* to select the driver file from your download location.

    > ### Note:  
    > The fingerprint of the driver file name to be uploaded must match the fingerprint mentioned above.

4.  Choose *Upload*.

5.  Choose <span class="FPA-icons-V3"></span> sync to synchronize the driver with the underlying component. Wait for about 5 to 10 minutes to finish synchronization before you start creating connections or using data flows with the connection.

    > ### Note:  
    > If the connection still doesn't work after uploading the driver, try syncing the driver again.




<a name="loiob9b5579054df48c39381d5b17286bf21__section_eyf_qzf_gmb"/>

## Remove \(and Re-Upload\) a Driver

You might need to remove a driver when you want to upload a new version of the driver or your licence agreement has terminated.

1.  Select the driver and choose <span class="FPA-icons-V3"></span> Delete.

2.  If you're using a connection that requires the removed driver for data flows, choose <span class="FPA-icons-V3"></span> Upload to re-upload the driver to make sure that you can continue using the data flows.

3.  Choose <span class="FPA-icons-V3"></span> sync to synchronize the driver changes with the underlying component. Once the synchronization has finished, you can continue using data flows with the connection, or, if you haven't uploaded a new driver, you won't be able to use data flows with the connection anymore unless you re-upload the driver.




## Troubleshooting

If a data flow fails with the error message saying that the driver could not be found, check that the drivers are uploaded and start synchronization.

