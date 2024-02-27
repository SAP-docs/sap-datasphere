<!-- loioa6fb3e70da0a42b2aa4a7ac7b73f5ae1 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Create an Input Parameter

Create input parameters in your data flows for use in projection operator filter conditions or calculated columns. When you want to staring a data flow run, you are prompted to enter a value and this value is used to filter the data to be loaded



## Procedure

1.  Open the data flow properties in the side panel, scroll down to the *Input Parameter* section and click <span class="FPA-icons-V3"></span> \(Input Parameters\).

2.  In the *Input Parameter* dialog, click <span class="FPA-icons-V3"></span> \(Add\) to create a new parameter.

3.  Complete the properties of the input parameter:


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
    
    Name 
    
    </td>
    <td valign="top">
    
    Enter a descriptive name to help users identify the object. This name can be changed at any time. 
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Data Type 
    
    </td>
    <td valign="top">
    
    Displays *string* as the currently available type. 
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Default Value 
    
    </td>
    <td valign="top">
    
    \[optional\] Enter a default value for the input parameter. Each time the user is required to enter a value for the parameter, they can accept the default value or override it. The values must be entered inside of single quotes, for example, 'Germany'. The default value is used whenever the data flow is run as part of a schedule or task chain. You can enter `CURRENT_DATE()` or `CURRENT_TIME()` to obtain the current UTC date or timestamp at runtime. 
    
    </td>
    </tr>
    </table>
    
4.  Click *OK* to close the dialog and return to the side panel where the input parameter is available for use.

5.  Use the input parameter as appropriate in the projection operator.


    <table>
    <tr>
    <th valign="top">

    Example
    
    </th>
    <th valign="top">

    Description
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    `Country = ${IP_Country}`
    
    </td>
    <td valign="top">
    
    Projection Filter expression \(see [Create a Projection Operator](create-a-projection-operator-912f740.md)\).

    This filter expression takes the value entered by the user for `IP_Country` and uses it to restrict the data returned by the data flow to only those rows where the `Country` column contains this value.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    `ADD_DAYS(Date,${IP_Days})`
    
    </td>
    <td valign="top">
    
    Calculated Column expression \(see [Create a Calculated Column in a Projection Operator](create-a-calculated-column-in-a-projection-operator-73116a5.md)\)

    This expression will fill the column with a value calculated by taking the value in the `Date` column and adding the value entered by the user \(days\) to the date.

    > ### Note:  
    > At runtime, the string entered by the user is converted into the correct data type.


    
    </td>
    </tr>
    </table>
    
    > ### Note:  
    > You must use each of the input parameters that you create at least once in your data flow or you will receive an error instructing you to use or delete them.


