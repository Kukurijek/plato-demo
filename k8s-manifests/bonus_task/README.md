# Bonus Task

## Step 1: Install helm

If you are using macOS and brew run:

```sh
brew install helm
```

## Step 2: Install Postgres

```sh
helm repo add bitnami https://charts.bitnami.com/bitnami
helm repo update
helm install my-postgresql bitnami/postgresql --namespace project-plato --create-namespace -f postgres-values.yaml
```

## Step 3: Deploy 'kube-prometheus-stack'

```sh
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
helm repo update
```

```sh
helm install my-observability prometheus-community/kube-prometheus-stack --version 61.7.0 --namespace project-plato --create-namespace
```

## Step 3: Portforwarding
```sh
kubectl port-forward -n project-plato svc/kube-prometheus-stack-prometheus 9090:9090
```

## Step 4: Open ServiceMonitor
```sh
http://localhost:9090/targets
```
