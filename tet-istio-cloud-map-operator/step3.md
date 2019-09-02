## Install Istio 

Install all the Istio Custom Resource Definitions (CRDs) using kubectl apply

Check for the latest version here (and replace version if desired)

`curl -L https://git.io/getLatestIstio | ISTIO_VERSION=1.2.5 sh -`{{execute}}

For this example, let's cd into the installed directory 

`cd istio-1.2.5`{{execute}}

The installation directory contains:
Installation YAML files for Kubernetes in install/kubernetes
Sample applications in samples/
The istioctl client binary in the bin/ directory. istioctl is used when manually injecting Envoy as a sidecar proxy.

Add istioctl client to your PATH:

`export PATH=$PWD/bin:$PATH`{{execute}}

Sure, why not, make sure autocompletion works on istioctl

`source ~/istioctl.bash`{{execute}}


Install all the Istio Custom Resource Definitions (CRDs) using kubectl apply, and wait a few seconds for the CRDs to be committed in the Kubernetes API-server:

`for i in install/kubernetes/helm/istio-init/files/crd*yaml; do kubectl apply -f $i; done`{{execute}}
