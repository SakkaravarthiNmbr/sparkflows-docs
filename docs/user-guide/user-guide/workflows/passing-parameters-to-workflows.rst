Passing Parameters to Workflows
===============================


Fire Insights runs the spark jobs with ``spark-submit``. It takes in the workflow JSON as a parameter. There are multiple ways to pass extra parameters to the workflow. If the same parameter is specified multiple times, the order of precendence in which they are applied is as shown below:
 
  * Through Program Parameters passed during Workflow Execution
  * By specifying the parameters in the Workflow Editor
  * Through a Parameter Processor in the workflow
  * A Node creating a variable during execution time


Through Program Parameters in Fire during Workflow Execution
------------------------------------------------------------

Key/Value pairs can be passed to Fire during Workflow Execution. An example of it is ``--var data=1``
These Key/Value pairs would override any Key/Value pair passed through the Parameter Processor in the workflow.

Below is a screenshot:

.. figure:: ../../_assets/user-guide/passing-parameters-1.png
   :alt: Passing Parameters to Workflows

By specifying the parameters in the Workflow Editor
---------------------------------------------------

Parameters can be specified in the Workflow Editor. They can be specified in the following format:

They can be passed with ``--var name1=value1  --var  name2=value2``

  
Through a Parameter Processor in the Workflow
-----------------------------------------
 
A Parameter Processor can be added to the workflow. It allows passing key/value pairs to the workflow.

.. figure:: ../../_assets/user-guide/passing-parameters-2.png
   :alt: Passing Parameters to Workflows
   
A Processor creating a variable during execution time
------------------------------------------------

A Processor can also create a parameter during run time. A Processor creates a new variable and puts it into the JobContext.

jobContext.nodeGeneratedParameters.put(variable, ""+count);

This parameter can then be later used by another Processor.

For example ``NodeCount`` puts the count of records into a variable in the Job Context.

``NodeAssert`` uses this variable when evaluating expressions.

   
Through ``--var`` parameters with spark-submit
--------------------------------------------------
 
Fire Insights workflow can also be directly executed on the cluster with spark-submit.

In this case, extra parameters can be passed with ``--var``::

 
    spark-submit    --class fire.execute.WorkflowExecuteFromFile    --master yarn    --deploy-mode client   fire-core-3.1.0-jar-with-dependencies.jar    --postback-url http://<machine>:8080 --job-id 1      --workflow-file kmeans.wf    --var name1=value1  --var  name2=value2

 
In the workflow, these parameters can be used with ``$name1    $name2``
 
Specific nodes make use of the parameters by **substituting   $name   with the value** provided for the name.


An **example** would be :     ``--var id=3``

When specifying the expression in the RowFilter Node we can use :   ``id > $id``

In the above **$id** would be replaced with **3**.
 
 

Specifying ``--var`` parameters for all in Sparkflows User Interface
-----------------------------------------------------------------
 
Sparkflows also allows specifying the **--var** parameters to be passed to all the jobs submitted through Sparkflows. Below is the screen under Administration/Configuration.

.. figure:: ../../_assets/user-guide/passing-parameters-3.png
   :alt: Passing Parameters to Workflows
   
In the above, **app.vars** parameter allows specifying a space separated list of name=value pairs. 

Each of these are passed to the jobs submitted by Sparkflows with ``--var name=value``
