# kluster
GitOps for a development cluster


## Start cluster

```shell
kind create cluster --name cluster --config ./kind/config.yaml
```

## Get credentials
```shell
kind export kubeconfig --name cluster
```

## Delete cluster

```shell
kind delete cluster --name cluster
```

## Bootstap

```shell
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
helm repo update
helm dependency update ./chart/charts/monitoring/

```

## Deploy chart

```shell
helm upgrade --install kcluster chart/ 
```

## Remove chart

```shell
helm uninstall kcluster
```