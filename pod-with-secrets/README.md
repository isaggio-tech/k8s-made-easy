## Deploy Pods with Secrets
### Verify Yamls:
kubeval *yaml 

### Dependency
Pods in this module depends on deploy-secrets module, located in the root directory

### About
Both yamls are independent and creates each pod, opod-secret-ref exports secrets as ENV as Key references
whilst pod-secret-volume mounts secrets into mouth path /secrets directory inside the pod

### Install Pod
kubectl create -f <<name>>.yaml

### Verify ENV once you deploy pod-secret-ref.yaml,
kubectl exec -i -t hw-secret-test -- /bin/sh

OR

kubectl exec -i -t hw-secret-test -- env (will list all env vars from pod)

### Verify /secrets directory once you deploy pod-secret-volume.yaml,
kubectl exec -i -t hw-secret-test -- /bin/sh (list the files inside the pod /secrets)
