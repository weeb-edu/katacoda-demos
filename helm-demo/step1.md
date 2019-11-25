
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

Update repo:
`helm repo update`{{execute}}

Are both Client and Server installed? Same version?
`helm version`{{execute}}

Repos installed:
`helm repo list`{{execute}}

tree is nice, let's install tree
`apt install tree`{{execute}}
