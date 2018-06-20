# Minikube

Minikube is a tool that makes it easy to run Kubernetes locally. Minikube runs a single-node Kubernetes cluster inside a VM on your laptop for users looking to try out Kubernetes or develop with it day-to-day.

官網連結：[https://kubernetes.io/docs/setup/minikube/](https://kubernetes.io/docs/setup/minikube/)

GitHub：[https://github.com/kubernetes](https://github.com/kubernetes)

# Hello Minikube

安裝 [Homebrew](https://brew.sh/) 和 xhyve

```
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
brew install wget
brew install xhyve
```

使用 curl 下載和安裝 Minikube 最新發布的版本：

```
curl -Lo minikube https://storage.googleapis.com/minikube/releases/latest/minikube-darwin-amd64 && \
  chmod +x minikube && \
  sudo mv minikube /usr/local/bin/
```

使用 Homebrew 安裝 xhyve 驅動程序並設置權限：

```
brew install docker-machine-driver-xhyve
sudo chown root:wheel $\(brew --prefix\)/opt/docker-machine-driver-xhyve/bin/docker-machine-driver-xhyve
sudo chmod u+s $\(brew --prefix\)/opt/docker-machine-driver-xhyve/bin/docker-machine-driver-xhyve
```

使用 Homebrew 下載 kubectl 命令行工具：

```
brew install kubectl
```

啟動 Minikube：

```
minikube start --vm-driver=xhyve
```



