# node-red-job-cluster
Job cluster running on Node-RED built on k8s

## cluster manifest
https://github.com/nojaja/kubernetes-nodered.git


## environment
``` worker node
          - name: SERVICENAME
            value: "nodered-service"
          - name: CLUSTER_GROUP
            value: "test"
          - name: CLUSTER_ROLE
            value: "worker"
          - name: TOPICS
            value: "topic1,topic2,git"
          - name: FLOW_MAX
            value: "1"
```

``` master node
          - name: SERVICENAME
            value: "nodered-service"
          - name: CLUSTER_GROUP
            value: "test"
          - name: CLUSTER_ROLE
            value: "jobctl"
```
### endpoint
```
http://${JOBCTL_SERVICE_IP}:${JOBCTL_SERVICE_HOST_HTTP_PORT}/${actionType}/${jobsession}/${topic}

```

```
exec
/${actionType}/:jobsession/:topic
```
            