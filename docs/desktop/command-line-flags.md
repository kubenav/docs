The desktopversion of kubenav supports the following command-line flags:

```
kubenav - the navigator for your Kubernetes clusters right in your pocket.

Usage:
  kubenav [flags]
  kubenav [command]

Available Commands:
  help        Help about any command
  version     Print version information for kubenav.

Flags:
      --debug                       Enable debug mode.
  -h, --help                        help for kubenav
      --kubeconfig string           Optional Kubeconfig file.
      --kubeconfig.exclude string   Comma separated list of globs to exclude from the Kubeconfig. This flag must be used in combination with the '--kubeconfig.include' flag.
      --kubeconfig.include string   Comma separated list of globs to include in the Kubeconfig.
      --kubeconfig.sync             Sync the changes from kubenav with the used Kubeconfig file.

Use "kubenav [command] --help" for more information about a command.
```
