# kubernetes-beginner
## kube config 
```
$ cd
$ mkdir .kube
$ vi .kube/config
$ export KUBECONFIG=.kube/config
```
## Setting the namespace
```
$ kubectl config set-context --current --namespace=<insert-namespace-name-here>
```