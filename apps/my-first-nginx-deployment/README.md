
```bash
kubectl  create namespace first-pod-dev
kubectl config set-context --current --namespace=default
kubectl -f my-first-nginx-deployment.yml apply
```
http://kubernetes.k3s.internal.synology.me:30000



Scale up/down
```bash
kubectl scale deployment/my-first-nginx-deployment --replicas=5
kubectl scale deployment/my-first-nginx-deployment --replicas=2
kubectl scale deployment/my-first-nginx-deployment --replicas=3
kubectl get pods -o wide
```