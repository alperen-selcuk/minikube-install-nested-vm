# minikube-install

## docker install

öncelikle driver için docker kuracağız.

```
curl https://raw.githubusercontent.com/alperen-selcuk/docker-install/main/install-docker.sh | bash -
```

## minikube install

linux için binary yükleyeceğim. siz link üzerinden istediğiniz platformu seçebilirsiniz. https://minikube.sigs.k8s.io/docs/start/

```
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
sudo install minikube-linux-amd64 /usr/local/bin/minikube
```

## minikube start

driver docker seçip minikube start diyoruz.

```
minikube start --container-runtime=containerd --nodes=3 --cni=calico --driver=docker --force
```

## kubectl

minikube cluster kurulduktan sonra kubectl yüklerek deneyimleyebiliriz.

```
curl https://raw.githubusercontent.com/alperen-selcuk/kubectl-install/main/install-kubectl-helm.sh | bash -
```


