# Minikube

---

Minikube is a tool that makes it easy to run Kubernetes locally. Minikube runs a single-node Kubernetes cluster inside a VM on your laptop for users looking to try out Kubernetes or develop with it day-to-day.

官網連結：[https://kubernetes.io/docs/setup/minikube/](https://kubernetes.io/docs/setup/minikube/)

GitHub：[https://github.com/kubernetes](https://github.com/kubernetes)

# Hello Minikube

---

## 建立 Minikube Cluster

安裝 [Homebrew](https://brew.sh/) 和 xhyve

```
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
brew install wget
brew install xhyve
```

使用 curl 下載和安裝 Minikube 最新發布的版本

```
curl -Lo minikube https://storage.googleapis.com/minikube/releases/latest/minikube-darwin-amd64 && \
  chmod +x minikube && \
  sudo mv minikube /usr/local/bin/
```

使用 Homebrew 安裝 xhyve 驅動程序並設置權限

```
brew install docker-machine-driver-xhyve
sudo chown root:wheel $\(brew --prefix\)/opt/docker-machine-driver-xhyve/bin/docker-machine-driver-xhyve
sudo chmod u+s $\(brew --prefix\)/opt/docker-machine-driver-xhyve/bin/docker-machine-driver-xhyve
```

使用 Homebrew 下載 kubectl 命令行工具

```
brew install kubectl
```

啟動 Minikube Cluster

```
minikube start --vm-driver=xhyve
```

啟用 Kubernetes Dashboard

```
minikube dashboard
```

## 建立 Docker container image

---

使用 Minikube Docker daemon

```
eval $(minikube docker-env)
```

建立 Docker image

```
docker build -t hello-node:v1 .
```

## 建立 Deployment

---

使用 kubectl 執行指令建立一個管理 Pod 的 Deployment

```
kubectl run hello-node --image=hello-node:v1 --port=8080
```

## 建立 Service

---

使用 kubectl expose 指令將 Pod 顯示在 Public Internet：

```
kubectl expose deployment hello-node --type=LoadBalancer
minikube service hello-node
```

## 清理

---

清理在 Cluster 中建立的資源：

```
kubectl delete service hello-node
kubectl delete deployment hello-node
```

停止 Minikube VM

```
minikube stop
eval $(minikube docker-env -u)
```

刪除 Minikube VM

```
minikube delete
```
