# template-tf-modules

Terraform module to create a Client VPN enpoint inside your VPC


### tfenv setup

Set the terraform version with tfenv, before launch pre-commit to avoid errors

```bash
tfenv use <x.y.x>
```

### Run pre-commit on local machine

Check your code before commit.

<https://github.com/antonbabenko/pre-commit-terraform#how-to-install>

```sh
# for terraform modules we need to initialize them with
bash .utils/terraform_run_all.sh init local
pre-commit run -a
```

<!-- BEGIN_TF_DOCS -->
<!-- END_TF_DOCS -->