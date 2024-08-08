# How to Verify the Results

I have used Minikube with Kubernetes version 1.30.0.

Follow these steps to verify the deployment results.

## Step 1: Install minikube

After installing it run:

```sh
minikube start
```

## Step 2: Ensure the Namespace Exists

Make sure you have a namespace called `project-plato`. If it doesn't exist, create it with the following command:

```sh
kubectl create ns project-plato
```

## Step 3: Apply all Files
use command

```sh
kubectl apply -f <name-of-the-file>.yaml
```

## Step 4: Verify Results

you can use different commands like:


```sh
kubectl get pods -n project-plato
```
to get pods

```sh
kubectl describe pod <name> -n project-plato
```

to describe pods

```sh
kubectl exec -it <db2-pod-name> -n project-plato -- sh
```
to enter a pod with interactive terminal and then check secrets with

```sh
echo $DB_USERNAME
```
or

```sh
echo $DB_PASSWORD
```
...