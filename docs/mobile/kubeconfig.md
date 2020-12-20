# Kubeconfig

You can also import a Kubeconfig file to add a new cluster to the kubenav app.

| Value | Description |
| ----- | ----------- |
| Kubeconfig | The content of your Kubeconfig file. You can copy and paste the content of the file into this Input field or you can select the file via the **Select Kubeconfig** button. |

Make sure that your Kubeconfig file does not contains paths to the certificate. Instead it should contain the base64 encoded certificate. For example: When your Kubeconfig file has a field `certificate-authority` with the path to a certificate, you have to replace this field with `certificate-authority-data` and the base64 encoded value of the certificate.

!!! attention
    Make sure that the Kubeconfig file only contains clusters and users, which are not using a Cloud Provider or OIDC for the cluster access. The import for such Kubeconfig files will fail. Please use one of the available Cloud Providers to import such clusters.
