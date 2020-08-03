## Explore Cronjob and Job Resources

### Verify Yamls:
kubeval *yaml 

### Deploy Pods
kubectl apply -f cron-job-pod.yaml
kubectl apply -f job-pod.yaml

### Verify
kubectl get pods
kubectl describe pod <<pod-name>>
kubectl logs <<pod-name>> -f
