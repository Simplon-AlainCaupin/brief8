# brief8

Création cluster AKS :
```
az aks create -n akslain -g brief8lain --network-plugin azure --enable-managed-identity --node-count 2 -a ingress-appgw --appgw-name appgwlain --appgw-subnet-cidr "10.225.0.0/16" --generate-ssh-keys
```

Récuperation credentials AKS :

```
az aks get-credentials --resource-group brief8lain --name akslain
```

Création des 2 namespaces QAL et PROD via leurs manifestes :

```
alain@kubernetes-master:~/brief8/brief8$ ll
total 24
drwxrwxr-x 3 alain alain 4096 févr. 27 11:26 ./
drwxrwxr-x 3 alain alain 4096 févr. 27 11:14 ../
drwxrwxr-x 8 alain alain 4096 févr. 27 11:38 .git/
-rw-rw-r-- 1 alain alain   53 févr. 27 11:26 prod.yml
-rw-rw-r-- 1 alain alain   52 févr. 27 11:27 qal.yml
-rw-rw-r-- 1 alain alain  414 févr. 27 11:38 README.md

kubectl apply -f .
```

Ajout des "service connections" entre AKS et AzureDezvops, par namespace
Pour déployer sur un NS particulier :

```
kubectl apply -f . -n qal
```


az aks create -n akslain -g brief8lain --network-plugin azure --node-count 2 -a ingress-appgw --appgw-name appgwlain --appgw-subnet-cidr "10.225.0.0/16" --generate-ssh-keys

az aks get-credentials --resource-group brief8lain --name akslain –admin

Subscription Id : a1f74e2d-ec58-4f9a-a112-088e3469febb

az aks get-credentials --resource-group brief8lain --name akslain --file kubeconfig