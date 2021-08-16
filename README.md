# http-server-issue
Reproducing an issue with http-server and proxying with https. 

## Instructions

1. Run `yarn create-ssl` to create the SSL certificate and key. 

Run the various start commands and visit the page in the browser, the following table shows the responses:

|                         | localhost:8080 | localhost:8080/foobar |
|-------------------------|----------------|-----------------------|
| yarn start              | index.html ✅   | 404 ✅                 |
| yarn start:secure       | index.html ✅   | 404 ✅                 |
| yarn start:proxy        | index.html ✅   | index.html ✅          |
| yarn start:proxy:secure | index.html ✅   | 404 ❌                 |


The issue is that proxying appears not work when using an HTTPS certificate. 
