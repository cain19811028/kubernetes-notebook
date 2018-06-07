# Kubernetes

官方文件：[https://kubernetes.io/docs](https://kubernetes.io/docs)

## 架構圖：![](/assets/01d38243-e5ab-4c0f-9e64-dd980f33fd8a.png)Pod

* Kubernetes 的基本調度單元
* 一般包含一個或多個容器
* 每個 Pod 都被分配一個唯一的 IP 位址

## Replication Controller

* 用來控制和管理 Pod 備份

## Service

* 定義 Pod 的邏輯集合和存取這個 Pod 集合的策略

## Label

* 用於區分 Pod、Service、Replication Controller 的鍵值對（key/value pairs）

## Node

* Kubernetes 的操作單元
* 也稱為 Worker 或 Minion
* 用來執行和管理容器
* Pod 最後執行在 Node 上



