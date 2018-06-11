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





