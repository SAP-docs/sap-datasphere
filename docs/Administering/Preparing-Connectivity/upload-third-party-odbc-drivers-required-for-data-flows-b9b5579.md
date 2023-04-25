<!-- loiob9b5579054df48c39381d5b17286bf21 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Upload Third-Party ODBC Drivers \(Required for Data Flows\)

To enable access to a non-SAP database via ODBC to use it as a source for data flows, you need to upload the required ODBC driver files to SAP Datasphere.



<a name="loiob9b5579054df48c39381d5b17286bf21__section_tqp_kfh_2mb"/>

## Prerequisites

-   Search for the required driver files in the internet, make sure you have selected the correct driver files \(identified by their SHA256-formatted fingerprint\) and download them from an appropriate web page \(see below\).

-   Ensure you have a valid license for the driver files.




<a name="loiob9b5579054df48c39381d5b17286bf21__section_k3n_hzn_tsb"/>

## Context

Drivers are required for the following connection types:


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
<th valign="top">

SHA256 Fingerprint



</th>
</tr>
<tr>
<td valign="top">

[Amazon Redshift Connections](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/8b132061d4e149d9a16b3576dda1f613.html "Use an Amazon Redshift connection to access data from Amazon Redshift 8.x databases.") :arrow_upper_right:



</td>
<td valign="top">

AmazonRedshiftODBC-64-bit-1.4.11.1000-1.x86\_64.rpm



</td>
<td valign="top">

`https://docs.aws.amazon.com` 



</td>
<td valign="top">

6d811e2f198a030274bf9f099d4c828b1b071b78e99432eee1531d4988768a22



</td>
</tr>
<tr>
<td valign="top">

[Oracle Connections](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/c73ae0601d364f47830d339b6e86b7e8.html "Use an Oracle connection to access data from an Oracle database (on-premise).") :arrow_upper_right:



</td>
<td valign="top">

instantclient-basiclite-linux.x64-12.2.0.1.0.zip

> ### Note:  
> Make sure to select the *Basic Light* package zip file from the 12.2.0.1.0 version. The package applies to all versions supported by the Oracle connection type \(Oracle 12c, Oracle 18c, and Oracle 19c\).



</td>
<td valign="top">

`https://oracle.com`



</td>
<td valign="top">

1c3adb36f9605aae84ae98461bd6ee9eb26b303cace3f5534cd7985d470d0494



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

Perform the following steps before creating the first Amazon Redshift or Oracle connection that you want to use for data flows.

1.  In the side navigation area, click <span class="FPA-icons"></span> \(*System*\) ** \> ** :wrench: \(*Configuration*\) ** \> *Data Integration*.

2.  Go to *Third-Party Drivers* and choose <span class="FPA-icons"></span> Upload.

3.  In the following dialog box, choose *Browse* to select the driver file from your download location.

    > ### Note:  
    > The fingerprint of the driver file name to be uploaded must match the fingerprint mentioned above.

4.  Choose *Upload*.

5.  Choose <span class="FPA-icons"></span> sync to synchronize the driver with the underlying component. Wait for about 5 to 10 minutes to finish synchronization before you start creating connections or using data flows with the connection.




<a name="loiob9b5579054df48c39381d5b17286bf21__section_eyf_qzf_gmb"/>

## Remove \(and Re-Upload\) a Driver

You might need to remove a driver when you want to upload a new version of the driver or your licence agreement has terminated.

1.  Select the driver and choose <span class="FPA-icons"></span> Delete.

2.  If you're using a connection that requires the removed driver for data flows, choose <span class="FPA-icons"></span> Upload to re-upload the driver to make sure that you can continue using the data flows.

3.  Choose <span class="FPA-icons"></span> sync to synchronize the driver changes with the underlying component. Once the synchronization has finished, you can continue using data flows with the connection, or, if you haven't uploaded a new driver, you won't be able to use data flows with the connection anymore unless you re-upload the driver.




## Troubleshooting

If a data flow fails with the error message saying that the driver could not be found, check that the drivers are uploaded and start synchronization.

