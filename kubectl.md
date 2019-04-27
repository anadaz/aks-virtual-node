## disable shceduling for node
kubectl cordon aks-agentpool-12103826-1

## remove taint

kubectl taint nodes virtual-node-aci-linux virtual-kubelet.io/provider-


## pod auto scale

kubectl autoscale deploy foo --min=2 --max=5 --cpu-percent=80

## scale
kubectl scale deploy/d1-static-web --replicas=10


```az aks get-credentials -g rg-azbc -n aks-azbc```
```az aks browse -g rg-azbc -n aks-azbc```


## enable virtual node
```az aks enable-addons -g rg-azbc -n aks-azbc --addons virtual-node --subnet-name virtual-node-aci ```

## disable virtual node 
```az aks disable-addons -g rg-azbc -n aks-azbc --addons virtual-node ```


## Install virtual kubelet

- helm init
- helm ls 
#### - Delete all installed helm charts and remove charts from local repo
- helm ls --all --short | xargs -L1 helm delete --purge

```az aks install-connector --resource-group myAKSCluster --name myAKSCluster --connector-name virtual-kubelet --os-type Windows```

## uninstall virtual kubelet

```az aks remove-connector --resource-group myAKSCluster --name myAKSCluster --connector-name virtual-kubelet```

## run container for testing

```kubectl run -it --rm virtual-node-test --image=debian```