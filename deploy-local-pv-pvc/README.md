## Deploy PV, PVC and Pod
### Verify Yamls:
kubeval *yaml 

### Deploy Persistent Volume
kubectl create -f pv-local.yaml
kubectl get pv

### Deploy Persistent Volume Claim
kubectl create -f pvc-local.yaml

### Verify the Persistent Storage Resources
kubectl get pv
kubectl get pvc

### Deploy a Pod to use the PVC
kubectl create -f busybox-persistent-storage.yaml

### Verify the POD status
kubectl get pods
NAME                                  READY   STATUS      RESTARTS   AGE
busybox-pvc                           1/1     Running     0          15s

### Verify the container storage mount
kubectl exec -it busybox-pvc -- /bin/sh
/ # ls -lsrt /mnt
total 0
     0 drwxrwxrwx    2 root     root             6 Aug  3 08:37 test-local