<!-- loio287194276a7d4d778ec98fdde5f61335 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Enable the SAP HANA Cloud Script Server on Your SAP Datasphere Tenant

You can enable the SAP HANA Cloud script server on your SAP Datasphere tenant to access the SAP HANA Automated Predictive Library \(APL\) and SAP HANA Predictive Analysis Library \(PAL\) machine learning libraries.

> ### Note:  
> The SAP HANA Cloud script server cannot be enabled in a SAP Datasphere consumption-based tenant with free plan.



## Procedure

1.  Select <span class="FPA-icons-V3"></span> \(*System*\) ** \> ** :wrench: \(*Configuration*\)*Tenant Configuration* \(see [Configure the Size of Your SAP Datasphere Tenant](configure-the-size-of-your-sap-datasphere-tenant-33f8ef4.md)\).
2.  Select the checkbox in the *Base Configuration* section.

Once the script server is enabled, the *Enable Automated Predictive Library and Predictive Analysis Library* option can be selected when creating a database user \(see [Create a Database User](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/798e3fd6707940c3bd2219b2d1ebaac2.html "Users with a space administration role can create database users, granting them privileges to read from and/or write to an Open SQL schema with restricted access to the space schema.") :arrow_upper_right:\).

For detailed information about using the machine learning libraries, see:

-   [SAP HANA Automated Predictive Library Developer Guide](https://help.sap.com/viewer/7223667230cb471ea916200712a9c682/2101/en-US)
-   [SAP HANA Cloud Predictive Analysis Library \(PAL\)](https://help.sap.com/docs/hana-cloud-database/sap-hana-cloud-sap-hana-database-predictive-analysis-library/sap-hana-cloud-sap-hana-database-predictive-analysis-library-pal)

