# Fiddler
Fiddler can capture web requests, manipulate and replay those requests.

## To capture HTTPS requests

See http://docs.telerik.com/fiddler/Configure-Fiddler/Tasks/DecryptHTTPS for fiddler's official document.

Open fiddler → Select the Tools menu → Select the Options menu → Switch to the HTTPS tab page → Tick the Capture HTTPS CONNECTS and Decrypt HTTPS Traffic

Answer Yes for all popups.

## To capture requests sent to localhost

Fiddler won't be able to capture request if it's sent to localhost. The workaround is to send the request to the IP address instead of localhost.


