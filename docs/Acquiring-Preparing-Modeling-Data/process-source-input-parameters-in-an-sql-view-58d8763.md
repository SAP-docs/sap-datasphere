<!-- loio58d8763437ac46b7924405acff7f39db -->

# Process Source Input Parameters in an SQL View

Process input parameters contained in source views by mapping them to new input parameters or entering a value to resolve them.



## Context

Graphical and SQL views can contain input parameters, which prompt the user to enter a value for use in filtering or other calculations when the view is run \(see [Create an Input Parameter](create-an-input-parameter-53fa99a.md)\).

When adding such a view as a source in your SQL view, you must process each of the input parameters.



## Procedure

1.  Add a view to your SQL view by typing its name or by dragging it from the *Source Browser* into the editor panel.

    If the view contains input parameters it will be added to your code in the following syntax, which differs slightly between SQL and SQLScript:


    <table>
    <tr>
    <th valign="top">

    SQL View


    
    </th>
    <th valign="top">

    SQLScript View


    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
        ```
    "<SourceName>"(<IPName>: :PARAM_1)
    ```


    
    </td>
    <td valign="top">
    
        ```
    "<SourceName>"(<IPName>=>:PARAM_1)
    ```


    
    </td>
    </tr>
    </table>
    
2.  Choose how you want to process each input parameter. You can:

    -   Map the source input parameter to an input parameter in the view.

        You must first create the input parameter in the side panel \(see [Create an Input Parameter](create-an-input-parameter-53fa99a.md)\) and then enter its name in the code, prefixed by a colon. The new input parameters can have the same name as the source input parameters, but this is not required.

        In this example the `Sales` view is added as a source and its input parameters, `IP_CITY` and `IP_DISCOUNT`, are mapped to new input parameters with the same names:


        <table>
        <tr>
        <th valign="top">

        SQL View


        
        </th>
        <th valign="top">

        SQLScript View


        
        </th>
        </tr>
        <tr>
        <td valign="top">
        
                ```
        "Sales"(IP_CITY: :IP_CITY,IP_DISCOUNT: :IP_DISCOUNT)
        ```


        
        </td>
        <td valign="top">
        
                ```
        "Sales"(IP_CITY=>:IP_CITY,IP_DISCOUNT=>:IP_DISCOUNT)
        ```


        
        </td>
        </tr>
        </table>
        
    -   Enter a value to resolve the input parameter.

        In this example the `IP_CITY` and `IP_DISCOUNT` input parameters are set to the values `Tokyo` and `10` respectively:


        <table>
        <tr>
        <th valign="top">

        SQL View


        
        </th>
        <th valign="top">

        SQLScript View


        
        </th>
        </tr>
        <tr>
        <td valign="top">
        
                ```
        "Sales"(IP_CITY: 'Tokyo',IP_DISCOUNT: 10)
        ```


        
        </td>
        <td valign="top">
        
                ```
        "Sales"(IP_CITY=>'Tokyo',IP_DISCOUNT=>10)
        ```


        
        </td>
        </tr>
        </table>
        

3.  Click *Validate SQL* to validate the completed syntax.


