<!-- loioab490fb4d083442197e2ba3b92079734 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Add a Target

Select a target \(connection and container\) to define the target environment for your replication flow.



<a name="loioab490fb4d083442197e2ba3b92079734__context_rr5_54f_vvb"/>

## Context

-   Connections are created by your system administration. You can only use a target if a connection has been created for it in your space and if you have the necessary authorizations.

-   Containers are the parent objects that hold the data.




## Procedure

1.  Choose <span class="FPA-icons"></span> \(Browse target connections\). A list of available target connections appears.

2.  Select the relevant one for your use case.

3.  If you replicate to the local repository \(SAP Datasphere\), the target container is automatically defined as the space you are in. For any other target, click *Browse target container*. A list of available containers appears. Select the relevant one for your use case.

    To narrow down the selection, start typing a part of the container name in the *Search* field.

4.  If you select a cloud storage \(Data Lake Files from SAP HANA Cloud, data lake\) as the target, a list of additional options is displayed. Choose the relevant ones for your use case.


    <table>
    <tr>
    <th valign="top">

    Option


    
    </th>
    <th valign="top">

    Description


    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
        **Group Delta By**


    
    </td>
    <td valign="top">
    
        For *Load Type* of *Initial and Delta*: Choose *None*, *Date*, or *Hour*.

    Specifies whether to create additional folders for sorting updates based on the date or hour.


    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
        **File Type**


    
    </td>
    <td valign="top">
    
         *csv*:

    -   *File Delimiter*: Specifies the character to use as a delimiter for columns in CSV files.
    -   *File Header*: Specifies whether CSV files include a header row with the column names.

    *parquet*:

    -   *File Compression*: Specifies the compression algorithm to use for parquet files \(*None*, *GZIP*, *Snappy*\).

     *json*:

    -   *Encoding*: Generated JSON files are encoded in UTF-8 format.

    -   *Orient*: Specifies the internal structure of the produced JSON files:*"records"*: \[\{column -\> value\}, ... ,\{column -\> value\}\]

     *jsonlines*:

    -   *Encoding*: Generated JSON Lines files are encoded in UTF-8 format.



    
    </td>
    </tr>
    </table>
    

