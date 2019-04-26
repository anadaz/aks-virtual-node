## disable shceduling for node
kubectl cordon aks-agentpool-12103826-1

## remove taint

kubectl taint nodes virtual-node-aci-linux virtual-kubelet.io/provider-


## pod auto scale

kubectl autoscale rs foo --min=2 --max=5 --cpu-percent=80


```az aks get-credentials -g rg-k8s-ae -n nadas-k8s-ae-virtual```
```az aks browse -g rg-k8s-ae -n nadas-k8s-ae-virtual```


## disable virtual node 
```az aks disable-addons -g rg-k8s-ae -n nadas-k8s-ae-virtual --addons virtual-node ```


## enable virtual node
```az aks enable-addons -g rg-k8s-ae -n nadas-k8s-ae-virtual --addons virtual-node --subnet-name virtual-node-aci ```


## Install virtual kubelet

- helm init
- helm ls 
#### - Delete all installed helm charts and remove charts from local repo
- helm ls --all --short | xargs -L1 helm delete --purge

```az aks install-connector --resource-group myAKSCluster --name myAKSCluster --connector-name virtual-kubelet --os-type Both```

## uninstall virtual kubelet

```az aks remove-connector --resource-group myAKSCluster --name myAKSCluster --connector-name virtual-kubelet```

## run container for testing

```kubectl run -it --rm virtual-node-test --image=debian```