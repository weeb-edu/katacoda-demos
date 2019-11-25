## Let's download an example chart and examine it

Download a test go api by 
`git clone https://github.com/daemonza/testapi.git; cd testapi`{{execute}}

Credit to Daemonza for the excellent test API in Go:
https://daemonza.github.io/2017/02/20/using-helm-to-deploy-to-kubernetes/

Here are the contents of the chart:
`tree ./testapi-chart/`{{execute}}

Take a look at the contents:
`cat ./testapi-chart/Chart.yaml`{{execute}}
`cat ./testapi-chart/values.yaml`{{execute}}

Helm lint checking is good practice:
`helm lint .`{{execute}}

Looks good!


