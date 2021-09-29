# NGINX Ingress Controller

> Only Helm v3 is supported

This is the documentation for the NGINX Ingress Controller.

https://kubernetes.github.io/ingress-nginx/

It is built around the [Kubernetes Ingress resource](http://kubernetes.io/docs/user-guide/ingress/), using a [ConfigMap](https://kubernetes.io/docs/tasks/configure-pod-container/configure-pod-configmap/#understanding-configmaps-and-pods) to store the NGINX configuration.

NGINX Ingress controller can be installed via [Helm](https://helm.sh/) using the chart from the project repository. To install the chart with the release name `ingress-nginx`:

```
module "nginx_ingress_controller" {
  source = "git::https://github.com/DNXLabs/terraform-aws-eks-generic-chart.git"

  enabled = true

  helm_chart_name         = "ingress-nginx"
  helm_chart_release_name = "ingress-nginx"
  helm_chart_version      = "4.0.3"
  helm_chart_repo         = "https://kubernetes.github.io/ingress-nginx"
  namespace               = "ingress-nginx"

  settings = {}
}
```

#### Detect installed version

```bash
POD_NAME=$(kubectl get pods -l app.kubernetes.io/name=ingress-nginx -o jsonpath='{.items[0].metadata.name}')
kubectl exec -it $POD_NAME -- /nginx-ingress-controller --version
```