# Time Based Scaling of Kubernetes Objects

## Pre-Requisites
- Access to a Kubernetes cluster; OpenShift for example
- Permission to Create ClusterRole, ClusterRoleBinding
## Create the namespace

```
oc create -f 00-namespace.yaml
```

## Create ServiceAccount, ClusterRole, ClusterRoleBinding

```
oc create -f 01-rbac.yaml
```

## Create Workloads to test scaling

```
oc create -f 02-deployment.yaml
```

## Create Scale Up Job

> Identify the schedule in your time zone (e.g. EST), convert it to UTC before setting it on the CronJob.

```
oc create -f 03-scale-up-cronjob.yaml
```

## Create Scale Down Job

```
oc create -f 04-scale-down-cronjob.yaml
```
