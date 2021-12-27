# Microsoft Azure

To import your AKS clusters from Microsoft Azure your have to provide some credentials. The instructions on how to get/create these credentials can be found in the following.

| Value | Description |
| ----- | ----------- |
| Subscription ID | A unique alphanumeric string that identifies your Azure subscription.  |
| Client ID | Client ID for your created Application. |
| Client Secret | Client Secret for your created Application. |
| Tenant ID | A unique id for your application which can be created via the Azure Active Directory. |
| Resource Group Name | The name of the resource group, where your AKS clusters were created. |
| Admin Credentials | When you activate this toggle kubenav will download the Kubeconfig file with the admin credentials of your user. |

## Microsoft Azure: Creating App Credentials

Login to the [Microsoft Azure Portal](https://portal.azure.com/), you need the following information to use the Azure integration for kubenav:

- Subscription ID
- Client ID
- Client Secret
- Tenant ID
- Resource Group Name

To get a Client ID, Client Secret and Tenant ID, you have to create an **App registration**, in the **Azure Active Directory**. For this go to **Azure Active Directory**, **App registrations** and create a **New registration**. You do not need to provide a Redirect URI. After the creation note download the **Application (client) ID** and **Directory (tenant) ID**.

![Microsoft Azure: Creating App Credentials](../images/mobile/microsoft-azure-1.png)

Then for this **App registration** go to **Certificates & secrets** and create a new **Client secret**.

![Microsoft Azure: Creating App Credentials](../images/mobile/microsoft-azure-2.png)

Then for this **App registration** go to **Manifest** and set <code>"oAuth2AllowImplicitFlow": true</code>. Then save the changed manifest.

![Microsoft Azure: Creating App Credentials](../images/mobile/microsoft-azure-3.png)

Next you have to give the new **App registration** permissions to manage the above resources. For this go to **Subscriptions**, choose the subscription that you want to use with kubenav, take a note of the **Subscription ID** and then go to **Access control (IAM)** in your subscription.

![Microsoft Azure: Creating App Credentials](../images/mobile/microsoft-azure-4.png)

There add a new **Role assignment** between the role **Contributor** and the **Azure AD user, group or service principal** that you just created.

![Microsoft Azure: Creating App Credentials](../images/mobile/microsoft-azure-5.png)
