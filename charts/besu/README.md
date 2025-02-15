
# besu

![Version: 0.3.5](https://img.shields.io/badge/Version-0.3.5-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square)

An Ethereum execution layer client designed to be enterprise-friendly for both public and private, permissioned network use cases. Besu is written in Java and released under the Apache 2.0 Licence.

**Homepage:** <https://www.hyperledger.org/use/besu>

## Source Code

* <https://github.com/hyperledger/besu>

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| affinity | object | `{}` | Affinity configuration for pods |
| annotations | object | `{}` | Annotations for the StatefulSet |
| customCommand | list | `[]` | Command replacement for the besu container |
| extraArgs | list | `[]` | Extra args for the besu container |
| extraContainers | list | `[]` | Additional containers |
| extraEnv | list | `[]` | Additional env variables (evaluated as template) |
| extraPorts | list | `[]` | Additional ports. Useful when using extraContainers |
| extraVolumeMounts | list | `[]` | Additional volume mounts (evaluated as template) |
| extraVolumes | list | `[]` | Additional volumes (evaluated as template) |
| fullnameOverride | string | `""` | Overrides the chart's computed fullname |
| image.pullPolicy | string | `"IfNotPresent"` | besu container pull policy |
| image.repository | string | `"hyperledger/besu"` | besu container image repository |
| image.tag | string | `"latest"` | besu container image tag |
| imagePullSecrets | list | `[]` | Image pull secrets for Docker images |
| ingress.annotations | object | `{}` | Annotations for Ingress |
| ingress.enabled | bool | `false` | Ingress resource for the HTTP API |
| ingress.hosts[0].host | string | `"chart-example.local"` |  |
| ingress.hosts[0].paths | list | `[]` |  |
| ingress.tls | list | `[]` | Ingress TLS |
| initChownData.enabled | bool | `true` | Init container to set the correct permissions to access data directories |
| initChownData.image.pullPolicy | string | `"IfNotPresent"` | Container pull policy |
| initChownData.image.repository | string | `"busybox"` | Container repository |
| initChownData.image.tag | string | `"1.34.0"` | Container tag |
| initChownData.resources | object | `{}` | Resource requests and limits |
| initContainers | list | `[]` | Additional init containers |
| livenessProbe | object | See `values.yaml` | Liveness probe |
| nameOverride | string | `""` | Overrides the chart's name |
| nodeSelector | object | `{}` | Node selector for pods |
| p2pLoadBalancerPort.annotations | object | `{}` | P2P LoadBalancer service annotations (evaluated as template) |
| p2pLoadBalancerPort.enabled | bool | `false` | Expose P2P ports via LoadBalancer service |
| p2pLoadBalancerPort.externalTrafficPolicy | string | Local | Denotes if this Service desires to route external traffic to node-local or cluster-wide endpoints. There are two available options: Cluster and Local (default). Cluster obscures the client source IP and may cause a second hop to another node, but should have good overall load-spreading. Local preserves the client source IP and avoids a second hop for LoadBalancer and NodePort type Services, but risks potentially imbalanced traffic spreading. ref: https://kubernetes.io/docs/tasks/access-application-cluster/create-external-load-balancer/#preserving-the-client-source-ip |
| p2pLoadBalancerPort.initContainer.image.pullPolicy | string | `"IfNotPresent"` | Container pull policy |
| p2pLoadBalancerPort.initContainer.image.repository | string | `"lachlanevenson/k8s-kubectl"` | Container image to fetch loadbalancer service information |
| p2pLoadBalancerPort.initContainer.image.tag | string | `"v1.21.3"` | Container tag |
| p2pLoadBalancerPort.tcpPort | int | `30303` | P2P TCP wire protocol port (if empty TCP port won't be exposed) |
| p2pLoadBalancerPort.udpPort | int | `30301` | P2P UDP discovery port (if empty UDP port won't be exposed) |
| p2pNodePort.enabled | bool | `false` | Expose P2P port via NodePort |
| p2pNodePort.initContainer.image.pullPolicy | string | `"IfNotPresent"` | Container pull policy |
| p2pNodePort.initContainer.image.repository | string | `"lachlanevenson/k8s-kubectl"` | Container image to fetch nodeport information |
| p2pNodePort.initContainer.image.tag | string | `"v1.21.3"` | Container tag |
| p2pNodePort.port | int | `31000` | NodePort to be used |
| p2pNodePort.portForwardContainer.image.pullPolicy | string | `"IfNotPresent"` | Container pull policy |
| p2pNodePort.portForwardContainer.image.repository | string | `"alpine/socat"` | Container image for the port forwarder |
| p2pNodePort.portForwardContainer.image.tag | string | `"latest"` | Container tag |
| persistence.accessModes | list | `["ReadWriteOnce"]` | Access mode for the volume claim template |
| persistence.annotations | object | `{}` | Annotations for volume claim template |
| persistence.enabled | bool | `false` | Uses an EmptyDir when not enabled |
| persistence.existingClaim | string | `nil` | Use an existing PVC when persistence.enabled |
| persistence.selector | object | `{}` | Selector for volume claim template |
| persistence.size | string | `"20Gi"` | Requested size for volume claim template |
| podAnnotations | object | `{}` | Pod annotations |
| podDisruptionBudget | object | `{}` | Define the PodDisruptionBudget spec If not set then a PodDisruptionBudget will not be created |
| podLabels | object | `{}` | Pod labels |
| podManagementPolicy | string | `"OrderedReady"` | Pod management policy |
| priorityClassName | string | `nil` | Pod priority class |
| rbac.clusterRules | list | See `values.yaml` | Required ClusterRole rules |
| rbac.create | bool | `true` | Specifies whether RBAC resources are to be created |
| rbac.rules | list | See `values.yaml` | Required Role rules |
| readinessProbe | object | See `values.yaml` | Readiness probe |
| replicas | int | `1` | Number of replicas |
| resources | object | `{}` | Resource requests and limits |
| secretEnv | object | `{}` | Additional env variables injected via a created secret |
| securityContext | object | See `values.yaml` | The security context for pods |
| serviceAccount.annotations | object | `{}` | Annotations to add to the service account |
| serviceAccount.create | bool | `true` | Specifies whether a service account should be created |
| serviceAccount.name | string | `""` | The name of the service account to use. If not set and create is true, a name is generated using the fullname template |
| serviceMonitor.annotations | object | `{}` | Additional ServiceMonitor annotations |
| serviceMonitor.enabled | bool | `false` | If true, a ServiceMonitor CRD is created for a prometheus operator https://github.com/coreos/prometheus-operator |
| serviceMonitor.interval | string | `"1m"` | ServiceMonitor scrape interval |
| serviceMonitor.labels | object | `{}` | Additional ServiceMonitor labels |
| serviceMonitor.namespace | string | `nil` | Alternative namespace for ServiceMonitor |
| serviceMonitor.path | string | `"/metrics"` | Path to scrape |
| serviceMonitor.relabelings | list | `[]` | ServiceMonitor relabelings |
| serviceMonitor.scheme | string | `"http"` | ServiceMonitor scheme |
| serviceMonitor.scrapeTimeout | string | `"30s"` | ServiceMonitor scrape timeout |
| serviceMonitor.tlsConfig | object | `{}` | ServiceMonitor TLS configuration |
| terminationGracePeriodSeconds | int | `30` | How long to wait until the pod is forcefully terminated |
| tolerations | list | `[]` | Tolerations for pods |
| updateStrategy | object | `{"type":"RollingUpdate"}` | Update stategy for the Statefulset |
| updateStrategy.type | string | `"RollingUpdate"` | Update stategy type |

# Examples

## Connecting to the goerli test network

```yaml
extraArgs:
  - --network=goerli
  - --max-peers=60
```

## Exposing the P2P service via NodePort

This will make your node accessible via the Internet using a service of type [NodePort](https://kubernetes.io/docs/concepts/services-networking/service/#nodeport).
When using `p2pNodePort.enabled` the exposed IP address on your ENR record will be the "External IP" of the node where the pod is running.

**Limitations:** You can only run a single replica per chart deployment when using `p2pNodePort.enabled=true`.If you need N nodes, simply deploy the chart N times.
Currently besu doesn't allow you to announce a a different discovery port, which would be a requirement to run multiple replicas within the same chart.

```yaml
replicas: 1

p2pNodePort:
  enabled: true
  port: 31000
```

## Exposing the P2P service via LoadBalancer

This will make your node accessible via the Internet using a service of type [LoadBalancer](https://kubernetes.io/docs/concepts/services-networking/service/#loadbalancer).
When using `p2pLoadBalancerPort.enabled` the exposed IP address on your ENR record will be the "public IP" of the LoadBalancer service.

**Limitations:** Kubernetes currently doesn't support [mixed protocols (TCP and UDP) on the same port at service type LoadBalancer)(https://kubernetes.io/docs/concepts/services-networking/service/#load-balancers-with-mixed-protocol-types) yet,
 accordingly we use a different port for UDP (discovery protocol) which needs to be specified at enode urls with `discport` parameter ([see](https://besu.hyperledger.org/en/stable/Concepts/Node-Keys/#enode-url)).

```yaml
p2pLoadBalancerPort:
  enabled: true
  tcpPort: 30303
  udpPort: 30301
```
