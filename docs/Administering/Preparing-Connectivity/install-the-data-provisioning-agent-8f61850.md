<!-- loio8f6185069a51404ebf23c684fee8cf39 -->

# Install the Data Provisioning Agent

Download the latest Data Provisioning Agent 2.0 version from SAP Software Download Center and install it as a standalone installation on a Windows or Linux machine. If you have already installed an agent, check if you need to update to the latest version. If you have more than one agent that you want to connect to SAP Datasphere, make sure to have the same latest version for all agents.



<a name="loio8f6185069a51404ebf23c684fee8cf39__context_ktz_cx3_3tb"/>

## Context



## Procedure

1.  Plan and prepare the Data Provisioning Agent installation.

    1.  Plan your installation to ensure that it meets your system landscape's needs.

        You can install the agent on any host system that has access to the sources you want to access, meets the minimum system requirements, and has any middleware required for source access installed. The agent should be installed on a host that you have full control over to view logs and restart, if necessary.

        For more information, see:

        -   [Planning and Preparation](https://help.sap.com/docs/HANA_SMART_DATA_INTEGRATION/7952ef28a6914997abc01745fef1b607/65a8690ba4b74503b7e50f66cb85be3b.html?locale=en-US&version=latest) in the *SAP HANA Smart Data Integration and SAP HANA Smart Data Quality* documentation.

        -   [Supported Platforms and System Requirements](https://help.sap.com/docs/HANA_SMART_DATA_INTEGRATION/7952ef28a6914997abc01745fef1b607/d52c01c93e674563ad8d5e12f25c2782.html?locale=en-US&version=latest) in the *SAP HANA Smart Data Integration and SAP HANA Smart Data Quality* documentation.


    2.  Download the latest Data Provisioning Agent *HANA DP AGENT 2.0* from the [SAP Software Download Center](https://support.sap.com/en/my-support/software-downloads.html).

        > ### Note:  
        > -   We recommend to always use the latest released version of the Data Provisioning Agent.
        > 
        > -   Make sure that all agents that you want to connect to SAP Datasphere have the same latest version.
        > 
        > -   Select your operating system before downloading the agent.

        For more information, see:

        -   [Software Download](https://help.sap.com/docs/HANA_SMART_DATA_INTEGRATION/7952ef28a6914997abc01745fef1b607/665d8ea78f0c4f0dbb530a1193737f11.html?locale=en-US&version=latest) in the *SAP HANA Smart Data Integration and SAP HANA Smart Data Quality* documentation

        -   [SAP HANA Smart Data Integration Product Availability Matrix \(PAM\)](https://support.sap.com/content/dam/launchpad/en_us/pam/pam-essentials/TIP/PAM_HANA_SDI_2_0.pdf) \(for supported and available versions for the Data Provisioning Agent and operating system support\)


2.  Install the Data Provisioning Agent on a host in your local network.

    For more information, see [Install from the Command Line](https://help.sap.com/docs/HANA_SMART_DATA_INTEGRATION/7952ef28a6914997abc01745fef1b607/c00f296abd4046ccb59ccbfb5f69d547.html?locale=en-US&version=latest) in the *SAP HANA Smart Data Integration and SAP HANA Smart Data Quality* documentation.

    > ### Note:  
    > If you have upgraded your Data Provisioning Agent to version 2.5.1 and want to create an Amazon Redshift connection, apply SAP note [2985825](https://launchpad.support.sap.com/#/notes/2985825).


[Install the Data Provisioning Agent](https://help.sap.com/viewer/7952ef28a6914997abc01745fef1b607/latest/en-US/dd8aaa71a6d4490485b8eb5123f46149.html)

[Update the Data Provisioning Agent](https://help.sap.com/viewer/7952ef28a6914997abc01745fef1b607/latest/en-US/23b6324923dc4f499425931311bad5ae.html)

