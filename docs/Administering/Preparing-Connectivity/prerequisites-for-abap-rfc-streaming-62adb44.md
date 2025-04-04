<!-- loio62adb440e4214c53a3028a4fdb5e1156 -->

# Prerequisites for ABAP RFC Streaming

If you want to stream ABAP tables for loading large amounts of data without running into memory issues it is required to meet the following requirements.

-   You need to create an RFC destination in the ABAP source system. With the RFC destination you register the Data Provisioning agent as server program in the source system.

    Using transaction SM59, you create a TCP/IP connection with a user-defined name. The connection should be created with “Registered Server Program” as “Activation Type”. Specify “IM\_HANA\_ABAPADAPTER\_\*” as a filter for the “Program ID” field, or leave it empty.

    > ### Note:  
    > You can ignore failing SM59 connection tests because the RFC connection is only built up when the replication is running to query records from the SAP system. For more information, see SAP Note [3206908](https://me.sap.com/notes/3206908).

-   Successful registration on an SAP Gateway requires that suitable security privileges are configured. For example:

    -   Set up an Access Control List \(ACL\) that controls which host can connect to the gateway. That file should contain something similar to the following syntax: `<permit> <ip-address[/mask]> [tracelevel] [# comment]`. `<ip-address>` here is the IP of the server on which Data Provisioning agent has been installed.

        For more information, see the *Gateway* documentation in the SAP help for your source system version, for example in the *SAP NetWeaver 7.5* documentation:

        -   [Configuring Network-Based Access Control Lists \(ACL\)](https://help.sap.com/viewer/62b4de4187cb43668d15dac48fc00732/7.5.latest/en-US/d0a4956abd904c8d855ee9d368bc510b.html)
        -   [Gateway ACL Editor](https://help.sap.com/docs/SAP_NETWEAVER_750/62b4de4187cb43668d15dac48fc00732/5872aed2b8cc4b0387374cbf5f4adcf6.html)

    -   You may also want to configure a `reginfo` file to control permissions to register external programs.



