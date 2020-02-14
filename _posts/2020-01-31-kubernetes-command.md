---
layout: post
title: "Kubernetes command"
date: 2020-01-30
excerpt: "Kubernetes command 관련"
tags: [kubernetes, kubectl, command]
comments: true
---

## kubectl command 명령어

### 기본 출력을 위한 Get 커맨드
```
kubectl get services                          # 네임스페이스 내 모든 서비스의 목록 조회
kubectl get pods --all-namespaces             # 모든 네임스페이스 내 모든 파드의 목록 조회
kubectl get pods -o wide                      # 네임스페이스 내 모든 파드의 상세 목록 조회
kubectl get deployment my-dep                 # 특정 디플로이먼트의 목록 조회
kubectl get pods                              # 네임스페이스 내 모든 파드의 목록 조회
kubectl get pod [pod-name] -o yaml            # 파드의 YAML 조회
kubectl get pod [pod-name] -o yaml --export   # 클러스터 명세 없이 파드의 YAML 조회
```

### 서비스 확인
```
Kubectl get svc
Kubectl get services
```

### 노드 확인
```
Kubectl get nodes
```

### pod 실행 명령어
```
Kubectl exec [pod-name] –ti bash
```

### 포트포워딩 설정 (모든 서버에)
```
Kubectl port-forward svc/[pod-name] 3306:3306 –address 0.0.0.0
```

### 포트포워딩 설정 (로컬 호스트)
```
Kubectl port-forward svc/[pod-name] 3306:3306
```

### 계정 만들기
```
Kubectl create sa foo
```

### 계정 상세 출력
```
Kubectl describe sa foo
```

### pod 상세 출력
```
Kubectl describe pod [pod-name]
```

### 모든 네임스페이스 내 모든 파드(또는 레이블을 지원하는 다른 쿠버네티스 오브젝트)의 레이블 조회
```
kubectl get pod --all-namespaces --show-labels
```
