---
layout: post
title: "Kubernetes command"
date: 2020-01-30
excerpt: "Kubernetes command 관련"
tags: [kubernetes, kubectl, command]
comments: true
---

## kubectl command 명령어

```
Kubectl get svc

Kubectl get nodes

Kubectl get pods --all-namespaces

Kubectl exec [pod-name] –ti bash

Export KUBECONFIG=/etc/kubernetes/admin.conf

Kubectl port-forward svc/[pod-name] 3306:3306 –address 0.0.0.0

Kubectl get services

Kubectl create sa foo

Kubectl describe sa foo

Kubectl describe pod [pod-name]

kubectl get pod --all-namespaces --show-labels
```
