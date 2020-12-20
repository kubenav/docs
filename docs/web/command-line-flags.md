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
      --debug                                           Enable debug mode.
      --debug.ionic string                              Path to the Ionic app. (default "build")
  -h, --help                                            help for kubenav
      --incluster                                       Use the in cluster configuration.
      --kubeconfig string                               Optional Kubeconfig file.
      --plugin.elasticsearch.address string             The address for Elasticsearch.
      --plugin.elasticsearch.enabled                    Enable the Elasticsearch plugin.
      --plugin.elasticsearch.password string            The password for Elasticsearch.
      --plugin.elasticsearch.username string            The username for Elasticsearch.
      --plugin.prometheus.address string                The address for Prometheus.
      --plugin.prometheus.dashboards-namespace string   The namespace, where kubenav should look for dashboards. (default "kubenav")
      --plugin.prometheus.enabled                       Enable the Prometheus plugin.
      --plugin.prometheus.password string               The password for Prometheus.
      --plugin.prometheus.username string               The username for Prometheus.

Use "kubenav [command] --help" for more information about a command.
```

## Environment Variables

The following command-line flags can be replaced via environment variables:

| Command-Line Flag | Environment Variable |
| ----------------- | -------------------- |
| `--plugin.elasticsearch.password` | `KUBENAV_ELASTICSEARCH_PASSWORD` |
| `--plugin.elasticsearch.username` | `KUBENAV_ELASTICSEARCH_USERNAME` |
| `--plugin.prometheus.password` | `KUBENAV_PROMETHEUS_PASSWORD` |
| `--plugin.prometheus.username` | `KUBENAV_PROMETHEUS_USERNAME` |
