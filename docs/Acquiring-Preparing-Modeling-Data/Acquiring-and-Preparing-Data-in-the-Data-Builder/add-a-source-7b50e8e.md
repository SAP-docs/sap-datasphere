<!-- loio7b50e8e304244ced9ff1e62e2f2fe919 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Add a Source

Add a source to read data from. You can add multiple sources and combine them together using join or union operators.



<a name="loio7b50e8e304244ced9ff1e62e2f2fe919__steps_ssd_1jj_xrb"/>

## Procedure

1.  If the *Source Browser* panel is not visible on the left of the screen, click *Source Browser* in the toolbar to show it.

2.  Browse or search for the object you want to add on either of the tabs.

    -   The *Repository* tab lists all the tables, views, and intelligent lookups that are available in the space \(including objects shared to the space\).. For more information, see [Add Objects from the Repository](../add-objects-from-the-repository-13fcecd.md).

    -   The *Sources* tab lists all the connections and other data sources that have been integrated to the space from which you can import tables. However it shows only limited records. If you can't see the sources you are looking for, use *Import from Connection* to perform search. You can:

        -   Expand the data sources to browse through their objects \(see [Import an Object from a Connection or Other Source](../import-an-object-from-a-connection-or-other-source-3e6f8f2.md)\).
        -   Open the *Import Objects from Connection* dialog on a particular connection to select multiple objects for import \(see [Import Multiple Objects from a Connection](../import-multiple-objects-from-a-connection-e720b13.md)\).


3.  Select the object of your choice, and then drag and drop it onto the diagram.

    > ### Note:  
    > -   You cannot use views with input parameters as sources in a data flow.
    > -   When browsing a remote file storage such as Amazon Simple Storage Service, Google Cloud Storage, or Microsoft Azure Blob Storage, you can only select files of type JSON/JSONL, CSV, XLS/XLSX, ORC, or PARQUET. Note that each cloud provider has its own naming convention for defining bucket and object names. These conventions should be followed accordingly to avoid any source-related issue. Even though Flowagent-based operators accept most special characters, we recommend that only alphanumeric characters are used \(no multibyte characters\). This will avoid any undesired issue because all sources work well with such characters. Furthermore, some special characters such as ", +, and , are not allowed by our Flowagent File Producer operator and should not be used.
    > -   Local tables with delta capture can be added as source tables. However, only the active records will be used. See [Capturing Delta Changes in Your Local Table](capturing-delta-changes-in-your-local-table-154bdff.md)

    > ### Restriction:  
    > If you add an excel file, you must ensure that the file size does not exceed 50 MB.

