# Configure Access to Multiple Clusters

!!! attention
    When kubenav runs inside a Kubernetes cluster with the `--kubeconfig` flag and the Prometheus plugin enabled (`--plugin.prometheus.enabled`) it will only use the Prometheus instance, which is running in the same cluster.

## Kustomize

The [deployment](https://github.com/kubenav/deploy/blob/master/kustomize/deployment.yaml) shown in the [kubenav/deploy](https://github.com/kubenav/deploy) repository deploys kubenav with the `--incluster` flag. This means kubenav has only access to the cluster were it is deployed in. To deploy kubenav with access to multiple cluster you have to mount a Kubeconfig file into the kubenav container and add the `--kubeconfig` flag.

The following example shows the changes you have to made to the `deployment.yaml` file to access multiple clusters from the same kubenav instance:

```yaml
spec:
  template:
    spec:
      containers:
        - name: kubenav
          args:
             - --kubeconfig=/kubenav/kubeconfig/kubeconfig
          volumeMounts:
            - name: kubeconfig
              mountPath: '/kubenav/kubeconfig'
              readOnly: true
      volumes:
        - name: kubeconfig
          secret:
            secretName: kubeconfig
```

The above example mounts a secret named `kubeconfig` into the kubenav pod and makes use of the Kubeconfig via the `--kubeconfig` flag. The secret must look as follows:

```yaml
---
apiVersion: v1
kind: Secret
metadata:
  name: kubeconfig
data:
  kubeconfig: <REPLACE WITH YOUR BASE64 ENCODED KUBECONFIG>
type: Opaque
```

The value for the `data.kubeconfig` key can be created with `cat ~/.kube/config | base64`.

## Helm

You can choose this mode also with the Helm Chart, for that you have to set the `deployment.mode` value to `kubeconfig` and you have to provide your base64 encoded Kubeconfig via the `deployment.kubeconfig` value.
