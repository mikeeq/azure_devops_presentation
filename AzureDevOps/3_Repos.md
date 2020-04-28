# Azure DevOps - Azure Repos

Microsoft is using custom implementation of git in their Azure Repos service to keep it compatible with their old VCS solution TFVC (Team Foundation Version Control).

You will find some quirks about it, but in theory it should be painless in use and you shouldn't 'feel any difference' (comparing to 'standard' Git Servers).

## Useful links

- Azure Repos git Limits: <https://docs.microsoft.com/en-us/azure/devops/repos/git/limits?view=azure-devops>
- Azure Repos RPC failures and http.postBuffer: <https://docs.microsoft.com/en-us/azure/devops/repos/git/rpc-failures-http-postbuffer?view=azure-devops>

## Terraform module SSH

```bash
# https://docs.microsoft.com/en-us/azure/devops/repos/git/use-ssh-keys-to-authenticate?view=azure-devops&tabs=current-page#step-3-clone-the-git-repository-with-ssh

git clone git@ssh.dev.azure.com:v3/fabrikam-fiber/FabrikamFiber/FabrikamFiber
```

```bash
# TF
module "vnet" {
  source             = "git::git@ssh.dev.azure.com:v3/nhsapp/NHS%20App/nhsapp-ops-terraform-module-azure-vnet?ref=v2.0"
...
