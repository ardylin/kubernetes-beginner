# pods
## Create pod nginx

```
# kubectl run nginx --image=nginx
```
## LAB
```
# kubectl run nginx --image=nginx
# kubectl get pod
# kubectl get pod -o wide
# kubectl describe pod nginx
# kubectl edit pod nginx
# kubectl delete pod nginx
```
# YAML
## Create pod myapp 
```
apiVersion: v1
kind: Pod
metadata:
  labels:
    app: myapp
    type: front-end
  name: myapp
spec:
  containers:
  - image: nginx
    name: nginx

# kubectl create -f myapp.yaml
# kubectl delete po myapp

```
## deployment
```
apiVersion: apps/v1
kind: Deployment
metadata:
  labels:
    app: myapp
    type: front-end
  name: myapp
spec:
  replicas: 1
  selector:
    matchLabels:
      app: myapp
      type: front-end
  strategy: {}
  template:
    metadata:
      labels:
        app: myapp
        type: front-end
    spec:
      containers:
      - image: nginx
        name: nginx

# kubectl create -f deployment.yaml
# kubectl delete deployment myapp
```
## Create yaml file by kubectl
```
# kubectl run myapp --image=nginx --labels="app=myapp,type=front-end" --dry-run=client -o yaml > pod-label.yaml
# Kubectl create deployment nginx --image=nginx --dry-run=client -o yaml > deployment-nginx.yaml

```
# Replicaset
```
apiVersion: apps/v1
kind: ReplicaSet
metadata:
  name: frontend
  labels:
    app: guestbook
    tier: frontend
spec:
  # modify replicas according to your case
  replicas: 3
  selector:
    matchLabels:
      tier: frontend
  template:
    metadata:
      labels:
        tier: frontend
    spec:
      containers:
      - name: php-redis
        image: gcr.io/google_samples/gb-frontend:v3

# kubectl apply -f replicas.yaml
# kubectl delete replicas frontend
```
