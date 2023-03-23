<!-- loioaa11efbc64ce411d9006562cf03e62f9 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Configure the View Output by an Intelligent Lookup

Your intelligent lookup outputs a view that can be used as a source for other views. The view is available for use as soon as the intelligent lookup is run.



## Context

You can use the output of your intelligent lookup as a source for a view or data flow, where it will be listed in the *Source Browser* on the *Repository* tab in the *Intelligent Lookups* category.

> ### Note:  
> The following restrictions apply to the view produced by an intelligent lookup. You cannot:
> 
> -   Expose an intelligent lookup for consumption directly \(though it can serve as the source for a view that is exposed\).
> -   Show an intelligent lookup in an E/R model.
> -   Share an intelligent lookup to another space.



## Procedure

1.  Click the *Output* node and configure the view that will be output by your intelligent lookup.

2.  In the *General* section, enter the following properties:


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

    Semantic Usage


    
    </td>
    <td valign="top">

    \[read-only\] The semantic usage of the view produced by an intelligent lookup is always set to *Relational Dataset*.


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    Include Review Records


    
    </td>
    <td valign="top">

    Include all records that remain in the *Review* category in the output. 

    Default: *On*


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    Include Unmatched Records


    
    </td>
    <td valign="top">

    Include all records that remain in the *Multiple* and *Unmatched* categories after all rules are applied in the output. Input records in these categories have default values assigned in their return columns. 

    Default: *Off*


    
    </td>
    </tr>
    <tr>
    <td valign="top">

    Include "Unmatched Record" Column


    
    </td>
    <td valign="top">

    Adds an *Unmatched Record* column to the intelligent lookup output. 

    This column contains the value *Yes* if the record remains in either the *Multiple* or *Unmatched* category after all rules are applied.


    
    </td>
    </tr>
    </table>
    
3.  In the *Columns* section, review the columns that will be output in the view .

4.  \[optional\] To set a default value for a return column \(to be used when the *Include Unmatched Records* option is enabled\), hover over the return column, click <span class="FPA-icons"></span> \(Menu\)** \> *Set Default Value*, enter a default value in the dialog and click *OK*.

    The default value is shown on the token under the column name.


