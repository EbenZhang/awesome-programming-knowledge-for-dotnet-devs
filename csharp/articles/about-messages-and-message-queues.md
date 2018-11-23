# About Messages and Message Queues

[https://msdn.microsoft.com/en-us/library/windows/desktop/ms644927\(v=vs.85\).aspx\#](https://msdn.microsoft.com/en-us/library/windows/desktop/ms644927%28v=vs.85%29.aspx#)

Here are some information for dotnet developers:

* `Application.Run` internally maintains the message/event loop
* `Control.BeginInvoke` is similar to `PostMessage`
* `Control.Invoke` , though internally implemented using `PostMessage`, will wait for the execution to complete like `SendMessage`
* `WinFormSynchronizationContext` or WPF `Dispatcher` should be used instead of `Control.BeginInvoke`/`Invoke`, because the Control might be already disposed when you call its `BeginInvoke` in another thread, whereas the `SynchronizationContext` maintains its own control that has a longer life time scope.
* `Application.DoEvents`: [https://msdn.microsoft.com/en-us/library/system.windows.forms.application.doevents.aspx](https://msdn.microsoft.com/en-us/library/system.windows.forms.application.doevents.aspx) the example in this document explains quite well the scenario it can, but not necessary, be used.

All the above \(except the `Application.Run`\) are signs of bad design, I post them here just to help you understand the existing code.

## NodeJS Event Loop

[https://youtu.be/8aGhZQkoFbQ](https://youtu.be/8aGhZQkoFbQ)

