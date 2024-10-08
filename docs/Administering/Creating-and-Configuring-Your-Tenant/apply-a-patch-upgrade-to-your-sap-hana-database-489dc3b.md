<!-- loio489dc3b4ba4040b79bd97a1ca236c004 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Apply a Patch Upgrade to Your SAP HANA Database

As an SAP Datasphere administrator, you can upgrade your SAP HANA database. This ensures your system is up to date and running smoothly.



## Context

> ### Note:  
> This task is limited to patch upgrades. For example, if your current database version is 2024.28.3, and the next patch version of 2024.28.4 is available, you can upgrade. You cannot go from version 2024.28.4 to 2024.29.0, because that is a larger upgrade, not a patch.



## Procedure

1.  In the side navigation area, click <span class="FPA-icons-V3"></span> System ** \> **<span class="FPA-icons-V3"></span> About.

2.  Click *More* and scroll to the bottom of the dialog.

3.  Click *Trigger Patch Upgrade*.

    A confirmation dialog is shown informing you that the upgrade will cause a short downtime where SAP Datasphere is not connected to SAP HANA.

4.  Click *Trigger upgrade* to continue.

    The patch upgrade begins. When the patch is finished, you'll receive a :bell:notification.


