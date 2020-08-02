## Deploy Secrets
### Verify Yamls:
kubeval *yaml 

### Deploy secrets
kubectl create -f my-secret.yaml

### Verify
kubectl get secrets

### Delete Secrets
kubectl delete -f my-secret.yaml