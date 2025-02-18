<!-- loio8f79fc80d6134a89a03837a205d340cd -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Apply a Data Access Control to a Graphical or SQL View

You can apply one or more data access controls to a view to control the data that users will see based on the specified criteria.



<a name="loio8f79fc80d6134a89a03837a205d340cd__context_hyk_1rd_2sb"/>

## Context

For detailed information about defining and using data access controls, see [Securing Data with Data Access Controls](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/a032e51c730147c7a1fcac125b4cfe14.html "Users with a space administrator role can create data access controls to allow modelers to apply row-level security to Data Builder and Business Builder objects. Once a data access control is applied to an object, any user viewing its data either directly or via an object using it as a source, will see only those records they are authorized to view, based on the specified criteria.") :arrow_upper_right:.



## Procedure

1.  In the left navigation area, click *Data Builder* and select the space you want to work in.

2.  Open the view that you want to apply the data access control to.

3.  Select the output node of the view and open the *Data Access Control* section in its side panel and click <span class="FPA-icons-V3"></span> \(Add\).

    Find available objects by entering the object's name in the search bar or click <span class="FPA-icons-V3"></span> \(Show filters\) and filter by *Semantic Usage* or other criteria.  

4.  In the *Join* section, map columns from your view to the criteria columns defined in the data access control.

    You must map a column from your view to each of the criteria columns defined in the data access control in order to correctly filter your view's data by the criteria.

5.  Click <span class="SAP-icons-V5"></span> \(Deploy\) to save and deploy the view.

    Users opening your view in SAP Datasphere or in SAP Analytics Cloud or other analytics tools will only see the data permitted by the assignment of their username to the criteria defined in the data access control.

    > ### Note:  
    > You can use the *View as User* tool in the *Data Viewer* panel to review the effects of the data access controls you apply by checking the records that another user will be allowed to see \(see [Viewing Object Data](viewing-object-data-b338e4a.md)\).


