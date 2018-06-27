# Kubernetes

官方文件：[https://kubernetes.io/docs](https://kubernetes.io/docs)

## 架構圖：![](/assets/01d38243-e5ab-4c0f-9e64-dd980f33fd8a.png)

## Pod

* Kubernetes 的基本調度單元
* 一般包含一個或多個容器
* 每個 Pod 都被分配一個唯一的 IP 位址

## Replication Controller

* 用來控制和管理 Pod 備份

## Service

* 定義 Pod 的邏輯集合和存取這個 Pod 集合的策略

## Label

* 用於區分 Pod、Service、Replication Controller 的鍵值對（key/value pairs）

## Node（Minion）

* Kubernetes 的操作單元
* 用來管理和執行容器
* 負責監控所有容器執行的健康狀態
* Pod 最後執行在 Node 上

![](/assets/Kubernetes Architecture.webp)

## Etcd

* 高可用的 key/value 儲存系統
* 靈感來自於 Zookeeper 和 Doozer
* 做為系統設定的儲存中心
* 重要資料都是持久性存在

---

![](/assets/kubernetes node.jpg)

## Kubelet

負責管理容器，會從 API Server 接收 Pod 建立的請求，啟動和停止容器，監控容器執行狀態並且匯報給 API Server

## Kubernetes Proxy

負責為 Pod 建立代理服務，從 API Server 取得所有 Service，並根據 Service 資訊建立代理服務，實現 Service 到 Pod 的請求路由和轉發

