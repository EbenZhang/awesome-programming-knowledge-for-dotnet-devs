# Trace Point and Conditional Break Point

## Trace Point

Besides the normal break point, you can also set trace point and conditional break point. Trace point is a special break point can be used to print variables along with some text to the output and continue the execution without breaking the application. It works as if you put the code like `Trace.TraceInformation("blahblah......")`.

To set a trace point you need to first set a normal break point and then convert it to a trace point by adding an action, which can be achieved by right clicking the break point and set the actions.

![](../../../.gitbook/assets/advancedbreakpoint.png) ![](../../../.gitbook/assets/tracepointactions.png)

## Conditional Break Point

Conditional break point is another kind of special break point that can break the application when certain criteria are met. Similar to trace point, you can convert a normal break point to conditional break point by right clicking the break point and select the `Conditions`to add your conditions.

![](../../../.gitbook/assets/conditionalbreakpoint.png)

