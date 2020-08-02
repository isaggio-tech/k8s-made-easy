## Simple Hello World 
### Verify Yamls:
kubeval *yaml 

### Create Deployment & Service
kubectl create -f simple-hw-deploy.yaml
kubectl create -f simple-hw-service.yaml

### Verify
kubectl get deployments
kubectl get pods

### Test URL:
vist or curl:  master-url:30094
