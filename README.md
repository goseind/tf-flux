# Using Terraform to Maintain Flux

This repo showcases the usage of the [terraform fluxcd provider](https://registry.terraform.io/providers/fluxcd/flux/latest). **Please see my [blog post](https://gosein.de/terraform-maintain-flux.html) for more details.**

You can use this repo as a template to get started, what you'll need is a K8s cluster (with the `config` saved in the default `.kube` directory), a GitHub repo, and a token with repo access.

## TL;TR

Replace the variable values in the `terraform apply` command below, then copy and paste this into your terminal:

```bash
git clone https://github.com/goseind/tf-flux
cd tf
terraform init
terraform apply -var github_org="<your-orga-or-username>" -var github_repository="<your-repo-name>" -var github_token="<your-token>"
mkdir ../flux/cluster
cp ../test/test-manifest.yaml ../flux/cluster/test-manifest.yaml
git add test-manifest.yaml
git commit -m 'apply test manifest to cluster'
git push
```

After this, all new files in `flux/cluster` will be synced with Flux, while the Flux installation itself is maintained by Terraform.
