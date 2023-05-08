---
title: 'kubernetes'
date: 2023-05-08 16:13:39
tags: []
published: true
hideInList: false
feature: 
isTop: false
---
# 常用命令
## 查看所有的pod

kubectl get pod -A

## 进入容器内部

kubectl exec -ti 容器名 -n 命名空间 sh

## 查看指定pod的日志

kubectl -n namespace logs podid

## 查看pod详细信息
kubectl describe  pod  dcu-device-plugin-daemonset-j5q9s -n kube-system

## kubectl
kubectl apply -f 
kubectl delete -f 

# 创建pod的例子
## 执行命令
```shell
apiVersion: v1
kind: Pod
metadata:
  name: command-demo
  labels:
    purpose: demonstrate-command
spec:
  containers:
  - name: command-demo-container
    image: debian
    command: ["printenv"]
    args: ["HOSTNAME", "KUBERNETES_PORT"]
  restartPolicy: OnFailure
```
## 让容器长久运行
容器退出其实是它认为完成了。所以你需要为容器提供永不完成的任务
```shell
    # Just spin &amp; wait forever
    command: [ "/bin/bash", "-c", "--" ]
    args: [ "while true; do sleep 30; done;" ]
```

# 使用GPU
https://github.com/NVIDIA/k8s-device-plugin
