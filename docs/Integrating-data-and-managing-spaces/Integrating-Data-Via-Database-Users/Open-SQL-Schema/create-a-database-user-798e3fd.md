<!-- loio798e3fd6707940c3bd2219b2d1ebaac2 -->

<link rel="stylesheet" type="text/css" href="../../css/sap-icons.css"/>

# Create a Database User

Users with the *DW Space Administrator* role can create database users, granting them privileges to read from and/or write to an Open SQL schema with restricted access to the space schema.



## Procedure

1.  In the side navigation area, click ![](images/Space_Management_a868247.png) \(*Space Management*\), locate your space tile, and click *Edit* to open it.

2.  In the *Database Users* section, click *Create* to open the *Create Database User* dialog.

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
    
    Enable Password Policy
    
    </td>
    <td valign="top">
    
    Require the database user to change their password with the frequency defined in the password policy \(see [Set a Password Policy for Database Users](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/14aedf6cecce474b93b2d5187662a090.html "Users with the DW Administrator role (administrators) can set a password policy to cause database user passwords to expire after a specified number of days.") :arrow_upper_right:\).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Enable Automated Predictive Library and Predictive Analysis Library
    
    </td>
    <td valign="top">
    
    Allow the user to access the SAP HANA Cloud machine learning libraries.

    For information about enabling and using these libraries, see [Enable the SAP HANA Cloud Script Server on Your SAP Datasphere Tenant](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/DEV_CURRENT/en-US/287194276a7d4d778ec98fdde5f61335.html "You can enable the SAP HANA Cloud script server on your SAP Datasphere tenant to access the SAP HANA Automated Predictive Library (APL) and SAP HANA Predictive Analysis Library (PAL) machine learning libraries.") :arrow_upper_right: 
    
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
    
    Allow the user to create objects and write data to their Open SQL schema. These objects are available to any modeler working in the space for use as sources for their views and data flows \(see [Using the Source Browser](https://help.sap.com/viewer/24f836070a704022a40c15442163e5cf/DEV_CURRENT/en-US/7d2b21d974e44bdc9d548cf7532b5a43.html "You use the Source Browser to add objects as sources for your data flow, graphical view, SQL view, or intelligent lookup. In an E/R model you add objects to visualize them together in a diagram, including importing objects from connections and other sources, and prepare them for use in other editors.") :arrow_upper_right:\).
    
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
    
4.  In your space page, click *Deploy* to deploy your space and create the database user in the run-time database.

    You will receive a notification when the deployment of the space is complete.

5.  Click the <span class="FPA-icons-V3"></span> button for your user in the *Database Users* list to open the *Database User Details* dialog.

6.  Request a password for your database user:

    1.  Click *Request New Password*.

    2.  Click *Show* to display the new password and enable the *Copy Password* button.

    3.  Click *Copy Password*.

        If you want to work with the SAP HANA database explorer, you will need to enter your password to grant the explorer access to your Open SQL schema. When connecting to your Open SQL schema with other tools, you should additionally note the following properties:

        -   Database User Name
        -   Host Name
        -   Port


7.  If you are using your database user to consume space data in an SAP SQL Data Warehousing HDI container, click the *Copy Full Credentials* button to copy the json code that you can use to initialize your user-defined service \(see [Consume Space Objects in Your HDI Container](../../Exchanging-Data-with-SAP-SQL-Data-Warehousing-HDI-Container/consume-space-objects-in-your-hdi-container-656eebc.md)\).

8.  Click *Close* to return to your space page.

    You can now use your database user \(see [Connect to Your Open SQL Schema](connect-to-your-open-sql-schema-b78ad20.md)\).


