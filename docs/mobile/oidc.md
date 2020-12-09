# OIDC

If you are using an OIDC provider to manage the access to your Kubernetes cluster, you can configure this in the **OIDC Provider** section within the **Add Clusters** modal:

| Value | Description |
| ----- | ----------- |
| Discovery URL | The url for your OIDC provider. |
| Client ID | A valid client id for your OIDC provider. |
| Client Secret | A valid client secret for your OIDC provider. |
| Certificate Authority | If your OIDC provider uses a self signed certificate, you must provide this certificate. This field is optional for OIDC providers without a self signed certificate. |
| Refresh Token | You can provide a valid refresh token to skip the login process. This field is optional. If the field isn't provided you will be redirected to your OIDC provider to get a refresh token. |

> **Attention:** You must allow `https://kubenav.io/oidc.html` as a valid redirect url in the settings of your OIDC provider.

When the login process within your OIDC provider is finished, you have to provide the details of your Kubernetes cluster:

| Value | Description |
| ----- | ----------- |
| Name | The name of the cluster, how it will be displayed in kubenav. |
| Server | The URL of the Kubernetes API server. |
| Certificate Authority Data | The certificate of the Kubernetes API server. This can be the base64 encoded value or the plain certificate. |
| Insecure Skip TLS Verify | If you haven't a certificate for the server, you can enabled the insecure mode, to skip the TLS verification. |
