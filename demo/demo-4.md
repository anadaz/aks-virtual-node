## demo 4 - CAUTION: This may break your AKS cluster.
Run one pod on real node then scale into ACI with replica pods

- edit replica to 1
- deploy
- stop scheduling for node
- remove taint, check removed
- edit replica to 3
- deploy
- pods should be created into ACI



kubectl cordon aks-agentpool-93729238-0

kubectl taint nodes virtual-node-aci-linux virtual-kubelet.io/provider-

az aks browse -g rg-azbc -n aks-azbc



kubectl uncordon aks-agentpool-93729238-0

kubectl taint nodes virtual-node-aci-linux virtual-kubelet.io/provider=aci:NoSchedule
