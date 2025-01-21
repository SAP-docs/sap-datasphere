<!-- loio407d1dff76a842699ea08c17eb8748dd -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Accelerate Table Data Access with In-Memory Storage

By default, when you are working in an SAP HANA Cloud, SAP HANA database space, table data is stored on disk. You can improve performance by enabling in-memory storage.



## Procedure

1.  Open your table in the table editor and navigate to the property Storage

2.  Enable the following option:Update the property as follows:


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
    
    Storage
    
    </td>
    <td valign="top">
    
    Change the value from "Disc" to "In-Memory
    
    </td>
    </tr>
    </table>
    
3.  Click <span class="SAP-icons-V5"></span> \(Deploy\) to deploy the table and move its data into in-memory storage.