4.  Click the source node to display its properties in the side panel, and complete the properties in the *General* section:


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
    
    *Label* 
    
    </td>
    <td valign="top">
    
    Enter a label to display in the source symbol.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Business Name / Technical Name / Type / Connection*
    
    </td>
    <td valign="top">
    
    \[read-only\] Provide information to identify the source table.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    Package
    
    </td>
    <td valign="top">
    
    Select the package to which the object belongs. 

    Packages are used to group related objects in order to facilitate their transport between tenants.

    > ### Note:  
    > Once a package is selected, it cannot be changed here. Only a user with the DW Space Administrator role \(or equivalent privileges\) can modify a package assignment in the *Packages* editor.

    For more information, see [Creating Packages to Export](https://help.sap.com/viewer/9f36ca35bc6145e4acdef6b4d852d560/DEV_CURRENT/en-US/24aba84ceeb3416881736f70f02e3a0a.html "Users with the DW Space Administrator role can create packages to model groups of related objects for transport between tenants. Modelers can add objects to packages via the Package field, which appears in editors when a package is created in their space. Once a package is complete and validated, the space administrator can export it to the Content Network. The structure of your package is preserved and, as the objects it contains evolve, you can easily export updated versions of it.") :arrow_upper_right:.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Type*
    
    </td>
    <td valign="top">
    
    Type of object. For example: a local table.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Status*
    
    </td>
    <td valign="top">
    
    \[read-only\] Displays the deployment and error status of the object. 

    For more information, see [Saving and Deploying Objects](../Creating-Finding-Sharing-Objects/saving-and-deploying-objects-7c0b560.md).
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Use As*
    
    </td>
    <td valign="top">
    
    \[read-only\] Specifies whether the table is used as a Source or Target in the data flow.

    > ### Note:  
    > Changing the use of a table will reset all its properties.


    
    </td>
    </tr>
    </table>
    
5.  In the *Columns* section, review the columns of the source.

    -   To view the data type of a column, hover over it and click <span class="FPA-icons"></span>
    -   If the source is a CSV, JSON, or Excel file, you can change the data type of a column and its corresponding properties by hovering over the column and clicking <span class="FPA-icons"></span> \(Menu\)*Edit Column*.

        > ### Note:  
        > For CSV, JSON, or Excel files, the schema is calculated based on a subset of data and hence you can adjust/verify the suggested data as per your requirements to cover all the data.

    -   For a remote source, you can control the data being read.
        -   To add/delete columns from source, click <span class="FPA-icons"></span>/<span class="FPA-icons"></span> \(Delete\) respectively.
        -   To add new/removed columns from the source based on latest metadata, click <span class="SAP-icons"></span> \(Refresh to fetch column changes from source\)


6.  \[optional\] For CDI, OData, and ABAP CDS sources complete the *Source Filters* section to define filter conditions for the consumption of their data:

    When defining filter conditions for columns,the following rules are applied:

    -   An "OR" is applied between the conditions defined on the same column.
    -   An "AND" is applied between the conditions defined on different columns.

    > ### Note:  
    > To apply the defined filters upon data preview, toggle the switch button, *ON* in the *Properties* pane.

    For SAP SuccessFactors, OData, and Cloud Data Integration \(CDI\) sources, you can enable delta loading. That is, move over the changed data records instead of doing a full load every time.

    To do this, in the *Source Filters* dialog, you must manually enter the condition `$MAX_VALUE_<column_name>` in the *Value* field.

    `<column_name>` is a column in the target table where data is being replicated, normally of type `date` or `timestamp`.

7.  \[optional\] For source tables from OData remote connections, you can add or edit the parameters of a selected source table in the *OData Parameters* section. OData parameters allow you to define additional information or constraints to control how the data is returned from the OData connection. Click <span class="FPA-icons"></span> \(Define Parameters\) to open the *OData Parameters* dialog. You can:

    -   Manually enter a custom parameter according to URI conventions \(see [URI Conventions](https://www.odata.org/documentation/odata-version-2-0/uri-conventions/)\).

    -   Click the *Parameters* dropdown button to see a list of suggested parameters.


    Add a value and click *OK* to validate your changes or *Reset* to erase all parameters.

    In the *OData Parameters* section, enable the *Apply Parameters on Preview* toggle if you want to see how the changes in parameter impact the table preview.

8.  \[optional\] For source tables from OData remote connections, you can edit the depth properties of a selected source table in the *OData Properties* section. Click <span class="FPA-icons"></span> \(Edit OData Properties\) to open the *OData Properties* dialog. You can set the depth of the source table to either 1 or 2.

    The depth of an OData object refers to the level of related entities that are included in the response when querying the OData service. The depth is by default set to 1 so that only the properties of the requested entity are returned. You can change the depth to 2 to include a second level. Depth is useful when you want to optimize performance by controlling the amount of data returned in a single request.

    > ### Example:  
    > If an OData service has two objects for `Products` and `Orders`, and a `Product` object has a navigation property to related `Order` objects, a request for a specific `Product` with a depth of 1 will return the properties of that `Product`, but not the related `Order` objects. But if you specify a depth of 2, it will also return the related `Order` objects and their properties.

    > ### Restriction:  
    > When the depth is set to 2, the *Columns* section shows the columns from the two collections \(or levels\) and the following problems occur:
    > 
    > -   The*Data Preview* cannot show more than one collection. The columns from the second collection cannot be previewed.
    > 
    > -   The Data Flow run will fail.
    > 
    > Retaining columns from just one collection and deleting the rest fixes both issues.

9.  \[optional\] For sources that are files, complete the appropriate additional section:

    -   For `.csv` files, click *Modify* in the *CSV Properties* section to configure various csv properties for your `.csv` file \(column separator, text separator, character set, escape character, etc.\).
    -   For `.json` and `.jsonl` files, click *Modify* in the *JSON Properties* section to configure the flattening levels of the JSON file.
    -   For `.xls` and `.xlsx` files, click *Modify* in the *Excel Properties* to choose the Excel worksheet to be used and to set a header row.

    > ### Note:  
    > You can reset all your changes in the section by clicking *Modify* \> *Reset*.

10. \[optional\] In the *Advanced* section, configure the following properties:


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
    
    *Control Fetch Size*
    
    </td>
    <td valign="top">
    
    To enforce a specific value for Batch Size, toggle this switch.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Fetch Size \(Number of Rows\)*
    
    </td>
    <td valign="top">
    
    Specifies the amount of data being read. It indicates the number of rows that will be committed to target on each batch.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Batch Query*
    
    </td>
    <td valign="top">
    
    Fetches the data batch by batch according to the fetch size defined above. Use this option for very large odata source files.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Fail Run on String Truncation*
    
    </td>
    <td valign="top">
    
    Fails the data flow run if string truncation is detected while fetching the source columns. This property is available only for CSV, JSON, and Excel files.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Enable ODBC Tracing*
    
    </td>
    <td valign="top">
    
    : \[SAP HANA connection only\] Enable this option to create a new log file in the vflow graph pod with HANA ODBC debug logs.

    > ### Caution:  
    > Enabling this option must be used for troubleshooting purposes only, as it uses a lot of system resources.


    
    </td>
    </tr>
    </table>
    
    > ### Note:  
    > You can reset all your changes in the section by clicking *Restore Default*.

11. To finalize the source, create a flow from it to an operator or to the target table, as appropriate.


