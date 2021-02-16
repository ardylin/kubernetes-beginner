# Replicaset
## Create replica set name nginx with image nginx 

```
apiVersion: apps/v1
kind: ReplicaSet
metadata:
  name: nginx-replicas
  labels:
    app: nginx
    tier: frontend
spec:
  replicas: 1
  selector:
    matchLabels:
      app: nginx
      tier: frontend
  template:
    metadata:
      labels:
        app: nginx
        tier: frontend
    spec:
      containers:
      - name: nginx
        image: nginx

# kubectl apply -f nginx-replicas.yaml

```
## Scale pod nginx =3 with kubectl scale command
```
# kubectl scale replicaset.apps/nginx-replicaset --replicas=3
```
## Scale pod nginx =6 with kubectl edit (replicas=3)
```
# kubectl edit replicaset.apps/nginx-replicaset
```
## Clean up
```
# kubectl delete replicaset.apps/nginx-replicaset
```
# Deployment
## Create Deployment set name nginx with image nginx