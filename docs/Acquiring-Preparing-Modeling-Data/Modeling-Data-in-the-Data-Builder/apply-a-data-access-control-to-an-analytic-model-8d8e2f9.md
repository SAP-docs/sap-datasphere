<!-- loio8d8e2f9b36a74de3b6f5f1384ad8f70d -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Apply a Data Access Control to an Analytic Model

You can apply one or more data access controls to an analytic model to control the data that users will see based on the specified criteria.



## Context

For detailed information about defining and using data access controls, see [Securing Data with Data Access Controls](https://help.sap.com/viewer/be5967d099974c69b77f4549425ca4c0/cloud/en-US/a032e51c730147c7a1fcac125b4cfe14.html "Users with a space administrator role can create data access controls to allow modelers to apply row-level security to Data Builder and Business Builder objects. Once a data access control is applied to an object, any user viewing its data either directly or via an object using it as a source, will see only those records they are authorized to view, based on the specified criteria.") :arrow_upper_right:.



## Procedure

1.  In the left navigation area, click *Data Builder* and select the space you want to work in.

2.  Open the object that you want to apply the data access control to.

3.  Click the background of the canvas to ensure that the analytic model is selected and open the *Data Access Control* list in its side panel.

    The list contains data access controls applied to the object.

4.  Click <span class="FPA-icons-V3"></span> \(Add\) to open the *Select Data Access Control* dialog, choose the data access control to apply, and click *Select*.

5.  In the *Join* section, map columns from your object to the criteria columns defined in the data access control.

    You must map a column from your object to each of the criteria columns defined in the data access control in order to correctly filter the data by the criteria.

6.  Click <span class="SAP-icons-V5"></span> \(Deploy\) to save and deploy the object.

    Users opening your object in SAP Datasphere or in SAP Analytics Cloud or other analytics tools will only see the data permitted by the criteria defined in the data access control.

    > ### Note:  
    > You can use the *View as User* tool in the *Data Viewer* panel to review the effects of the data access controls you apply by checking the records that another user will be allowed to see \(see [Viewing Object Data](../viewing-object-data-b338e4a.md)\).


