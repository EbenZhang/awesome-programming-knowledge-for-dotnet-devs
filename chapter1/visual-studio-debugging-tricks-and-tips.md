# First chance, second chance exception and exception settings

See [here](https://blogs.msdn.microsoft.com/davidklinems/2005/07/12/what-is-a-first-chance-exception/) for the definition of the first chance exception. A first chance exception will be either handled or left unhandled. If a first chance exception is not handled then the debugger will receive a second chance exception notification and crash the application.

Sometimes you may want to break the application immediately to see more details and context \(e.g. parameters\) of the exception when the first chance exception notification is raised, especially when debugging a complex application with the exception handler far away from where the exception is raised.

See [here](https://docs.microsoft.com/en-us/visualstudio/debugger/managing-exceptions-with-the-debugger) for instructions to configure Visual Studio to break on specific exceptions. In addition, I would like to mention that

* You can add an exception if it is not in the list
* Starting from Visual Studio 2017, you can break on exception for a specific module

  


**Postmortem of a dump file**

  


See

[here](https://docs.microsoft.com/en-us/visualstudio/debugger/using-dump-files)

\(Microsoft\) 

and

[here](https://en.wikipedia.org/wiki/Core_dump)

\(Wikipedia\) for the definition of a dump. A lot of tools can create dump file such as 

TaskMgr,

[ProcDump](https://docs.microsoft.com/en-us/sysinternals/downloads/procdump)

, and Visual Studio. S

ee

["What is a dump and how do I create one"](https://blogs.msdn.microsoft.com/debugger/2009/12/30/what-is-a-dump-and-how-do-i-create-one/)

.

  


To debug a dump file in Visual Studio, you can just simply click the 

File

  


Visual Studio is capable to debugging dump files.

Trace point and conditional break point

pin a variable

  


Use dot peek as symbol server when you dont have the pdb of a dll

  


Remote debugging

  


Tips

run to cursor

step into specific method

  


object id

return value of a function

modify variable at runtime

debug display attribute

\[DebuggerDisplay\("Count = {Values.Count}, {DebugString}"\)\]

start 

debug 

multiple applications kiosk 

and kioskservice

innerexception show

stepover property

debug into .net source code

  


  


