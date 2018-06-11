# Kubernetes Pod Lifecycle

官網說明：[https://kubernetes.io/cn/docs/concepts/workloads/pods/pod-lifecycle/](https://kubernetes.io/cn/docs/concepts/workloads/pods/pod-lifecycle/)

## ![](https://cdn-images-1.medium.com/max/1500/1*WDJmiyarVfcsDp6X1-lLFQ.png)

## Kubelet

負責管理容器，會從 API Server 接收 Pod 建立的請求，啟動和停止容器，監控容器執行狀態並且匯報給 API Server

