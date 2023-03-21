# Maintain flux with terraform

This repo showcases the usage of the [terraform fluxcd provider](https://registry.terraform.io/providers/fluxcd/flux/latest).

```bash
git clone <this-repo-url>
cd tf
terraform init
terraform apply # enter orga, repo and token
```

After this all new files in `flux/cluster` will be synced with flux, while the flux installation itself is maintained by terraform.
