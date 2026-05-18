# cluster-capi-aws

## 0. Introduction

- [cluster-capi-kind](https://github.com/nephio-project/catalog/tree/main/infra/capi/cluster-capi-kind) 를 참고하여 생성
- cluster-capi-aws-templates 을 이용하여 aws cluster 를 생성

## 1. Prerequisites

### 1.1 Install cluster-capi-infrastructure-aws

```sh
kpt pkg get cluster-capi-infrastructure-aws;
kpt live init cluster-capi-infrastructure-aws;
kpt live apply cluster-capi-infrastructure-aws --reconcile-timeout=2m --output=table;
```

### 1.2 Install cluster-capi-aws-templates

```sh
kpt pkg get cluster-capi-aws-templates;
kpt live init cluster-capi-aws-templates;
kpt live apply cluster-capi-aws-templates --reconcile-timeout=2m --output=table;
```

## 2. Install AWS Cluster

### 2.1 Initialize kpt pkg

- kpt 패키지 초기화

```sh
kpt pkg init cluster-capi-aws
```

### 2.2 Install AWS Cluster

```sh
# Apply the Package
kpt live init cluster-capi-aws --force;
kpt live apply cluster-capi-aws --reconcile-timeout=2m --output=table
```

## 3. Cleanup

### 3.1 Uninstall AWS Cluster

```sh
kpt live destroy cluster-capi-aws;
```
