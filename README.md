# minikube-install

>>> CLOUD SHELL 

google cloud üzerinde minikube kurabilmek için belirli bir cpu kullanmamız gerek. sanallaştırma desteklemesi gerekiyor.  Intel Haswell cpu çalıştırılan region bulmamız gerekiyor. bilgiye buradan ulaşabilirsiniz. https://cloud.google.com/compute/docs/cpu-platforms

ben us-east1-a kullanacağım.

```
gcloud compute instances create nested-instance   --enable-nested-virtualization   --zone=us-east1-b   --min-cpu-platform="Intel Haswell" --machine-type=n1-standard-4
```



>>> INSTANCE 

## docker install

öncelikle docker kuracağız.

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


