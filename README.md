# K8s Prometheus Grafana

[K8s](https://kubernetes.io/) + [Prometheus](https://prometheus.io/) + [Grafana](https://grafana.com/)

If you are from China, please set up a `registry.k8s.io` mirror first. Ref: [K3s Registry Mirror](https://github.com/jerryshell/k3s-registry-mirror)

```bash
git clone https://github.com/jerryshell/k8s-prometheus-grafana.git
cd k8s-prometheus-grafana
```

```bash
kubectl create -f kube-prometheus/setup
```

<details>

<summary>Expected output</summary>

```
customresourcedefinition.apiextensions.k8s.io/alertmanagerconfigs.monitoring.coreos.com created
customresourcedefinition.apiextensions.k8s.io/alertmanagers.monitoring.coreos.com created
customresourcedefinition.apiextensions.k8s.io/podmonitors.monitoring.coreos.com created
customresourcedefinition.apiextensions.k8s.io/probes.monitoring.coreos.com created
customresourcedefinition.apiextensions.k8s.io/prometheuses.monitoring.coreos.com created
customresourcedefinition.apiextensions.k8s.io/prometheusagents.monitoring.coreos.com created
customresourcedefinition.apiextensions.k8s.io/prometheusrules.monitoring.coreos.com created
customresourcedefinition.apiextensions.k8s.io/scrapeconfigs.monitoring.coreos.com created
customresourcedefinition.apiextensions.k8s.io/servicemonitors.monitoring.coreos.com created
customresourcedefinition.apiextensions.k8s.io/thanosrulers.monitoring.coreos.com created
namespace/monitoring created
```

</details>

```bash
kubectl apply -f kube-prometheus/
```

## Remove

```bash
kubectl delete --ignore-not-found=true -f kube-prometheus/ -f kube-prometheus/setup
```

## LICENSE

[GNU Affero General Public License v3.0](https://choosealicense.com/licenses/agpl-3.0/)
