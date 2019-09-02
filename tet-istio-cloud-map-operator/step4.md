## Set up the Istio Cloud Map operator to your Kubernetes cluster:

1. Create an AWS IAM identity with read access to AWS Cloud Map for the operator to use.

2. Create a Kubernetes secret with the Access Key ID and Secret Access Key of the identity you just created in the namespace you want to deploy the Istio Cloud Map Operator:

apiVersion: v1
kind: Secret
metadata:
  name: aws-credz
  namespace: istio-system
type: Opaque
data:
  access-key-id: <base64-encoded-IAM-access-key-id>
  secret-access-key: <base64-encoded-IAM-secret-access-key>
  
3. Edit the aws-config config map in kubernetes/deployment.yaml to choose the AWS Cloud Map region to sync with.

4. Deploy the Istio Cloud Map Operator:

`kubectl apply -f kubernetes/rbac.yaml -f kubernetes/deployment.yaml`{{execute}}

Verify that your ServiceEntries have been populated with the information in Cloud Map; there should be one ServiceEntry for every service in Cloud Map:

`kubectl get serviceentries`{{execute}}

NAME                                       CREATED AT
cloudmap-dev.null.demo.tetrate.io          17h
cloudmap-test-server.cloudmap.tetrate.io   17h

`kubectl get serviceentries cloudmap-test-server.cloudmap.tetrate.io -o yaml`{{execute}}

apiVersion: networking.istio.io/v1alpha3
kind: ServiceEntry
metadata:
  name: cloudmap-test-server.cloudmap.tetrate.io
  namespace: default
spec:
  addresses:
  - 172.31.37.168
  endpoints:
  - address: 172.31.37.168
    ports:
      http: 80
      https: 443
  hosts:
  - test-server.cloudmap.tetrate.io
  ports:
  - name: http
    number: 80
    protocol: HTTP
  - name: https
    number: 443
    protocol: HTTPS
  resolution: STATIC


