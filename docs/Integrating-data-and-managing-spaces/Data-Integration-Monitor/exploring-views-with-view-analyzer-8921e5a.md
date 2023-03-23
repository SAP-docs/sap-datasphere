<!-- loio8921e5acf2ad4c8a98073edae4c214c7 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Exploring Views with View Analyzer

Use the *View Analyzer* to explore graphical or SQL views, and the entities they consume.

The *View Analyzer* provides you with statistics and useful information on each entity that composes your view, no matter the complexity of the view. It analyzes each view definition, the consumed views, the local tables and the data sources used by remote tables that compose your data model. You can then use this information to optimize your data model, and decide, for example, which view to persist when performance or technical problems such as out-of-memory errors occur.

> ### Note:  
> While working with complex views, see [View Persistency and Memory Consumption](view-persistency-and-memory-consumption-e3d0495.md).

To use the *View Analyzer*,

1.  Go to *Data Integration Monitor* \> *View Persistency Monitor*. Select the view you need to analyze and navigate to the details screen of this view.

    > ### Note:  
    > You need to select a space if you are member of several spaces.

2.  Select *View Persistency* \> *Start View Analyzer*.

    You can choose between 2 options:

    -   Run the *View Analyzer* without memory consumption: The *View Analyzer* will not execute the persistency simulation. For views already persisted , the memory consumption of view persistency task will be shown. The analyzer will analyze the entities that compose your data model and will provide you with the information it has collected.

        ![](images/View_Analyzer_Settings_Without_Memory_Consumption_cff6761.png)

    -   Run the *View Analyzer* with memory consumption: In addition to exploring the entities that compose your data model, the analyzer will execute the persistency simulation for non persisted views. It will report the memory consumption that would be used to get an entity persisted or will provide you with the actual memory consumption used when you have persisted your data. The simulations are executed sequentially as they may add some workloads to the system. To reduce these workloads, you can define a limit to the memory consumption that can be used to persist the view thanks to the threshold. If one of the analyzed views exceeds the limit, then no further view persistency simulations are run.

        ![](images/View_Analyzer_Settings_With_Memory_Consumption_6fe57f8.png)

        Note: The maximum memory consumption is based on the statement memory limit of the space workload configuration. For more information on statement limits, see [Set a Priority and Statement Limits for a Space](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/internal/en-US/d66ac1efb5054068a104c4559b72d272.html "Use the properties in the Workload Management section to prioritize between spaces for resource consumption and set limits to the amount of memory and threads that a space can consume.") :arrow_upper_right:.

        > ### Caution:  
        > To use the *View Analyzer* with memory consumption during persistency simulation, you must enable *Expensive Statement Tracing* in :wrench:. For more information, see [Analyze Monitoring Data in a Space](https://help.sap.com/viewer/935116dd7c324355803d4b85809cec97/internal/en-US/9cd0691c44a74f2aa47b52f615f74433.html "Define the two spaces dedicated to monitoring SAP Datasphere (such as monitoring the database for resource consumption).") :arrow_upper_right:.


3.  Analyze your results

    To understand how you can interpret the analyzer's findings, let's take an example with the following View\_001\_001. It consumes 4 views \(in red\) and 4 remote tables \(in purple\): ![](images/View_Analyzer_Example_with_an_Analyzed_View_a5955d0.png)

    Now, let's start the *View Analyzer* with memory consumption. On the total of 8 GiB that I have allowed in my statement memory limit, let's decide to limit the memory consumption to 4 GiB. This means that if a persistency task exceeds this limit, the next persistency simulations will be canceled:

     ![](images/View_Analyzer_Settings_ec24c8a.png)

    Once the *View Analyzer* has completed the task, 2 tabs are available in the details screen:

    -   *Task Log*: It contains all information related to the *View Analyzer* task itself. You can see that my 5 views have been analyzed, and an overview of some key indicators is displayed: memory consumption, number of records, etc.

        ![](images/TaskLog_AnalyzedView_cc9147b.png)

    -   *Entities*: It contains the details of the *View Analyzer* findings per analyzed entities. Information is displayed in a table format:

         ![](images/Analyzed_View_Entities_tab_ac6253e.png)


        <table>
        <tr>
        <th valign="top">

        Column


        
        </th>
        <th valign="top">

        Description


        
        </th>
        </tr>
        <tr>
        <td valign="top">

        *Entity Name*


        
        </td>
        <td valign="top">

        Name of the analyzed entity. It can be a local or a remote table, a view, a shared entity, an external entity, an intelligent lookup and or a data access control.


        
        </td>
        </tr>
        <tr>
        <td valign="top">

        *Persisted*


        
        </td>
        <td valign="top">

        Indicates if the view is already persisted, or the remote table replicated.


        
        </td>
        </tr>
        <tr>
        <td valign="top">

        *Partitions*


        
        </td>
        <td valign="top">

        Indicates if partitions have been defined for the analyzed views.

        > ### Note:  
        > If partitions have been defined for remote tables, it's not displayed. Only partitions defined for views are indicated by the *View Analyzer*.


        
        </td>
        </tr>
        <tr>
        <td valign="top">

        *Peak Memory \(MiB\)*


        
        </td>
        <td valign="top">

        Indicates the memory used during the simulation, or in case of the view already persisted, the memory used to persist the view.


        
        </td>
        </tr>
        <tr>
        <td valign="top">

        *Row*


        
        </td>
        <td valign="top">

        Indicates the number of rows


        
        </td>
        </tr>
        <tr>
        <td valign="top">

        *Duration*


        
        </td>
        <td valign="top">

        Indicates the duration in second to persist the view \(simulation or actual persistency\).


        
        </td>
        </tr>
        <tr>
        <td valign="top">

        *Adapter*


        
        </td>
        <td valign="top">

        Indicates if an adapter is used to access the remote table source.


        
        </td>
        </tr>
        </table>
        
        If you click on an entity row or click the \>, you'll access the details for the selected entity. For example, if I click on the table SCARR:

         ![](images/ViewAnlayzer_OneEntityDetails_6d347d9.png)

        In the message's details, you can see that the remote table is using an adapter that has limited capacities. This is why the entity was marked with a warning in the results.

        From the *Entities* tab, you can do many actions to explore your results:


        <table>
        <tr>
        <th valign="top">

        Action


        
        </th>
        <th valign="top">

        Description


        
        </th>
        </tr>
        <tr>
        <td valign="top">

        <span class="FPA-icons"></span> \(Sort\)


        
        </td>
        <td valign="top">

        Set sort order and sort columns:

        ![](images/Sort_View_Analyzer_Results_dd1987f.png)


        
        </td>
        </tr>
        <tr>
        <td valign="top">

        <span class="SAP-icons"></span> \(Filter\)


        
        </td>
        <td valign="top">

        Filter your results:

        ![](images/Filter_View_Analyzer_Results_1615f32.png)


        
        </td>
        </tr>
        <tr>
        <td valign="top">

         <span class="FPA-icons"></span> \(Inspect\)


        
        </td>
        <td valign="top">

        Display the whole list of results that you can also export in CSV format:

        ![](images/View_Analyzer_Full_list_of_Results_6fb1d68.png)


        
        </td>
        </tr>
        <tr>
        <td valign="top">

        *Start Analyzer*


        
        </td>
        <td valign="top">

        You can select one or more views and start a new view analyzer.

        > ### Note:  
        > The analyzer will always start from the main view. Selecting the views here in the entity list, or in the lineage graph has an effect only on the persistency simulation. In case memory consumption is chosen, the persistency simulation will be executed for the selected views, regardless of their persistency status.


        
        </td>
        </tr>
        <tr>
        <td valign="top">

        <span class="FPA-icons"></span> \(Lineage View\)


        
        </td>
        <td valign="top">

        Display the Lineage graph:

        ![](images/View_Analyzer_Impact_and_Lineage_graph_fcf57ea.png)

        If you click on one entity from the graph, you can see the view analyzer results and the indicators. For example, I click on SpfiJoinScarr view:

        ![](images/Graph_View_for_one_Entity_Details_cad8d32.png)

        > ### Note:  
        > It is also possible to select multiple views here and start the *View Analyzer* with memory consumption.


        
        </td>
        </tr>
        </table>
        


> ### Note:  
> The *View Analyzer* is executed in asynchronous mode. If necessary, for example if the run takes too long, you can select the task and use the *Cancel Run* button to stop it.

