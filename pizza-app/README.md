## Deploy Pizza-APP
Simple Pizza App built on Nginx - The Task is part of Linux Academy Skills test

### Verify Yamls:
kubeval *yaml 

### Deploy App and Service
kubectl apply -f pizza-deployment.yaml
kubectl apply -f pizza-service.yaml

### Verify Resources
kubectl get all -n pizza

### Verify Service
curl <<k8s-node-ip>>:30080

### Cleanup
kubectl delete ns pizza               
