# Azure DevOps - Azure Pipelines

## Agents

In ADO Basic plan you receive 1 free agent

```
# https://docs.microsoft.com/en-us/azure/devops/pipelines/agents/hosted?view=azure-devops#use-a-microsoft-hosted-agent
pool:
  vmImage: ubuntu-18.04

```

Run on Microsoft Azure general purpose virtual machines Standard_DS2_v2


### Useful links

- Available OSs:
<https://docs.microsoft.com/en-gb/azure/devops/pipelines/agents/hosted?view=azure-devops>

- Preinstalled software:
<https://github.com/actions/virtual-environments/blob/master/images/linux/Ubuntu1804-README.md>

- GitHub Actions - They're Not Azure Pipelines:
<https://www.jamesqmurphy.com/blog/2019/11/github-actions-is-not-azure-pipelines>
