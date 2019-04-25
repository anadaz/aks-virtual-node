kubectl cordon aks-agentpool-12103826-1

## remove taint

kubectl taint nodes virtual-node-aci-linux virtual-kubelet.io/provider-


## pod auto scale

kubectl autoscale rs foo --min=2 --max=5 --cpu-percent=80
