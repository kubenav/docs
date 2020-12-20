# Configuration

The desktop version of kubenav will automatic load all configured clusters from the default Kubeconfig file at `~/.kube/config` or the `KUBECONFIG` environment variable. If you want to use another Kubeconfig file, you can start kubenav with the `--kubeconfig` flag.

You can also use the `--kubeconfig.include` and `--kubeconfig.exclude` flag to load Kubeconfig files from multiple locations by glob. The following example loads all Kubeconfig files which are starting with `kube` from the `~/Documents/kubeconfigs-prod` and `~/Documents/kubeconfigs-dev` folder:

```sh
kubenav --kubeconfig.include ~/Documents/kubeconfigs-prod/kube*,~/Documents/kubeconfigs-dev/kube*
```

The `--kubeconfig.sync` flag can be used to write context changes back to your Kubeconfig file, so the context is also changed in your terminal.

!!! attention
    kubenav is based on Electron and go-astilectron, which will be downloaded on the first start of the app. Therefore the first start of the app can take a bit longer with a slow internet connection.
