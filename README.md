# terraform-aws-eks-generic-chart

[![Lint Status](https://github.com/DNXLabs/terraform-aws-eks-generic-chart/workflows/Lint/badge.svg)](https://github.com/DNXLabs/terraform-aws-eks-generic-chart/actions)
[![LICENSE](https://img.shields.io/github/license/DNXLabs/terraform-aws-eks-generic-chart)](https://github.com/DNXLabs/terraform-aws-eks-generic-chart/blob/main/LICENSE)


Terraform module for deploying a generic chart inside Kubernetes cluster.


## Usage

```
module "generic_chart" {
  source = "git::https://github.com/DNXLabs/terraform-aws-eks-generic-chart.git"

  enabled = true

  helm_chart_name         = ""
  helm_chart_release_name = ""
  helm_chart_version      = ""
  helm_chart_repo         = ""
  namespace               = ""

  settings = {}
}
```

## Examples

- [NGINX Ingress Controller](docs/nginx-ingress-controller.md)
- [Sealed Secrets](docs/sealed-secrets.md)
- [kube-state-metrics](docs/kube-state-metrics.md)

<!--- BEGIN_TF_DOCS --->


<!--- END_TF_DOCS --->

## Authors

Module managed by [DNX Solutions](https://github.com/DNXLabs).

## License

Apache 2 Licensed. See [LICENSE](https://github.com/DNXLabs/terraform-aws-eks-generic/blob/master/LICENSE) for full details.
