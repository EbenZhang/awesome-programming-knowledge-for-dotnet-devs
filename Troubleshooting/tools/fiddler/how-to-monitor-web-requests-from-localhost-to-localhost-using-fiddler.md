# How to monitor web requests from localhost to localhost using Fiddler

You need to change the request url to use machine name or non-local IP address instead of `localhost` or `127.0.0.1`
For example, instead of `http://localhost:8081/mytestpage.aspx` or `http://127.0.0.1:8081/mytestpage.aspx`, use `http://machinename:8081/mytestpage.aspx` or your IP address (e.g. http://10.2.40.xxx/xxxx)

See http://docs.telerik.com/fiddler/Configure-Fiddler/Tasks/MonitorLocalTraffic