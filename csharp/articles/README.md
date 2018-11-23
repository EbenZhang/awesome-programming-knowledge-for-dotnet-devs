# Articles

* in DLL's app.config: will be ignored
* in unit test or smoketest DLL's app.config: will be used by the nunit test runner, and can be automatically generated
* in application's app.config: will be used by the application, and can be automatically generated
* in web.config: will be used, and you can't automatically generate it. When there's a conflict, you need to manually add the bindingRedirect.
* Why bindingRedirect is needed: [https://stackoverflow.com/a/43366172/997453](https://stackoverflow.com/a/43366172/997453)

