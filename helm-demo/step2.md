## Let's install a Chart

How about redis. Sure, let's install redis.

`helm search redis`{{execute}}

Inspect will give us a little more context around a chart:

`helm inspect stable/redis`{{execute}}

Install the chart:

`helm install stable/redis`{{execute}}

What's running?

`helm ls`{{execute}}

No, what's reallllly running?
`kubectl get all`{{execute}}
