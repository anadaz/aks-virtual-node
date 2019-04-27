## demo three
- deploy windows container
- check pods
- pod will be pending
- install VK for windows
- deploy windows container, it will take few minutes check k8s dashboard
- check pods





kubectl apply -f ./files/d3-win-container.yaml

watch -n 5 kubectl get nodes

az aks install-connector -g rg-azbc -n aks-azbc --connector-name virtual-kubelet --os-type Windows



az aks browse -g rg-azbc -n aks-azbc

kubectl delete -f ./files/d3-win-container.yaml

az aks remove-connector -g rg-azbc -n aks-azbc --connector-name virtual-kubelet --os-type Windows