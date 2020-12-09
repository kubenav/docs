# Manual

This method can be used, when you want to manually configure each cluster.

| Value | Description |
| ----- | ----------- |
| Name | The name of the cluster, how it will be displayed in kubenav. |
| Server | The URL of the Kubernetes API server. |
| Certificate Authority Data | The certificate of the Kubernetes API server. This can be the base64 encoded value or the plain certificate. |
| Insecure Skip TLS Verify | If you haven't a certificate for the server, you can enabled the insecure mode, to skip the TLS verification. |
| Client Certificate Data | The client certificate. This can be the base64 encoded value or the plain certificate. |
| Client Key Data | The client key. This can be the base64 encoded value or the plain key. |
| Token | The access token for the Kubernetes API server. |
| Username | When you are using basic authentication you can use the username and password field. |
| Password | When you are using basic authentication you can use the username and password field. |

## Use a Service Account

If you haven't a Kubeconfig file which is compatible with kubenav or if your cloud provider isn't supported you can create a Service Account and use these credentials for the authentication.

In the first step you have to create a `ServiceAccount`, `ClusterRole` and `ClusterRoleBinding`. In the following example we create the required resources in a new Namespace named `kubenav`:

```sh
cat <<EOF | kubectl apply -f -
---
apiVersion: v1
kind: Namespace
metadata:
  name: kubenav

---
apiVersion: v1
kind: ServiceAccount
metadata:
  name: kubenav
  namespace: kubenav

---
apiVersion: rbac.authorization.k8s.io/v1
kind: ClusterRole
metadata:
  name: kubenav
  namespace: kubenav
rules:
  - apiGroups: ["*"]
    resources: ["*"]
    verbs: ["*"]

---
apiVersion: rbac.authorization.k8s.io/v1
kind: ClusterRoleBinding
metadata:
  name: kubenav
  namespace: kubenav
roleRef:
  apiGroup: rbac.authorization.k8s.io
  kind: ClusterRole
  name: kubenav
subjects:
  - kind: ServiceAccount
    name: kubenav
    namespace: kubenav
EOF
```

Now we have to use the created secret, which is used by the Service Account. To get the name of the secret run the following command:

```sh
export SECRET_NAME=$(kubectl get sa --namespace kubenav kubenav -o=jsonpath='{.secrets[*].name}')
```

To get the certificate and access token to authenticate against the Kubernetes API we can run the following:

```sh
kubectl get secret $SECRET_NAME -o=jsonpath='{.data.ca\.crt}' | base64 --decode
kubectl get secret $SECRET_NAME -o=jsonpath='{.data.token}' | base64 --decode
```

The output from the first command can now be used for the `Certificate Authority Data` field and the output from the second command for the `Token` field.

> **Attention:** The specified RBAC rules from the example provide full cluster access wihtout any restrictions. More information can be found in the Kubernets documentation: [Using RBAC Authorization](https://kubernetes.io/docs/reference/access-authn-authz/rbac/).
