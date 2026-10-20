<!-- loio5064ede215654f2eb6e18b86a29dfab5 -->

<link rel="stylesheet" type="text/css" href="../css/sap-icons.css"/>

# Run Expression Evaluator Tasks in a Task Chain

Use the Expression Evaluator task to compute a small calculation based on input and output parameters. You can reuse this calculation later as an input parameter in the task chain.



## Prerequisites

Users require the usual Modeler and Integrator role permissions to model and run any task chain that includes an Expression Evaluator task.

> ### Note:  
> Only HANA spaces are supported to utilize expression tasks.



## Context

-   To add an Expression Evaluator task to a task chain, you need to click and drag the Expression Evaluator task object \(<span class="FPA-icons-V3"></span> \) from the toolbar to the task chain canvas. \(This is different than the way in which you can select and drag other SAP Datasphere object types directly from the Repository to the canvas.\)
-   Once you’ve added a new Expression Evaluator task object to the canvas, you configure the expression in the *Properties* pane.
-   The Expression Evaluator task will automatically create an output parameter that can be used as an input parameter in another task in the task chain.



## Procedure

1.  To add an Expression Evaluator task to a task chain, you need to click and drag the Expression Evaluator task object \(<span class="FPA-icons-V3"></span> \) from the toolbar to the task chain canvas.

    A new Expression Evaluation task object is added to the task chain canvas. While the object is selected, the *Properties* pane provides configuration information that details the task’s operation.

2.  In the *General* section of the Properties pane, type a new technical name to represent the expression task in the task chain.

3.  Create am expression in the *Expression* box provided.

    Below the *Expression* there a 3 tabs that provide operations that you can add to the expression.

    ****


    <table>
    <tr>
    <th valign="top">

    Properties
    
    </th>
    <th valign="top">

    Comments
    
    </th>
    </tr>
    <tr>
    <td valign="top">
    
    *Functions* 
    
    </td>
    <td valign="top">
    
    This provides a list of functions that you can add to your expression task.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Input Parameters* 
    
    </td>
    <td valign="top">
    
    This provides a list of any input parameters that you have created in the expression task that you can add.
    
    </td>
    </tr>
    <tr>
    <td valign="top">
    
    *Others* 
    
    </td>
    <td valign="top">
    
    This provides a list of other operations you can add to your expression task.
    
    </td>
    </tr>
    </table>
    
4.  After you’ve completed the configuration of an expression task, you can expand the last section of the Properties pane, *Test Run*, to perform a test run of your expression task. To initiate the test, click the*Test Run* button. This will run the single task so you can evaluate the results without having to run the entire task chain.

5.  Add a value to the output parameter dialog box.

6.  Following verification that your expression task can be run successfully, you can proceed with any other setup and inclusion of other objects in the task chain, and then run or schedule the entire task chain. As with any other objects in a task chain, you can monitor details of the execution of an API task in the *Data Integration* monitoring app.


