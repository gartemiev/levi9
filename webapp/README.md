# WebApp

## Introduction

This chart creates a webapp Deployment based on NGINX Docker container and HostPort.
NOTE: it doesn't use Service object since We use a HostPort here like was in requirements!!!

## Prerequisites

- Kubernetes 1.10+
- helm v3
- minikube minikube 1.12.3

## Installing the Chart

To install the chart with the release name `webapp`:

```bash
$ helm install webapp-release webapp
```

This command deploys a web application which displays Hellow World page.

To access 

## Uninstalling the Chart

To uninstall/delete the `my-release` deployment:

```bash
$ helm uninstall webapp
```

The command removes all the Kubernetes components associated with the chart and deletes the release.

## Configuration

The following table lists the configurable parameters of the webapp chart and their default values.

Parameter                       | Description                           | Default
------------------------------- | ------------------------------------- | ----------------------------------------------------------
`image.webapp.repository`       | Alpine Nginx image                    | `nginx`
`image.webapp.tag`              | `nginx` release tag.                  | `7.0`
`image.pullPolicy`              | Image pull policy                     | `IfNotPresent`
`hostPort`                      | hostPort                              | `8080`
`livenessProbe.path`            | HTTP path to check for webapp status  | `/`

Please refer to [values.yaml](values.yaml) for the full default variables list. 

Specify each parameter using the `--set key=value[,key=value]` argument to `helm install`. For example,

```bash
$ helm install webapp-release --set image.webapp.repository=nginx webapp
```

The above command deploys webapp `webapp-release` name and `nginx` image.

Alternatively, a YAML file that specifies the values for the parameters can be provided while installing the chart. For example:

```bash
$ helm install --name webapp-release -f values.yaml webapp
```