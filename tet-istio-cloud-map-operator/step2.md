## 

Retrieve static configuration for Envoy to use

`curl -L https://getenvoy.io/samples/basic-front-proxy.yaml > basic-front-proxy.yaml`{{execute}}

Investigate the static configuration file.

`cat basic-front-proxy.yaml`{{execute}}

The YAML contains comments explaining the behavior of the relevant sections.

Run Envoy using the static configuration.

`envoy --config-path ./basic-front-proxy.yaml`{{execute}}

Open a new shell and cURL Envoy with google.com as the host header.

<script src="//katacoda.com/embed.js"></script>
<div id="my-panel" data-katacoda-env="bash" data-katacoda-ui="panel"></div>

`curl -s -o /dev/null -vvv -H 'Host: google.com' localhost:15000/`{{execute}}

In this abbreviated response you can see that we made it to google.com as it is setting a cookie. If you want to see the full HTTP response body remove the -s -o /dev/null flags.

cURL Envoy with bing.com as the host header.

`curl -s -o /dev/null -vvv -H 'Host: bing.com' localhost:15000/`{{execute}}


In this abbreviated response you can see that we made it to bing.com as it is also setting a cookie. If you want to see the full HTTP response body remove the -s -o /dev/null flags.

Check the access logs in the shell running Envoy.

[2019-06-05T08:30:01.145Z] "GET / HTTP/1.1" 200 - 0 111162 374 135 "-" "curl/7.54.0" "c1aeafd2-dcd9-4070-80fd-f8f4f6bd1e85" "www.bing.com" "13.107.21.200:80"
[2019-06-05T08:30:07.799Z] "GET / HTTP/1.1" 200 - 0 12426 64 60 "-" "curl/7.54.0" "0c8ce45d-e99e-4ddc-9cc4-06d75d81e610" "www.google.com" "216.58.213.4:80"

The access logs confirm that we have made two successful requests: one to www.google.com and the other to www.bing.com. To find out more about the default format of the access logs and information on the other fields present, check out the Envoy documentation.
