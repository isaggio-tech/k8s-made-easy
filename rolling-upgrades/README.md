## ROLLING UPGRADE HELP
### Verify Yamls:
kubeval *yaml 

### Create Deployment & Service
kubectl create -f rolling-upgrade-deploy.yaml
kubectl create -f rolling-upgrade-service.yaml

### Upgrade
kubectl set image deployment/echo-server-deploy echo-server=ealen/echo-server:0.2.0 --record
kubectl get deployments
kubectl get pods

### RollBack:
#### History:
kubectl rollout history deployment echo-server-deploy
kubectl rollout undo deployment echo-server-deploy --to-revision=1 


### Test URL:
vist:  master-url:30096/hello-world

### echo-server Document
https://ealenn.github.io/Echo-Server/pages/docker.html

