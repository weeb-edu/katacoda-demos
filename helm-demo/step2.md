## Let's install a Chart

`kubectl cluster-info`{{execute}}

Thanks, Bitnami! Download demo charts from their docs:

`git clone https://github.com/bitnami/charts.git`{{execute}}
`cd charts/bitnami/nginx`{{execute}}

Download all needed dependencies:

`helm dep list`{{execute}}
`helm dep update`{{execute}}
`helm dep build`{{execute}}

lint check:

`helm lint .`{{execute}}


