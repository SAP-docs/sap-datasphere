<!-- loio9a00dde9a5fa492b914e409b4e80c6bd -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Enable Access to Data Provisioning Agent Logs

Enable accessing an agent’s log files before you can view them in SAP Datasphere.



<a name="loio9a00dde9a5fa492b914e409b4e80c6bd__prereq_e1j_zsw_w4b"/>

## Prerequisites

A Data Provisioning Agent administrator has provided the necessary File adapter configuration with an access token that you need for enabling the log access in SAP Datasphere.

To configure the access token in the agent's secure storage, the administrator has performed the following steps in the agent configuration tool in command-line interactive mode:

1.  At the command line, navigate to <code><i class="varname">&lt;DPAgent_root&gt;</i>/bin</code>.

2.  Start the agent configuration tool with the ***setSecureProperty*** parameter.

    -   On Windows: `agentcli.bat --setSecureProperty`

    -   On Linux, `./agentcli.sh --setSecureProperty`


3.  Choose *Set FileAdapter Access Token* and specify the token.


For more information about the File adapter configuration, see [File](https://help.sap.com/viewer/7952ef28a6914997abc01745fef1b607/latest/en-US/d430dc8f21e84853a3fe39351fc5fafc.html) in the *Installation and Configuration Guide* of the *SAP HANA Smart Data Integration and SAP HANA Smart Data Quality* documentation.



## Procedure

1.  From the <span class="SAP-icons"></span> main menu, open *Configuration* \> *Data Integration*.

2.  On the agent’s tile, click *Edit*.

3.  In the *Agent Settings* dialog, set *Enable Log Access* to *true*.

4.  In the *FileAdapter Password* field that appears, enter the File adapter access token.

5.  Click *Save* to activate the log access.




<a name="loio9a00dde9a5fa492b914e409b4e80c6bd__result_osg_45w_w4b"/>

## Results

The *Review Logs* entry in the menu of the agent’s tile is enabled and the `framework_alert.trc` and `framework.trc` logs are written to the database of SAP Datasphere. You can now review the current and archived log files from the agent's tile.

