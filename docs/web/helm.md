# Helm

You can deploy kubenav into your Kubernetes cluster via [Helm](https://helm.sh):

```sh
helm repo add kubenav https://kubenav.github.io/helm-repository
helm repo update

kubectl create namespace kubenav
helm upgrade --install --namespace kubenav kubenav kubenav/kubenav
```

## Values

| Value | Description | Default |
| ----- | ----------- | ------- |
| `replicaCount` | Number of replicas which should be created. | `1` |
| `image.repository` | The repository of the Docker image. | `kubenav/kubenav` |
| `image.tag` | The tag of the Docker image which should be used. | `3.2.0` |
| `image.pullPolicy` | The pull policy for the Docker image, | `IfNotPresent` |
| `imagePullSecrets` | Secrets which can be used to pull the Docker image. | `[]` |
| `nameOverride` | Expand the name of the chart. | `""` |
| `fullnameOverride` | Override the name of the app. | `""` |
| `deployment.mode` | Set the mode how kubenav should be deployed. This must be `incluster` or `kubeconfig`. | `incluster` |
| `deployment.kubeconfig` | When the `kubeconfig` mode is used. This must be a base64 encoded Kubeconfig file. | `""` |
| `plugins.prometheus.enabled` | Enables the Prometheus plugin. | `false` |
| `plugins.prometheus.address` | The address of Prometheus. | `""` |
| `rbac.create` | Create the cluster role and cluster role binding. | `true` |
| `rbac.name` | The name of the cluster role and cluster role binding, which should be created/used by kubenav. | `kubenav` |
| `rbac.name` | The permissions which kubenav should have. This must be `admin` or `viewer`. | `admin` |
| `serviceAccount.create` | Create the service account. | `true` |
| `serviceAccount.annotations` | Additional annotations for the service account. | `true` |
| `serviceAccount.name` | The name of the service account, which should be created/used by kubenav. | `kubenav` |
| `podSecurityContext` | Security context for the kubenav pod. | `{}` |
| `securityContext` | Security context for the kubenav container. | `{}` |
| `service.type` | Type of the service which is created. | `ClusterIP` |
| `service.port` | Port of the service which is created. | `14122` |
| `ingress.enabled` | Create an ingress. | `false` |
| `ingress.annotations` | Additional annotations for the ingress. | `{}` |
| `ingress.hosts` | Hosts for the ingress. | `[]` |
| `ingress.tls` | TLS configuration for the ingress. | `[]` |
| `resources` | Set resources for the operator. | `{}` |
| `nodeSelector` | Set a node selector. | `{}` |
| `tolerations` | Set tolerations. | `[]` |
| `affinity` | Set affinity. | `{}` |

## Contributing

Each contribution to kubenav is welcome. If you make changes to the Helm chart you have to bump the `version` in the [`helm/Chart.yaml`](https://github.com/kubenav/deploy/blob/master/helm/Chart.yaml) file. Then a new version of the Helm chart is automatically published when your PR is merged into the master branch.

When you add a new value to the [`helm/values.yaml`](https://github.com/kubenav/deploy/blob/master/helm/values.yaml) file, please also adjust the [documentation](https://docs.kubenav.io/web/helm/).
