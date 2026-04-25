# Day 29 Hands-On Revision

Document all commands run for repeated weak topics.

## 1) State Commands Practice

```bash
echo 'resource "random_id" "test" { byte_length = 4 }' > main.tf
terraform init
terraform apply -auto-approve
terraform state list
terraform state show random_id.test
terraform state rm random_id.test
terraform state list
terraform destroy -auto-approve
```

## 2) Workspace Practice

```bash
terraform workspace new dev
terraform workspace new staging
terraform workspace list
terraform workspace select dev
terraform workspace show
terraform workspace delete staging
```

## 3) Provider Version Constraints Practice

```hcl
terraform {
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 5.0"
    }
  }
}
```

```hcl
terraform {
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 5.0.0"
    }
  }
}
```

```hcl
terraform {
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = ">= 5.0, < 6.0.0"
    }
  }
}
```
