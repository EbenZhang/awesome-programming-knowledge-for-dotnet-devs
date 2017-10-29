Sometimes you own PC may not have the environment \(e.g. hardware\) to debug an application, in this case you may want to debug the application running on another device.

In summary you'll need the debugger on your local machine, an debugger agent on the remote machine. You can debug Native C++, Managed .NET code, and also mixed projects.

## Connectivity to the Remote Machine

Make sure your PC can connect to the remote machine over network, so can Visual Studio.

## Remote Debugging Agent

Install `Remote Tools for Microsoft Visual Studio 2013`\(Assuming Visual Studio 2013 is used for debugging\) on the remote machine.

Once installed, you should be able to find it from the start menu:

![](/assets/VisualStudioRemoteDebugAgent.png)

Now right click and run the `Remote Debugger` as admin, and select the `Tools` -&gt; `Options` menu to configure the authentication.

![](/assets/RemoteAgentConfigurationMenus.png)

![](/assets/RemoteDebugAgentAuthentication.png)

Here I'm using `No Authentication` as security is not a concern and I'm going to use the agent for a very short time in intranet.

You may also want to increase the idle time otherwise the agent will stop working after the idle time.

## Run the Target Application

* Compile your code, better to use debug version, but release version \(code optimized\) with PDB is also OK if you have no choice for example the application only crashes in release mode

* Copy assembly to the target machine
* Start the application as you normally do

## Debug in Visual Studio

Back to your local machine, open Visual Studio and the solution of the code of course.

Version:0.9 StartHTML:0000000221 EndHTML:0000001057 StartFragment:0000000257 EndFragment:0000001021 SourceURL:https://helixleisure.atlassian.net/wiki/spaces/EM/pages/166363307/Debugging+Remotely+using+Visual+Studio

* Select the`Debug -> Attach To Process`
* Select`Remote (no authentication)`\(up to the Authentication method you've configured previously\) as the Transport, put the IP of the remote machine into the`Qualifier`text box \(e.g `172.16.10.61`\) and press the`Refresh`button. You need to tick the `Show processes from all users` if the application was started by another user rather than the one who started the remote debug agent.
* Select application from the list and press the `Attach` to start debugging

![](/assets/RemoteDebugProcessSelection.png)





