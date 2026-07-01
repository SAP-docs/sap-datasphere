<!-- loio798e3fd6707940c3bd2219b2d1ebaac2 -->

<link rel="stylesheet" type="text/css" href="../../css/sap-icons.css"/>

# Create a Database User

Users with a space administrator role can create database users, granting them privileges to read from and/or write to an Open SQL schema with restricted access to the space schema.

This topic contains the following sections:

-   [Prerequisites](create-a-database-user-798e3fd.md#loio798e3fd6707940c3bd2219b2d1ebaac2__section_qkz_ylg_zgc)
-   [Create a Database User with Password-Based Authentication](create-a-database-user-798e3fd.md#loio798e3fd6707940c3bd2219b2d1ebaac2__section_password_auth)
-   [Create a Database User with Certificate-Based Authentication](create-a-database-user-798e3fd.md#loio798e3fd6707940c3bd2219b2d1ebaac2__section_certificate_auth)
-   [Switch Database User Authentication from Password to Certificate-Based](create-a-database-user-798e3fd.md#loio798e3fd6707940c3bd2219b2d1ebaac2__section_swith_to_certificate)
-   [Delete a Database User](create-a-database-user-798e3fd.md#loio798e3fd6707940c3bd2219b2d1ebaac2__section_nmy_1ng_zgc)



<a name="loio798e3fd6707940c3bd2219b2d1ebaac2__section_qkz_ylg_zgc"/>

## Prerequisites

To create database users, you must have a scoped role that grants you access to a space with the following privileges:

-   *Data Warehouse General* \(`-R------`\) - To access SAP Datasphere.
-   *Spaces* \(`-RU-----`\) - To open and update your space in the *Space Management* tool.
-   *Space Files* \(`-R------`\) - To view objects in your space.

The *DW Space Administrator* role template, for example, grants these privileges. For more information, see [Privileges and Permissions](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/STABI/en-US/d7350c6823a14733a7a5727bad8371aa.html "A privilege represents a task or an area in SAP Datasphere and can be assigned to a specific role. The actions that can be performed in the area are determined by the permissions assigned to a privilege.") :arrow_upper_right: and [Standard Roles Delivered with SAP Datasphere](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/STABI/en-US/a50a51d80d5746c9b805a2aacbb7e4ee.html "SAP Datasphere is delivered with several standard roles. A standard role includes a predefined set of privileges and permissions.") :arrow_upper_right:. 



<a name="loio798e3fd6707940c3bd2219b2d1ebaac2__section_password_auth"/>

## Create a Database User with Password-Based Authentication

1.  In the side navigation area, click ![](images/Space_Management_a868247.png) \(*Space Management*\), locate your space tile, and click *Edit* to open it.
2.  In the *Database Users* section, click *Create*. The *Create Database User* dialog opens.
3.  Complete the properties as appropriate and click *Create* to create the user:


    <table>
    <tr>
    <th valign="top">

    Property
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Database User Name Suffix
    
    </td>
    <td valign="top">
    
    Enter the name of your database user, which will be appended to the space name to give the name of the Open SQL schema.

    Can contain a maximum of \(40 minus the space name\) uppercase letters or numbers and must not contain spaces or special characters other than \_ \(underscore\).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Authentication Type
    
    </td>
    <td valign="top">
    
    Select *Password-Based Authentication*.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Enable Password Lifetime
    
    </td>
    <td valign="top">
    
    Require the database user to change the password with the frequency defined in the password policy and on the first logon \(see [Set a Password Policy for Database Users](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/STABI/en-US/14aedf6cecce474b93b2d5187662a090.html "You can set a password policy for database users with complexity requirements, expiration periods, and reuse restrictions.") :arrow_upper_right:\).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Enable Automated Predictive Library \(APL\) and Predictive Analysis Library \(PAL\)
    
    </td>
    <td valign="top">
    
    Allow the user to access the SAP HANA Cloud machine learning libraries.

    You can also enable:

    -   *With Grant Option* - Grant access to the libraries to other users if they need to create procedures in the Open SQL schema that call APL/PAL procedures and use them in a task chain \(see [Creating a Task Chain](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/STABI/en-US/d1afbc2b9ee84d44a00b0b777ac243e1.html "Group multiple tasks into a task chain and run them manually once, or periodically, through a schedule.") :arrow_upper_right:\). Select this option only for users who need to create procedures. This option is not intended for granting APL/PAL access to other users.

    For information about enabling and using these libraries, see [Enable the SAP HANA Cloud Script Server on Your SAP Datasphere Tenant](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/STABI/en-US/287194276a7d4d778ec98fdde5f61335.html "You can enable the SAP HANA Cloud script server on your SAP Datasphere tenant to access the SAP HANA Automated Predictive Library (APL) and SAP HANA Predictive Analysis Library (PAL) machine learning libraries.") :arrow_upper_right:.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Enable Read Access \(SQL\)
    
    </td>
    <td valign="top">
    
    Allow the user to read all views that have *Expose for Consumption* enabled via their Open SQL schema.

    You can also enable:

    -   *With Grant Option* - Allow the user to grant read access to other database users.
    -   *Enable HDI Consumption* - Allow the creation of a user-defined service to give read access to an HDI container added to the space \(see [Consume Space Objects in Your HDI Container](../../Exchanging-Data-with-SAP-SQL-Data-Warehousing-HDI-Container/consume-space-objects-in-your-hdi-container-656eebc.md)\).


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Enable Write Access \(SQL, DDL, DML\)
    
    </td>
    <td valign="top">
    
    Allow the user to create objects and write data to their Open SQL schema. These objects are available to any modeler working in the space for use as sources for their views and data flows \(see [Using the Source Browser](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/STABI/en-US/7d2b21d974e44bdc9d548cf7532b5a43.html "You use the Source Browser to add objects as sources for your data flow, graphical view, SQL view, or intelligent lookup. In an E/R model you add objects to visualize them together in a diagram, including importing objects from connections and other sources, and prepare them for use in other editors.") :arrow_upper_right:\).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Enable Audit Logs for Read Operations / Enable Audit Logs for Change Operations
    
    </td>
    <td valign="top">
    
    Enable logging of all read and change operations performed by the user.

    For more information, see [Logging Read and Change Actions for Audit](../../logging-read-and-change-actions-for-audit-2665539.md).
    
    </td>
    </tr>
    </table>
    
4.  Click the <span class="FPA-icons-V3"></span> button for your user in the *Database Users* list to open the *Database User Details* dialog.
5.  Request a password for your database user:
    1.  Click *Request New Password*.
    2.  Click *Show* to display the new password and enable the *Copy Password* button.
    3.  Click *Copy Password*.

        If you want to work with the SAP HANA database explorer, you will need to enter your password to grant the explorer access to your Open SQL schema. When connecting to your Open SQL schema with other tools, you should additionally note the following properties:

        -   Database User Name
        -   Host Name
        -   Port


6.  If you are using your database user to consume space data in an SAP HANA for SQL data warehousing HDI container, click the *Copy Full Credentials* button to copy the json code that you can use to initialize your user-defined service \(see [Consume Space Objects in Your HDI Container](../../Exchanging-Data-with-SAP-SQL-Data-Warehousing-HDI-Container/consume-space-objects-in-your-hdi-container-656eebc.md)\).
7.  Click *Close* to return to your space page.

You can now use your database user \(see [Connect to Your Open SQL Schema](connect-to-your-open-sql-schema-b78ad20.md)\).

> ### Note:  
> A database user with the status *Active* can be used.



<a name="loio798e3fd6707940c3bd2219b2d1ebaac2__section_certificate_auth"/>

## Create a Database User with Certificate-Based Authentication

You can create a database user with certificate-based authentication provided that a X.509 root certificate \(root CA\) has been uploaded for the tenant by a user with an administrator role \(see [Manage Certificates](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/STABI/en-US/46f5467adc5242deb1f6b68083e72994.html "Upload certificates and select their purpose: Choose TLS Server to secure connections or X.509 Client (Open SQL) to enable X.509 client certificate-based authentication for Open SQL database users.") :arrow_upper_right:\).

1.  In the side navigation area, click ![](images/Space_Management_a868247.png) \(*Space Management*\), locate your space tile, and click *Edit* to open it.
2.  In the *Database Users* section, click *Create*. The *Create Database User* dialog opens.
3.  Complete the properties as appropriate and click *Create* to create the user:


    <table>
    <tr>
    <th valign="top">

    Property
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    Database User Name Suffix
    
    </td>
    <td valign="top">
    
    Enter the name of your database user, which will be appended to the space name to give the name of the Open SQL schema.

    Can contain a maximum of \(40 minus the space name\) uppercase letters or numbers and must not contain spaces or special characters other than \_ \(underscore\).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Authentication Type
    
    </td>
    <td valign="top">
    
    \[Default\] *Certificate-Based Authentication*
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    X.509 Certificate
    
    </td>
    <td valign="top">
    
    Upload a X.509 client certificate. Once the certificate has been uploaded, its subject and issuer distinguished names are displayed.

    > ### Note:  
    > The certificate will work if a X.509 root certificate \(root CA\) has been uploaded for the tenant by a user with an administrator role \(see [Manage Certificates](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/STABI/en-US/46f5467adc5242deb1f6b68083e72994.html "Upload certificates and select their purpose: Choose TLS Server to secure connections or X.509 Client (Open SQL) to enable X.509 client certificate-based authentication for Open SQL database users.") :arrow_upper_right:\).

    > ### Note:  
    > Once you've uploaded a certificate for the database user:
    > 
    > -   You cannot switch to password-based authentication.
    > -   You cannot upload another certificate later for this user. Also, you cannot use the same certificate for several database users.

    Client certificates have an expiry date. If your certificate expires, contact the administrator who issued it to obtain a replacement.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Enable Automated Predictive Library \(APL\) and Predictive Analysis Library \(PAL\)
    
    </td>
    <td valign="top">
    
    Allow the user to access the SAP HANA Cloud machine learning libraries.

    You can also enable:

    -   *With Grant Option* - Grant access to the libraries to other users if they need to create procedures in the Open SQL schema that call APL/PAL procedures and use them in a task chain \(see [Creating a Task Chain](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/STABI/en-US/d1afbc2b9ee84d44a00b0b777ac243e1.html "Group multiple tasks into a task chain and run them manually once, or periodically, through a schedule.") :arrow_upper_right:\). Select this option only for users who need to create procedures. This option is not intended for granting APL/PAL access to other users.

    For information about enabling and using these libraries, see [Enable the SAP HANA Cloud Script Server on Your SAP Datasphere Tenant](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/STABI/en-US/287194276a7d4d778ec98fdde5f61335.html "You can enable the SAP HANA Cloud script server on your SAP Datasphere tenant to access the SAP HANA Automated Predictive Library (APL) and SAP HANA Predictive Analysis Library (PAL) machine learning libraries.") :arrow_upper_right:.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Enable Read Access \(SQL\)
    
    </td>
    <td valign="top">
    
    Allow the user to read all views that have *Expose for Consumption* enabled via their Open SQL schema.

    You can also enable:

    -   *With Grant Option* - Allow the user to grant read access to other database users.
    -   *Enable HDI Consumption* - Allow the creation of a user-defined service to give read access to an HDI container added to the space \(see [Consume Space Objects in Your HDI Container](../../Exchanging-Data-with-SAP-SQL-Data-Warehousing-HDI-Container/consume-space-objects-in-your-hdi-container-656eebc.md)\).


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Enable Write Access \(SQL, DDL, DML\)
    
    </td>
    <td valign="top">
    
    Allow the user to create objects and write data to their Open SQL schema. These objects are available to any modeler working in the space for use as sources for their views and data flows \(see [Using the Source Browser](https://help.sap.com/viewer/c8a54ee704e94e15926551293243fd1d/STABI/en-US/7d2b21d974e44bdc9d548cf7532b5a43.html "You use the Source Browser to add objects as sources for your data flow, graphical view, SQL view, or intelligent lookup. In an E/R model you add objects to visualize them together in a diagram, including importing objects from connections and other sources, and prepare them for use in other editors.") :arrow_upper_right:\).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Enable Audit Logs for Read Operations / Enable Audit Logs for Change Operations
    
    </td>
    <td valign="top">
    
    Enable logging of all read and change operations performed by the user.

    For more information, see [Logging Read and Change Actions for Audit](../../logging-read-and-change-actions-for-audit-2665539.md).
    
    </td>
    </tr>
    </table>
    
4.  Click the <span class="FPA-icons-V3"></span> button for your user in the *Database Users* list to open the *Database User Details* dialog.
5.  In the *User Authentication* area, you can see the certificate's subject and issuer distinguished names are displayed.
6.  If you are using your database user to consume space data in an SAP HANA for SQL data warehousing HDI container, click the *Copy Full Credentials* button to copy the json code that you can use to initialize your user-defined service \(see [Consume Space Objects in Your HDI Container](../../Exchanging-Data-with-SAP-SQL-Data-Warehousing-HDI-Container/consume-space-objects-in-your-hdi-container-656eebc.md)\).
7.  Click *Close* to return to your space page.

You can now use your database user \(see [Connect to Your Open SQL Schema](connect-to-your-open-sql-schema-b78ad20.md)\).

> ### Note:  
> A database user with the status *Active* can be used.



<a name="loio798e3fd6707940c3bd2219b2d1ebaac2__section_swith_to_certificate"/>

## Switch Database User Authentication from Password to Certificate-Based

You can change a database user's authentication from password-based to certificate-based, but you cannot change it back from certificate-based to password-based.

1.  In the side navigation area, click ![](images/Space_Management_a868247.png) \(*Space Management*\), locate your space tile, and click *Edit* to open it.
2.  In the *Database Users* section, click the <span class="FPA-icons-V3"></span> button for your database, which opens the *Database User Details* dialog.
3.  In the *Switch to X.509 Authentication* section, upload a X.509 client certificate. The certificate's subject and issuer distinguished names are displayed.

    > ### Note:  
    > The certificate will work if a X.509 root certificate \(root CA\) has been uploaded for the tenant by a user with an administrator role \(see [Manage Certificates](https://help.sap.com/viewer/9f804b8efa8043539289f42f372c4862/STABI/en-US/46f5467adc5242deb1f6b68083e72994.html "Upload certificates and select their purpose: Choose TLS Server to secure connections or X.509 Client (Open SQL) to enable X.509 client certificate-based authentication for Open SQL database users.") :arrow_upper_right:\).

    > ### Note:  
    > Once you select a certificate, you cannot switch to password-based authentication.

4.  Click *Apply*.



<a name="loio798e3fd6707940c3bd2219b2d1ebaac2__section_nmy_1ng_zgc"/>

## Delete a Database User

1.  In the side navigation area, click ![](images/Space_Management_a868247.png) \(*Space Management*\), locate your space tile, and click *Edit* to open it.
2.  In the *Database Users* section, select the database user that you want to delete and click *Delete*.

    In the confirmation dialog, enter DELETE if you are sure that you no longer need the database user and any of its content or data, then click the *Delete* button.

    The database user and the following content and data are permanently deleted and cannot be recovered:

    -   All objects and data contained in the Open SQL schema.
    -   All audit logs entries related to the Open SQL schema.


