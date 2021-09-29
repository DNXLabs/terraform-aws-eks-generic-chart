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

## Requirements

| Name | Version |
|------|---------|
| terraform | >= 0.13 |
| aws | >= 3.13, < 4.0 |
| helm | >= 1.0, < 3.0 |
| kubernetes | >= 1.10.0, < 3.0.0 |

## Providers

| Name | Version |
|------|---------|
| helm | >= 1.0, < 3.0 |
| kubernetes | >= 1.10.0, < 3.0.0 |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| create\_namespace | Whether to create Kubernetes namespace with name defined by `namespace`. | `bool` | `true` | no |
| enabled | Variable indicating whether deployment is enabled. | `bool` | `true` | no |
| helm\_chart\_name | Generic Helm chart name to be installed. | `string` | n/a | yes |
| helm\_chart\_release\_name | Helm release name. | `string` | n/a | yes |
| helm\_chart\_repo | Generic repository name. | `string` | n/a | yes |
| helm\_chart\_version | Generic Helm chart version. | `string` | n/a | yes |
| mod\_dependency | Dependence variable binds all AWS resources allocated by this module, dependent modules reference this variable. | `any` | `null` | no |
| namespace | Kubernetes namespace to deploy Generic Helm chart. | `string` | `"kube-system"` | no |
| settings | Additional settings which will be passed to the Helm chart values. | `map` | `{}` | no |

## Outputs

No output.

<!--- END_TF_DOCS --->

## Authors

Module managed by [DNX Solutions](https://github.com/DNXLabs).

## License

Apache 2 Licensed. See [LICENSE](https://github.com/DNXLabs/terraform-aws-eks-generic/blob/master/LICENSE) for full details.
