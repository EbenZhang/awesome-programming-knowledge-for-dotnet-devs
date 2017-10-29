See [here](https://blogs.msdn.microsoft.com/davidklinems/2005/07/12/what-is-a-first-chance-exception/) for the definition of the first chance exception. A first chance exception will be either handled or left unhandled. If a first chance exception is not handled then the debugger will receive a second chance exception notification and crash the application.

Sometimes you may want to break the application immediately to see more details and context \(e.g. parameters\) of the exception when the first chance exception notification is raised, especially when debugging a complex application with the exception handler far away from where the exception is raised.

See [here](https://docs.microsoft.com/en-us/visualstudio/debugger/managing-exceptions-with-the-debugger) for instructions to configure Visual Studio to break on specific exceptions. In addition, I would like to mention that

* You can add an exception if it is not in the list
* Starting from Visual Studio 2017, you can break on exception for a specific module
* The Managed Debug Assist is very useful to catch unintended behaviour if your .NET application has interoperation with native code.



