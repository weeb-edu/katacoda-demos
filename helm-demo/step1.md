
## First, install Helm

First, we install the latest version of Helm (2.x)

`curl https://raw.githubusercontent.com/helm/helm/master/scripts/get > get_helm.sh`{{execute}}
`chmod 700 get_helm.sh`{{execute}}
`./get_helm.sh`{{execute}}

We see that Tiller is not yet installed
`helm init`{{execute}}

Helm has a working set of public repositories. More on this later, but for now the repo cache can be updated.
`helm repo update`{{execute}}

At this point Helm should be healthy.
`helm version`{{execute}}

The current location of Helm is in your homedir
`ls $(helm home)`{{execute}}

Repos installed:
`helm repo list`{{execute}}

Great! Next, Let's install some charts.
