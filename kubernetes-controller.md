# Kubernetes Controller Manager

## Cloud Controller Manager（CCM）

CCM 的功能大部份來自 KCM

## ![](https://k8smeetup.github.io/images/docs/post-ccm-arch.png)

## Replication Controller

Replication Controller 簡稱 RC，RC 可以保證在任意時間運行 Pod 的副本數量和 Pod 的健康狀態，能夠保證 Pod 總是可用的。

* Replica Set：下一代的 Replication Controller
* Deployment：可以更加方便的管理 Pod 和 Replica Set

## Node Controller

管理維護 Node，定期檢查 Node 的健康狀態，並且標示出故障的 Node。

## Namespace Controller

管理維護 Namespace，定期清理無效的 Namespace，包含 Namespace 下的 API 物件，像 Pod、Service、Secret 等。

## Service Controller

同時監控 Service 和 Node 的變化，針對任何新建或更新的服務，ServiceController 用 Load Balancer Provider 來實現 Load Balancer 的配置。

## Endpoints Controller

負責生成和維護所有 Endpoints 對象的控制器，並監聽 Service 和對應的 Pod 副本變化。

1. 如果監測到 Service 被刪除，則刪除和 Service 同名的 Endpoints 對象
2. 如果監測到 Service 被創建或修改，則根據 Service 訊息獲得相關的 Pod 列表，然後創建或更新 Service 對應的 Endpoints 對象
3. 如果監測到 Pod 的事件，則更新 Service 對應的 Endpoints 對象

## Service Account Controller

管理維護 Service Account，為每個 Namespace 建立預設的 Service Account 和 Service Account Secret。

