## demo two
Scale the webapp and watch ACI containers

- check tolerations
- Deploy service Load Balancer
- Browse service
- Scale out more pods
- Check running pods
- Check running containers


kubectl apply -f

kubectl get pods --watch

az container list

kubectl scale deploy/d2-lb-web-app --replicas=10
