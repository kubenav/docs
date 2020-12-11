# Command-Line Flags

The Docker image for kubenav supports the following command-line flags:

```txt
kubenav - the navigator for your Kubernetes clusters right in your pocket.

Usage:
  kubenav [flags]
  kubenav [command]

Available Commands:
  help        Help about any command
  version     Print version information for kubenav.

Flags:
      --debug                              Enable debug mode.
      --debug.ionic string                 Path to the Ionic app. (default "build")
  -h, --help                               help for kubenav
      --incluster                          Use the in cluster configuration.
      --kubeconfig string                  Optional Kubeconfig file.
      --plugin.prometheus.address string   The address for Prometheus.
      --plugin.prometheus.enabled          Enable the Prometheus plugin.

Use "kubenav [command] --help" for more information about a command.
```
