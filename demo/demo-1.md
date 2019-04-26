## demo one
- Enable virtual node
- Check nodes in cluster
- Check pods wide to check node running them
- deploy d1-static-web
- watch pods created





az aks enable-addons -g rg-azbc -n aks-azbc --addons virtual-node --subnet-name virtual-node-aci



kubectl apply -f ./files/d1-static-web.yaml

kubectl port-forward deployment/d1-static-web 8081:80 

kubectl scale deploy/d1-static-web --replicas=10

kubectl delete -f ./files/d1-static-web.yaml
