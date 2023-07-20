<!-- loio562e9969426840798e8a5bbf9c395ce8 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Adding Sharing Destinations

You can add sharing destinations to your export and specify their level of permissions for the content in the *Package Properties* page of the Export app.



## Procedure

1.  Click the :heavy_plus_sign: \(*Add destination*\) button above the *Destinations* list to open the *Destinations* dialog.

2.  Complete the dialog as follows:


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
    
    Destination Type


    
    </td>
    <td valign="top">
    
    Select the category of the destination that you want to add:

    -   *System*: Add an individual tenant by URL. Select a *Landscape*, and copy the URLs to the *Systems* list.

        > ### Note:  
        > SAP Datasphere is only available on the Cloud Foundry platform. You can share to tenants that use the same type of Cloud Foundry data center as yours. These host systems use two digits, such as eu10 or us30.

    -   *Customer*: Add all tenants that belong to one customer based on their ERP ID. Type the ID in the *Customer* field.



    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Access


    
    </td>
    <td valign="top">
    
    Select one or more permissions that you want to grant to the sharing destination:

    -   *View*: Your package will appear in the *My Content* page for the destination tenants, and their users will be able to view the name and summary.
    -   *Import*: The tenants' users can import the package from the *My Content* list.
    -   *Edit*: Your package will appear in the *Manage Packages* page for the destination tenants, where users can make changes to the package and export it again.
    -   *Delete*: From the *Manage Packages* page, the tenants' users can delete the package.


    
    </td>
    </tr>
    </table>
    
3.  Click *Add* to add the destination to the *Added Destinations* list.

    You can add multiple destinations and edit access or remove destinations from the list.

4.  Select *OK* to finish adding destinations and return to the wizard.


