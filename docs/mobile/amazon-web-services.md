To use the Amazon Web Services provider to import your EKS cluster you have to provide the following AWS credentials:

| Value | Description |
| ----- | ----------- |
| Access Key ID | Access key for AWS. |
| Secret Key | A secret key which corresponds to your **Access Key ID**. |
| Region | Your AWS region. |

These credentials are also used to mange the authentication against the Kubernetes API server of your EKS cluster. So make sure that the **Access Key ID** has the rights to get a list of your EKS clusters and to access your cluster.

## AWS Single Sign-On

You can also use AWS Single Sign-On within kubenav, for that you have to provide the following settings:

| Value | Description |
| ----- | ----------- |
| Start URL | The start URL for AWS Single Sign-On process. |
| Account ID | Is the ID of your AWS account. |
| Role Name | Is the name of a role, which is connected with your AWS SSO account. |
| SSO Region | The AWS region, where you configured SSO. |
| Region | The region for your Kubernetes cluster. |
