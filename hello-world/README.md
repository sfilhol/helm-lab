# Hello World

This is a Helm chart for a Hello World application.

## Prerequisites

- Kubernetes 1.16+
- Helm 3.0+
- Nginx ingress controller

## Installation

To install the chart with the release name `my-release`:

```bash
helm install my-release hello-world
To uninstall the chart:
helm uninstall my-release
```

## Configuration

The following table lists the configurable parameters of the Hello World chart and their default values.

| Parameter                | Description         | Default                                 |
| ------------------------ | ------------------- | --------------------------------------- |
| `replicaCount`           | Number of replicas  | `1`                                     |
| `image.repository`       | Image repository    | `nginx`                                 |
| `image.pullPolicy`       | Image pull policy   | `IfNotPresent`                          |
| `service.type`           | Service type        | `ClusterIP`                             |
| `service.port`           | Service port        | `80`                                    |
| `ingress.enabled`        | Enable ingress      | `true`                                  |
| `ingress.annotations`    | Ingress annotations | `{}`                                    |
| `ingress.hosts[0].host`  | Ingress host name   | `hello-world.example.com`               |
| `ingress.hosts[0].paths` | Ingress paths       | `[{"path": "/", "pathType": "Prefix"}]` |

To override some of these values, you can provide a custom values file:
helm install my-release hello-world -f custom-values.yaml
