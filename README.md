# kubernetes-beginner
## kube config 
```
$ mkdir -p $HOME/.kube
$ vi .kube/config
```
## Setting the namespace
```
$ kubectl config set-context --current --namespace=<insert-namespace-name-here>
```