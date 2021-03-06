# Settings

kubenav provides multiple settings, to customize the look and usage of the app.

## General

| Setting | Description | Values | Default |
| ------- | ----------- | ------ | ------- |
| Theme | Set the theme which should be used for kubenav. | `System`, `Dark`, `Light` | `System` |
| Request Timeout (in seconds) | The maximum time in seconds for a request. | `10` - `120` | `60` |
| Terminal Font Size (in px) | The font size for the terminal. | `8` - `48` | `12` |
| Terminal Scrollback (in lines) | The maximum number of lines to scrollback in the terminal. | `1000` - `50000` | `10000` |
| Enable Pod Metrics | Enables or disables the metrics for Pods in list views. | `true`, `false` | `true` |
| Limit | The maximum number of items which can be queried per request. | `100` - `1000` | `100`  |
| Refresh Interval (in seconds) | The interval in which the data of views is refreshed. | `30` - `600` | `300` |

## SSH

| Setting | Description | Default |
| ------- | ----------- | ------- |
| Port | The port, which should be used for the SSH connection. | `22` |
| Private Key | The private key, which should be used for the SSH connection. | |
| User | The name of the user, which should be used for the SSH connection. | |

## Prometheus

| Setting | Description | Default |
| ------- | ----------- | ------- |
| Enabled | Enables or disables the Prometheus plugin. | `false` |
| Namespace | The namespace, where Prometheus is running. | `monitoring` |
| Selector | The selector, which matches the Prometheus Pod. | `app=prometheus` |
| Port | The port, where the Prometheus API is exposed. | `9090` |
| Username | Username for Prometheus, when the Prometheus endpoint is protected via Basic Authentication. | |
| Password | Password for Prometheus, when the Prometheus endpoint is protected via Basic Authentication. | |
| Dashboards Namespace | The namespace, where kubenav should look for dashboards. | `kubenav` |

## Elasticsearch

| Setting | Description | Default |
| ------- | ----------- | ------- |
| Enabled | Enables or disables the Elasticsearch plugin. | `false` |
| Namespace | The namespace, where Elasticsearch is running. | `logging` |
| Selector | The selector, which matches the Elasticsearch Pod. | `app=elasticsearch` |
| Port | The port, where the Elasticsearch API is exposed. | `9200` |
| Username | Username for Elasticsearch, when the Elasticsearch endpoint is protected via Basic Authentication. | |
| Password | Password for Elasticsearch, when the Elasticsearch endpoint is protected via Basic Authentication. | |

## Jaeger

| Setting | Description | Default |
| ------- | ----------- | ------- |
| Enabled | Enables or disables the Jaeger plugin. | `false` |
| Namespace | The namespace, where Jaeger is running. | `tracing` |
| Selector | The selector, which matches the Jaeger Pod. | `app=jaeger,app.kubernetes.io/component=query` |
| Port | The port, where the Jaeger API is exposed. | `16686` |
| Username | Username for Jaeger, when the Jaeger endpoint is protected via Basic Authentication. | |
| Password | Password for Jaeger, when the Jaeger endpoint is protected via Basic Authentication. | |
| Query Base Path | The base path for all Jaeger Query HTTP routes. This must be the same as the `--query.base-path` command line parameter or the `QUERY_BASE_PATH` environment variable. | |

## Proxy

| Setting | Description |
| ------- | ----------- |
| Enabled | When the proxy setting is enabled, all requests are using the configured proxy. |
| Address | The address of the proxy. |
