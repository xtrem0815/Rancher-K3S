# Install Kubernetes Rancher k3s

## Links
https://github.com/jamct/kubernetes-einstieg/tree/main

./vagrant_up.sh master-k3s-01 ubuntu
./vagrant_up.sh worker-k3s-01 ubuntu
./vagrant_up.sh worker-k3s-02 ubuntu


ssh vagrant@192.168.1.156
ssh vagrant@192.168.1.109
ssh vagrant@192.168.1.180


sudo hostnamectl hostname master-k3s-01.local.ch
sudo hostnamectl hostname worker-k3s-01.local.ch
sudo hostnamectl hostname worker-k3s-02.local.ch

sudo shutdown -h now

## On master-k3s-01:
```bash
mkdir -p /etc/rancher/k3s/
vi /etc/rancher/k3s/config.yaml
disable: traefik

curl -sfL https://get.k3s.io | sh -s - server --cluster-init
```

### Token on master node
```
cat /var/lib/rancher/k3s/server/token
K105efc99483ab6d06e4c4ea6a725c6b1a4511e47e6a128b542dfa5c7a7f8969d5b::server:b20a4cb1cdd0f6d45abe4f4eea5b164c
```

## On worker nodes (join cluster)
```bash
curl -sfL https://get.k3s.io | K3S_TOKEN=K105efc99483ab6d06e4c4ea6a725c6b1a4511e47e6a128b542dfa5c7a7f8969d5b::server:b20a4cb1cdd0f6d45abe4f4eea5b164c sh -s - server --server https://192.168.1.156:6443
```

```bash
cat /etc/rancher/k3s/k3s.yaml
vim /home/lars/.kube/config
  Change default to k3s-dev
kubectl config use-context k3s-dev
```

```bash
kubectl get nodes
kubectl get nodes -o wide
```


curl -fsSL https://downloads.k8slens.dev/keys/gpg | gpg --dearmor | sudo tee /usr/share/keyrings/lens-archive-keyring.gpg > /dev/null
echo "deb [arch=amd64 signed-by=/usr/share/keyrings/lens-archive-keyring.gpg] https://downloads.k8slens.dev/apt/debian stable main" | sudo tee /etc/apt/sources.list.d/lens.list > /dev/null
sudo apt update
sudo apt install lens


https://kubernetes.k3s.internal.synology.me:6443

https://kubernetes.k3s.internal.synology.me:6443   192.168.1.156



##
```bash

```

##
```bash

```

##
```bash

```

##
```bash

```

##
```bash

```

##
```bash

```

##
```bash

```

##
```bash

```

##
```bash

```

##
```bash

```

##
```bash

```

##
```bash

```

##
```bash

```

##
```bash

```

##
```bash

```

##
```bash

```

##
```bash

```

##
```bash

```




