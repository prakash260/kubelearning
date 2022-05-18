### Creating Replication Controller
- kubectl create -f rc-definition.yml
- kubectl get replicationcontroller
- kubectl get pods
- kubectl delete rc myapp-rc

### Creating Replicaset (Remember apiversion is apps/v1)
- kubectl create -f rs-definition.yml
- kubectl get replicasets
- kubectl get pods
- kubectl describe replicaset myapp-rs
- kubectl delete rs myapp-rs

###  scaling the replicas 
- kubectl replace -f rs-definition.yml
- kubectl scale --replicas=6  -f rs-definition.yml
- kubectl scale --replicas=6  replicaset myapp-rs

**for in memory edit**
- kubectl edit replicaset myapp-rs

*selector is the difference between replicaset vs replicationcontroller so that replicaset handle the replicas of pods which are not created as part of it.*

### Deployments  (Primarily used to deploy in rolling fashion)
- kubectl create -f dep-def.yml --record
- kubectl apply -f dep-def.yml
- kubectl set image deployment myapp-deployment nginx-container=nginx:1.9.1
- kubectl rollout undo deployment/myapp-deployment
- kubectl rollout status deployment/myapp-deployment
- kubectl rollout history deployment/myapp-deployment
- kubectl delete deployment deployment/myapp-deployment

minikube service result-service --url


