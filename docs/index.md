# Welcome to the Documentation for kubenav

<div align="center">
  <img src="https://raw.githubusercontent.com/kubenav/kubenav/master/utils/assets/github-logo.png" width="200" />
  <br><br>

  <b>kubenav</b> is the navigator for your <b>Kubernetes</b> clusters right in your pocket. kubenav is a <b>mobile and desktop</b> app to manage Kubernetes clusters and to get an overview of the status of your resources.

  <p>
    <a href="https://apps.apple.com/us/app/kubenav/id1494512160" target="_blank"><img class="app-badges" src="https://raw.githubusercontent.com/kubenav/kubenav/master/utils/assets/app-store-badge.png"></a>
    <a href="https://play.google.com/store/apps/details?id=io.kubenav.kubenav" target="_blank"><img class="app-badges" src="https://raw.githubusercontent.com/kubenav/kubenav/master/utils/assets/google-play-badge.png"></a>
    <a href="https://github.com/kubenav/kubenav/releases" target="_self"><img class="app-badges" src="https://raw.githubusercontent.com/kubenav/kubenav/master/utils/assets/desktop-badge.png"></a>
  </p>

  <img src="https://raw.githubusercontent.com/kubenav/kubenav/master/utils/assets/github-screenshot.png" width="100%" />
</div>

kubenav is a mobile and desktop app to  manage Kubernetes clusters. The app provides an overview of all resources in a Kubernetes clusters, including current status information for workloads. The details view for resources provides additional information. It is possible to view logs and events or to get a shell into a container. You can also edit and delete resources or scale your workloads within the app.

The app is developed using [Ionic Framework](https://ionicframework.com) and [Capacitor](https://capacitor.ionicframework.com). The frontend part of the app is implemented using TypeScript and React functional components. The backend part uses [Go mobile](https://github.com/golang/go/wiki/Mobile) for communication with the Kubernetes API server and Cloud Providers. So it is possible to achieve nearly 100% code sharing between the mobile and desktop implementation of kubenav.

## Features

- **Available for mobile and desktop:** kubenav provides the same experience for mobile and desktop, with nearly 100% code sharing.
- **Manage Resources:** All major resources like Deployments, StatefulSets, DaemonSets, Pods, etc. are supported.
- **Custom Resource Definitions:** View all Custom Resource Definitions and mange Custom Resources.
- **Modify Resources:** Edit and delete all available resources or scale your Deployments, StatefulSets, DaemonSets.
- **Filter and Search:** Filter the resources by Namespace and find them by there name.
- **Status Information:** Fast overview of the status of workloads and detailed information including Events.
- **Resource Usage:** View the requests, limits and current usage of Pods and Containers.
- **Logs:** View the logs of a container or stream the logs in realtime.
- **Terminal:** Get a shell into a container, right from your phone.
- **Manage multiple Clusters:** Add multiple clusters via `kubeconfig` or your prefered Cloud Provider, including Google, AWS and Azure.

## Content

- [Mobile](mobile/getting-started.md):
- [Desktop](desktop/getting-started.md):
- [Web](web/getting-started.md):
- [Developers](developers/getting-started.md):

## Repositories

- [kubenav/docs](https://github.com/kubenav/docs):
- [kubenav/kubenav](https://github.com/kubenav/kubenav):
- [kubenav/helm-repository](https://github.com/kubenav/helm-repository):
- [kubenav/deploy](https://github.com/kubenav/deploy):
- [kubenav/kubenav.io](https://github.com/kubenav/kubenav.io):
- [kubenav/kubenav-plugin](https://github.com/kubenav/kubenav-plugin):
- [kubenav/bind](https://github.com/kubenav/bind):
