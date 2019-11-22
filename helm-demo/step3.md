## Dynamically set and scale


Use Helm to set for nginx example (not redis)

`helm upgrade --set scale=9,tag="1.12" <name> <chartname>`{{execute}}


See changes happening

`kubectl get pods`{{execute}}

Check release inside of pod

`kubectl exec nginx-podname -- nginx -v`{{execute}}

Helm rollback

`helm rollback <livid-llama> 1`{{execute}}

Where the 1 is the revision number

Check release inside of pod again

`kubectl exec nginx-podname -- nginx -v`{{execute}}

Replaces the following commands:

kubectl apply -f service.yaml
kubectl apply -f deployment.yaml 
kubectl apply -f ingress.yaml
kubectl set image deployment/nginx nginx=1.13
kubectl scale deployment nginx --replicas=9
