## Liveness & Readiness Probes
### Verify Yamls:
kubeval *yaml 

### Create Deployment & Service
kubectl create -f probes-deploy.yaml
kubectl create -f probes-service.yaml

### Verify
kubectl get deployments
kubectl get pods

#### This will provide the details of probe failures - no info, if all is success
kubectl describe pod <<pod_name>> 

```
Note:

Liveness failures — Kubernetes restarts the failed container
Readiness failures — Kubernetes does nothing when a container fails. ContainersReady set to False
```

### Test URL:
vist or curl:  master-url:30095
