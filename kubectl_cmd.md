 1. 从容器中拷贝文件

```shell

kubectl cp -n namespace pod_name:app/test.txt ./test.txt

```

2. 查看pod详情

```plain

kubectl describe pods -n namespace

```

3. 删除节点

```shell

#先停止服务

systemctl stop docker

systemctl stop kubelet

kubectl delete node node_name

```

4. 删除pod

```shell

kubectl delete pod pod_name -n namespace

强制删除

kubectl delete pod pod_name -n namespace --grace-period=0 --force

```



5. 回滚

```

kubectl rollout history deployment/grafana -n kubesphere-monitoring-system

kubectl rollout history deployment/grafana --revision=83 -n kubesphere-monitoring-system

kubectl rollout undo deployment/grafana --to-revision=1 -n kubesphere-monitoring-system

```

