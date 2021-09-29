# Sealed Secrets

https://github.com/bitnami-labs/sealed-secrets

Problem: "I can manage all my K8s config in git, except Secrets."

Solution: Encrypt your Secret into a SealedSecret, which is safe to store - even to a public repository. The SealedSecret can be decrypted only by the controller running in the target cluster and nobody else (not even the original author) is able to obtain the original Secret from the SealedSecret.


```
module "sealed_secrets" {
  source = "git::https://github.com/DNXLabs/terraform-aws-eks-generic-chart.git"

  enabled = true

  helm_chart_name         = "sealed-secrets"
  helm_chart_release_name = "sealed-secrets"
  helm_chart_version      = "1.16.1"
  helm_chart_repo         = "https://bitnami-labs.github.io/sealed-secrets"
  namespace               = "sealed-secrets"

  settings = {}
}
```

#### Usage

https://github.com/bitnami-labs/sealed-secrets#usage