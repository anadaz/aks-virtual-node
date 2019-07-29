## demo one
Enable virtual node and deploy a webapp into ACI

- Enable virtual node
- Check nodes in cluster
- Check pods wide to check node running them
- deploy d1-static-web
- watch pods created
- confirm ACI containers have been created, azure portal





watch -n 5 kubectl get nodes

az aks enable-addons -g rg-azbc -n aks-azbc --addons virtual-node --subnet-name virtual-node-aci

kubectl apply -f ./files/d1-static-web.yaml

az container list -o table


kubectl delete -f ./files/d1-static-web.yaml

## if enabled already
az aks disable-addons -g rg-azbc -n aks-azbc --addons virtual-node 
