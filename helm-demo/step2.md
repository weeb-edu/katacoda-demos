## Let's install a Chart

How about redis. Sure, let's install nginx.

`helm search nginx`{{execute}}

Inspect will give us a little more context around a chart:

`helm inspect stable/nginx`{{execute}}

Install the chart:

`helm install stable/nginx`{{execute}}

What's running?

`helm ls`{{execute}}

No, what's reallllly running?
`kubectl get all`{{execute}}
