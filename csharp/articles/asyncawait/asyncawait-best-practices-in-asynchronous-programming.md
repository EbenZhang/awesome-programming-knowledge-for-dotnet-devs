# Async/Await - Best Practices in Asynchronous Programming

* Avoid async void except the top level event handlers
* Async all the way even the main function \(with C\# 7.1\)
* Use `ConfigureAwait(false)` in library and let the consumer choose the context

For more details, see Stephen Cleary's [blog post](https://msdn.microsoft.com/en-us/magazine/jj991977.aspx) or Mads Torgerse's [video](https://www.youtube.com/watch?v=H4EmfpsYcfs)

