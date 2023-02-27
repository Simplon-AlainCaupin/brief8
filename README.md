# brief8

Création cluster AKS

az aks create -n akslain -g brief8lain --network-plugin azure --enable-managed-identity --node-count 2 -a ingress-appgw --appgw-name appgwlain --appgw-subnet-cidr "10.225.0.0/16" --generate-ssh-keys

az aks get-credentials --resource-group brief8lain --name akslain

  git config --global user.email simplon.alaincaupin@gmail.com
  git config --global user.name Simplon-AlainCaupin