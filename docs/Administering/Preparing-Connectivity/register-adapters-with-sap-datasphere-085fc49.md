<!-- loio085fc4917f6f4011900344d44d721705 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Register Adapters with SAP Datasphere

After configuring the Data Provisioning Agent, in SAP Datasphere, register the Data Provisioning adapters that are needed to connect to on-premise sources.



<a name="loio085fc4917f6f4011900344d44d721705__prereq_zhy_2f3_jlb"/>

## Prerequisites

For third-party adapters, ensure that you have downloaded and installed any necessary JDBC libraries. Place the files in the <code><i class="varname">&lt;DPAgent_root&gt;</i>/lib</code> folder before registering the adapters with SAP Datasphere. For connection types *Amazon Redshift* and *Generic JDBC*, place the file in the <code><i class="varname">&lt;DPAgent_root&gt;</i>/camel/lib</code> folder.

For information about the proper JDBC library for your source, see the [SAP HANA smart data integration and all its patches Product Availability Matrix \(PAM\) for SAP HANA SDI 2.0](https://support.sap.com/content/dam/launchpad/en_us/pam/pam-essentials/TIP/PAM_HANA_SDI_2_0.pdf). Search for the library in the internet and download it from an appropriate web page.



<a name="loio085fc4917f6f4011900344d44d721705__steps_ns4_r23_jlb"/>

## Procedure

1.  In the side navigation area, click <span class="FPA-icons-V3"></span> \(*System*\) ** \> ** :wrench: \(*Configuration*\) ** \> *Data Integration*.

2.  In the *On-Premise Agents* section, click the *Adapters* button to display the agents with their adapter information.

3.  Click <span class="SAP-icons-V5"></span> \(menu\) and then :pencil2: *Edit*.

4.  In the *Agent Settings* dialog, under *Agent Adapters* select the adapters.

5.  Click *Close* to close the dialog and register the selected adapters with SAP Datasphere.

    > ### Note:  
    > It is not required to save to update the agent settings.

    The registered adapters are now available for creating connections to the supported on-premise sources.




<a name="loio085fc4917f6f4011900344d44d721705__postreq_tk5_33t_vnb"/>

## Next Steps

To use new functionality of an already registered adapter or to update the adapter in case of issues that have been fixed in a new agent version, you can refresh the adapter by clicking the <span class="SAP-icons-V5"></span> \(menu\) button and then choosing <span class="SAP-icons-V5"></span> *Refresh*.

