# Install ArgoCD

```bash
kubectl create namespace argocd
helm repo add argo https://argoproj.github.io/argo-helm
helm install my-argo argo/argo-cd -n argocd
kubectl port-forward service/my-argo-argocd-server -n argocd 8080:443
```

```bash
WARNING: Kubernetes configuration file is group-readable. This is insecure. Location: /home/lars/.kube/config
WARNING: Kubernetes configuration file is world-readable. This is insecure. Location: /home/lars/.kube/config
NAME: my-argo
LAST DEPLOYED: Tue Dec 26 19:20:57 2023
NAMESPACE: argocd
STATUS: deployed
REVISION: 1
TEST SUITE: None
NOTES:
In order to access the server UI you have the following options:

1. kubectl port-forward service/my-argo-argocd-server -n argocd 8080:443

    and then open the browser on http://localhost:8080 and accept the certificate

2. enable ingress in the values file `server.ingress.enabled` and either
      - Add the annotation for ssl passthrough: https://argo-cd.readthedocs.io/en/stable/operator-manual/ingress/#option-1-ssl-passthrough
      - Set the `configs.params."server.insecure"` in the values file and terminate SSL at your ingress: https://argo-cd.readthedocs.io/en/stable/operator-manual/ingress/#option-2-multiple-ingress-objects-and-hosts


After reaching the UI the first time you can login with username: admin and the random password generated during the installation. You can find the password by running:

kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d

(You should delete the initial secret afterwards as suggested by the Getting Started Guide: https://argo-cd.readthedocs.io/en/stable/getting_started/#4-login-using-the-cli)
```

http://kubernetes.k3s.internal.synology.me:8080

UEsd2ukbyq7aht0M