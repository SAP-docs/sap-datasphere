<!-- loio53fa99ad58c04a1ba3bb87288756dabc -->

<link rel="stylesheet" type="text/css" href="css/sap-icons.css"/>

# Create an Input Parameter

Create an input parameter to prompt the user to enter a value for use in filtering or other calculations when the view is run. If the view is consumed in an SAP Analytics Cloud story the user will be prompted to enter a value for the input parameter in the *Set Variables* dialog. 



## Context

You can use input parameters when creating graphical and SQL views:

-   In the graphical view editor, you can use input parameters to require user input in any sql expression, including those used in filter, calculated columns, and aggregation nodes.
-   In the SQL view editor, you can use input parameters in your `WHERE` clause or anywhere else in your SQL code.

Views that contain input parameters require special treatment in the following situations:

-   Previewing data - You must enter a value for each input parameter \(see [Viewing or Previewing Data in Data Builder Objects](viewing-or-previewing-data-in-data-builder-objects-b338e4a.md)\).

    Previewing a SQL view isn't possible if one of the view's objects is shared from another space and has an input parameter.

-   Adding a view as a source in the graphical view editor - You must map each input parameter in the source view to a value or an input parameter in the new view \(see [Add a Source](add-a-source-1eee180.md)\).
-   Adding a view as a source in the SQL view editor - You must complete the syntax to map each input parameter parameter in the source view to a value or an input parameter in the new view \(see [Process Source Input Parameters in an SQL View](process-source-input-parameters-in-an-sql-view-58d8763.md)\).
-   Using a view as a data source in an SAP Analytics Cloud story - Enter a value for each input parameter in the *Set Variables* dialog \(see [Setting Story Variables](https://help.sap.com/viewer/00f68c2e08b941f081002fd3691d86a7/release/en-US/305dcf7053634875a408a9d9832c8b8f.html) in the *SAP Analytics Cloud Help Library*\).



## Procedure

1.  Select the output node of your view to display its properties in the side panel, scroll down to the *Input Parameters* section, and click <span class="FPA-icons"></span> \(Input Parameters\).

2.   In the *Input Parameters* dialog, click <span class="FPA-icons"></span> \(Add\) to create a new parameter. 

3.  Complete the properties of the input parameter:


    <table>
    <tr>
    <th valign="top">

    Property


    
    </th>
    <th valign="top">

    Desription


    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
        Business Name


    
    </td>
    <td valign="top">
    
         Enter a descriptive name to help users identify the object. This name can be changed at any time. 


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
        Technical Name


    
    </td>
    <td valign="top">
    
        Displays the name used in scripts and code, synchronized by default with the *Business Name*.

    To override the default technical name, enter a new one in the field. Technical names can contain only alphanumeric characters and underscores.

    > ### Note:  
    > Once the object is saved, the technical name can no longer be modified.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
        Data Type


    
    </td>
    <td valign="top">
    
        Specify the type of data that the input parameter will contain \(see [Column Data Types](Acquiring-and-Preparing-Data-in-the-Data-Builder/column-data-types-7b1dc6e.md)\), and which should be appropriate for the contexts in which it will be used. Some data types require you to specific a length and or precision.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
        Default Value


    
    </td>
    <td valign="top">
    
        \[optional\] Enter a default value for the input parameter. Each time that a user is required to enter a value for the parameter, they can accept the default value or override it with their own chosen value.


    
    </td>
    </tr>
    </table>
    
4.  Click *OK* to close the dialog and return to the side panel, where the input parameter is available for use.

    The output symbol displays the number of input parameters present in the view. In this example, the source view and output view both contain two input parameters::

    ![](images/Input_Parameters_Source_Symbol_d4621d9.png)

5.  Use the input parameter as appropriate in your view:

    -   In graphical views, input parameters can be used in the following nodes:


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
        
                `Country = :IP_Country`


        
        </td>
        <td valign="top">
        
                Filter node \(see [Filter Data](filter-data-6f6fa18.md)\)

        This filter expression takes the value entered by the user for `IP_Country` and uses it to restrict the data returned by the view to only those rows where the `Country` column contains this value.


        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
                `Total*((100-IP_Discount)/100)`


        
        </td>
        <td valign="top">
        
                Calculated Columns node \(see [Create a Column](create-a-column-3897f48.md)\)

        This expression will fill the column with a value calculated by taking the value in the `Total` column and deducting the percentage value entered by the user.


        
        </td>
        </tr>
        <tr>
        <td valign="top">
        
                `SUM(Revenue) >IP_Min_Rev`


        
        </td>
        <td valign="top">
        
                Aggregation node \(see [Aggregate Data](aggregate-data-7733250.md)\)

        This `HAVING` expression will limit the values aggregated to only those with a total `Revenue` over the value entered by the user.


        
        </td>
        </tr>
        </table>
        
    -   In SQL views, input parameters can be used in your `WHERE` statement and any other appropriate context.

        In this example, two input parameters are defined and used:

        -   `IP_DISCOUNT` - is used to calculate the new column, `Discounted Sale`.
        -   `IP_CITY` - is used in the `WHERE` clause to prompt the user to specify a city to filter on.

        ```
        SELECT "ID",
        	"Date",
        	"City",
        	"Product",
        	"Customer",
        	"Net Sale",
        	"Gross Sale",
        	"Quantity",
        	"Net Sale" * ((100 - :IP_DISCOUNT) / 100) AS "Discounted Sale"
        FROM "Sales"
        WHERE "City" = :IP_CITY
        ```


    > ### Note:  
    > You must use each of the input parameters that you create at least once in your view or you will receive an error instructing you to use or delete them.


