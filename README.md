
# Introduction

This repo bootstraps an emqx deployment on a Kubernetes cluster using the Kustomize. kubectl 1.14.0+ already support kustomize. This is experimental. It should not be used in a production environment

# Prerequisites

+ Kubernetes 1.14 +

# Install

```bash
git clone https://github.com/wuxingzhong/emqx-kustomize.git
kubectl apply -k emqx-kustomize
# or
kubectl apply -k https://github.com/wuxingzhong/emqx-kustomize.git
```

# Generate yaml

```bash
kubectl kustomize emqx-kustomize
```

# Uninstall

```bash
kubectl delete -k emqx-kustomize
```
