# template-tf-modules

Terraform module to create a Client VPN enpoint inside your VPC


## Usage

```hcl
module "vpn" {
  source                     = "git::https://github.com/pagopa/terraform-aws-client-vpn-endpoint.git?ref=v1.0.0"
  endpoint_name              = "vpn"
  endpoint_client_cidr_block = "10.100.0.0/22"
  endpoint_subnets           = [module.vpc.private_subnets[0]] # Attach VPN to single subnet. Reduce cost
  endpoint_vpc_id            = module.vpc.vpc_id
  tls_subject_common_name    = "vpn.sandbox.pagopa.it"
  saml_provider_arn          = aws_iam_saml_provider.vpn.arn

  authorization_rules = {}

  authorization_rules_all_groups = {
    full_access_private_subnet_0 = module.vpc.private_subnets_cidr_blocks[0]
  }
}
```


<!-- BEGIN_TF_DOCS -->
<!-- END_TF_DOCS -->