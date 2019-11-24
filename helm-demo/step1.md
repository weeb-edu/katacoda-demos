
## First, install Helm

First, we install the latest version of Helm (2.x)

Helm can be downloaded from https://github.com/kubernetes/helm/releases

`curl https://raw.githubusercontent.com/helm/helm/master/scripts/get > get_helm.sh
chmod 700 get_helm.sh
./get_helm.sh`{{execute}}

We see that Tiller is not yet installed
`helm init`{{execute}}

You might need to wait a minute for all the install scripts to finish. 
Check to confirm tiller has installed successfully with no errors before proceeding.

Let's confirm the install was completed:
`kubectl get pods -n kube-system | grep tiller`{{execute}}

Helm has a working set of public repositories. More on this later, but for now the repo cache can be updated.
`helm repo update`{{execute}}

At this point Helm should be healthy.
`helm version`{{execute}}

The current location of Helm is in your homedir
`ls $(helm home)`{{execute}}

Repos installed:
`helm repo list`{{execute}}

Great! Next, Let's install some charts.

Oh yeah, tree would be nice in this demo so
`apt install tree`{{execute}}
