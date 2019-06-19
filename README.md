
# Introduction

This repo bootstraps an emqx deployment on a Kubernetes cluster using the Kustomize. kubectl 1.14.0+ already support kustomize. This is experimental. It should not be used in a production environment

# Prerequisites

+ Kubernetes 1.14 +

# Install

## Example

```bash
git clone https://github.com/wuxingzhong/emqx-kustomize.git
kubectl apply -k emqx-kustomize/overlays/example
# or
kubectl apply -k https://github.com/wuxingzhong/emqx-kustomize/overlays/example
```

## custom

```bash

# create your kustomization.yaml
# vim kustomization.yaml
bases:
- https://github.com/wuxingzhong/emqx-kustomize/base

# or

git clone https://github.com/wuxingzhong/emqx-kustomize.git
mkdir emqx-kustomize/overlays/test
cd emqx-kustomize/overlays/test
# vim kustomization.yaml
bases:
- ../../base

# install
kubectl apply -k .
```

# Generate yaml

```bash
kubectl kustomize https://github.com/wuxingzhong/emqx-kustomize/overlays/example
# or
kubectl kustomize <your dir>
```

# Uninstall

```bash
kubectl delete -k https://github.com/wuxingzhong/emqx-kustomize/overlays/example
# or
kubectl delete -k <your dir>
```