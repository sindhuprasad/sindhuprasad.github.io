---
layout: post
title: What happens when you type in an URL in the browser?
---

This post describes the sequence of events when before a URL is loaded in the web browser.

1. When you type in `www.google.com`, the brower asks the OS to find the IP address of the remote webserver which has the name `www.google.com`. If
the OS does not know it already, it asks DNS server.
2. Once the IP address is obtained from DNS server, a TCP/IP socket connection is established on port 80.
3. Once the connection is established, a HTTP GET request is sent to through the connection to the remote webserver.
4. The webserver will give back a http a HTTP response which typically includes a HTML page. Additional resources within the page like stylesheets, images, etc
are requested by browser in the background.





