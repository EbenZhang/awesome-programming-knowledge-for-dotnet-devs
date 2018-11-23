# Windows Message Queue

## About Messages and Message Queues

[https://msdn.microsoft.com/en-us/library/windows/desktop/ms644927\(v=vs.85\).aspx](https://msdn.microsoft.com/en-us/library/windows/desktop/ms644927%28v=vs.85%29.aspx) Importantly these sections in the page:

* Message Loop
* Posting and Sending Messages

## DotNet Related

* `Application.Run` internally maintains the message/event loop
* `Control.BeginInvoke` is similar to `PostMessage`
* `Control.Invoke`, though internally implemented using `PostMessage`, will wait for the execution to complete like `SendMessage`
* `WinFormSynchronizationContext` or WPF `Dispatcher` should be used instead of `Control.BeginInvoke`/`Invoke`, because the Control might be already disposed when you call its `BeginInvoke` in another thread, whereas the `SynchronizationContext` maintains its own control that has a longer life time scope.
* `Application.DoEvents`: [https://msdn.microsoft.com/en-us/library/system.windows.forms.application.doevents.aspx](https://msdn.microsoft.com/en-us/library/system.windows.forms.application.doevents.aspx) the example in this document explains quite well the scenario it can, but not necessary, be used.

