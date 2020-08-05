## Deploy DATA Consumer APP
Simple DATA Consumer APP built - The Task is part of Linux Academy Skills test

There is a fluentd configuration located on the server at /usr/ckad/fluent.conf. Load the data from this file into a ConfigMap called fluentd-config.
Create the pod descriptor in /usr/ckad/adapter-pod.yml. An empty file has already been created for us.
The pod should be named counter.
Add a container to the pod that runs the busybox image, and name it count.
Run the count container with the following arguments:

- /bin/sh
- -c
- >
  i=0;
  while true;
  do
    echo "$i: $(date)" >> /var/log/1.log;
    echo "$(date) INFO $i" >> /var/log/2.log;
    i=$((i+1));
    sleep 1;
  done
Add another container called adapter to the pod, and make it run the k8s.gcr.io/fluentd-gcp:1.30 image.

Add an environment variable to the adapter container called FLUENTD_ARGS with the value -c /fluentd/etc/fluent.conf.
Mount the fluentd-config ConfigMap to the adapter container so that the config data is located inside the container in a file at /fluentd/etc/fluent.conf.
Create a volume for the pod in such a way that the storage will be deleted if the pod is removed from a node. Mount this volume to both containers at /var/log. The count container will output log data to this volume, and the adapter container will read the data from the same volume.
Create a hostPath volume where the adapter container will output the formatted log data. Store the data at the /usr/ckad/log_output path. Mount the volume to the adapter container at /var/logout.


USAGE:

kubectl create -f config-map.yaml
kubectl create -f pv.yaml
kubectl create -f pvc.yaml
kubectl create -f pod.yaml


kubectl delete -f .
configmap "fluentd-config" deleted
pod "counter" deleted
persistentvolume "log-data-pv" deleted
persistentvolumeclaim "log-data-pvc" deleted