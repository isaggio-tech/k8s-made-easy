## Deploy Secrets
### Verify Yamls:
kubeval *yaml 

### Convert secret to base64,
echo -n password123 | base64

Copy output to my-secret.yaml

### Deploy secrets
kubectl create -f my-secret.yaml

### Verify
kubectl get secrets

### Delete Secrets
kubectl delete -f my-secret.yaml