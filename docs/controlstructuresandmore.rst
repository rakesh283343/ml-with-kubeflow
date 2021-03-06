Control structures and more
===========================

This tutorial shows the usage of control structures that skip parts of the pipeline.
It's also a great tutorial demonstrating how kubeflow figures out the order in which to
execute the tasks.

You can run the code on your cluster, or inspect the notebook from the tutorials directory
on github:

`Notebooks directory <https://github.com/gtoonstra/ml-with-kubeflow/tree/master/tutorials>`_

**Important takeaways from the tutorial**

* Kubeflow connects components together by looking at which outputs are used as inputs to other components.
* The type of parameter to a function can have some special meaning or treatment by kubeflow, for example **InputPath** and **OutputPath**.
  So Kubeflow will actually generate the path/filename for these types, so that you don't have to make arbitrary decisions. The UI
  further uses it for immediate display in the browser (clicking on the file downloads it from gcs, or the cluster and you can then
  immediately inspect the contents).
* Obviously you can still pass "simple type" parameters like strings and integers and floats.
* An "op" (task) in kubeflow can explicitly define dependencies by using the "after" method call.
* If you need imports in a python function, you have to import them locally inside the function, not at the top level.
* Conditions can be used to check outputs of a component that skip parts of the flow.
* For complex use cases, you can write a helper python function to drive this decision.
