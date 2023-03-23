<!-- loiod66ac1efb5054068a104c4559b72d272 -->

# Set a Priority and Statement Limits for a Space

Use the properties in the *Workload Management* section to prioritize between spaces for resource consumption and set limits to the amount of memory and threads that a space can consume.



<a name="loiod66ac1efb5054068a104c4559b72d272__steps_abz_fhb_wrb"/>

## Procedure

1.  In the side navigation area, click ![](../images/Space_Management_a868247.png) \(*Space Management*\), locate your space tile, and click *Edit* to open it. Then, select *Workload Management*.

2.  To prioritize between spaces, enter in the *Space Priority* section the prioritization of this space when querying the database. You can enter a value from 1 \(lowest priority\) to 8 \(highest priority\). The default value is 5. In situations where spaces are competing for available threads, those with higher priorities have their statements run before those of spaces with lower priorities.

3.  To manage other workload parameters, you can select either of the following in the *Space Configuration* dropdown list:

    -   *Default*. The default configuration provides generous resource limits, while preventing any single space from overloading the system. The default configuration is applied by default to new spaces.

        These statement limit and admission control parameters are taken into account in the default configuration and cannot be changed:


        <table>
        <tr>
        <th valign="top">

        Parameter Type


        
        </th>
        <th valign="top">

        Parameter


        
        </th>
        <th valign="top">

        Value


        
        </th>
        </tr>
        <tr>
        <td valign="top">

        Admission Control


        
        </td>
        <td valign="top">

        ADMISSION CONTROL QUEUE CPU THRESHOLD


        
        </td>
        <td valign="top">

        80%


        
        </td>
        </tr>
        <tr>
        <td valign="top">

        Statement Limits


        
        </td>
        <td valign="top">

        TOTAL STATEMENT THREAD LIMIT


        
        </td>
        <td valign="top">

        80%


        
        </td>
        </tr>
        </table>
        
    -   *Custom*. These statement limit and admission control parameters are taken into account in the custom configuration. You can specify only the value for statements limits to set maximum total thread and memory limits that statements running concurrently in the space can consume:

        > ### Caution:  
        > Be aware that changing the statement limits may cause performance issues.


        <table>
        <tr>
        <th valign="top">

        Parameter Type


        
        </th>
        <th valign="top">

        Parameter


        
        </th>
        <th valign="top">

        Value


        
        </th>
        </tr>
        <tr>
        <td valign="top">

        Admission Control


        
        </td>
        <td valign="top">

        ADMISSION CONTROL QUEUE CPU THRESHOLD


        
        </td>
        <td valign="top">

        80%


        
        </td>
        </tr>
        <tr>
        <td valign="top" rowspan="2">

        Statement Limits


        
        </td>
        <td valign="top">

        TOTAL STATEMENT THREAD LIMIT


        
        </td>
        <td valign="top">

        In the *Total Statement Thread Limit* area, enter the maximum number \(or percentage\) of threads that statements running concurrently in the space can consume. You can enter a percentage between 1% and 70% \(or the equivalent number\) of the total number of threads available in your tenant.

        Setting this limit prevents the space from consuming too many threads, and can help with balancing resource consumption between competing spaces.

        > ### Caution:  
        > Be aware that setting this limit too low may impact statement performance, while excessively high values may impact the performance of statements in other spaces.

        > ### Note:  
        > If you’ve set a thread limit percentage \(or number\) that is no longer allowed, it is changed to the default percentage 70% \(or to the number corresponding to 70% of the total number of threads\).

        Default: 70%


        
        </td>
        </tr>
        <tr>
        <td valign="top">

        TOTAL STATEMENT MEMORY LIMIT


        
        </td>
        <td valign="top">

        In the *Total Statement Memory Limit* area, enter the maximum number \(or percentage\) of GBs of memory that statements running concurrently in the space can consume. You can enter any value or percentage between 0 \(no limit\) and the total amount of memory available in your tenant.

        Setting this limit prevents the space from consuming all available memory, and can help with balancing resource consumption between competing spaces.

        > ### Caution:  
        > Be aware that setting this limit too low may cause out-of-memory issues, while excessively high values or 0 may allow the space to consume all available system memory.

        Default: 80%


        
        </td>
        </tr>
        </table>
        
        > ### Note:  
        > Admission control is designed to avoid overloading the system under peak load by denying any further SQL requests when the load on the system is equal to or exceeds a given threshold.
        > 
        > You can investigate why statements are being queued.
        > 
        > -   Events related to requests which have been queued for longer than 5 seconds are logged and can be reviewed in the M\_ADMISSION\_CONTROL\_EVENTS view. For more information, see [Managing Peak Load \(Admission Control\)](https://help.sap.com/viewer/f9c5015e72e04fffa14d7d4f7267d897/latest/en-US/8569dd96c6ab4849a21f4a97d1ffe832.html) in the *SAP HANA Cloud, SAP HANA Database Administration Guide*.
        > 
        > -   You can monitor the statements that are queued by viewing the cards dedicated to admission control in the *Dashboard* tab of the *System Monitor*. For more information, see [Monitoring SAP Datasphere](../Monitoring-SAP-Datasphere/monitoring-sap-datasphere-28910cd.md).
        > 
        > 
        > A statement which exceeds a threshold is rejected with the SQL error 616: "rejected by workload class configuration, Code: 616, SQL State: HY000". A statement which exceeds a queue threshold is queued for up to 10 minutes, after this time the statement is rejected. For more information, see [Properties for Workload Classes and Mappings](https://help.sap.com/viewer/f9c5015e72e04fffa14d7d4f7267d897/latest/en-US/3ae17c3b1d6c4adea6f0ddfec3041dd4.html) in the *SAP HANA Cloud, SAP HANA Database Administration Guide*.


4.  Click *Save* to save your changes to the space, or *Deploy* to save and immediately make the changes available to space members.


