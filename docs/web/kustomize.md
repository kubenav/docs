You can deploy kubenav into your Kubernetes cluster via [Kustomize](https://kustomize.io):

```sh
kubectl apply --kustomize github.com/kubenav/deploy/kustomize
```

To access kubenav run the following command:

```sh
kubectl port-forward --namespace kubenav svc/kubenav 14122
```
