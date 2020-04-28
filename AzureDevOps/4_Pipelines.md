# Azure DevOps - Azure Pipelines

There are three different ways how you can implement your pipeline in ADO.

1. Build Pipeline (CI)
   - YAML
   - Classic (Click-Ops)
2. Release Pipeline (CD)
   - Classic (Click-Ops)

- CI, CD, YAML & Classic:
<https://docs.microsoft.com/en-us/azure/devops/pipelines/get-started/pipelines-get-started?view=azure-devops>

- YAML Schema:
<https://docs.microsoft.com/en-gb/azure/devops/pipelines/yaml-schema?view=azure-devops&tabs=schema%2Cparameter-schema>

- Available ADO modules/tasks + example YAML snippets:
<https://docs.microsoft.com/en-us/azure/devops/pipelines/tasks/?view=azure-devops>

- Example pipelines:
  - <https://dev.azure.com/ms/azure-devops-dotnet-samples/_release>
  - <https://microsoft.github.io/PartsUnlimited/iac/200.2x-IaC-SecurityandComplianceinpipeline.html>
  - <https://cloudblogs.microsoft.com/opensource/2019/05/06/azure-pipelines-update-free-open-source-builds/>

## Issues

- Read-Only SSH project key - there is no way to setup SSH key for pulling only repos from Azure DevOps
  - like deploy keys in gitlab - https://docs.gitlab.com/ee/ssh/#deploy-keys

- Slow caching feature, it's slower than downloading image directly from ACR:
29s to save image in cache + 42s to save cache + 46s to load cache in next job + 48s to load image from cache
vs 29s to download image from ACR
<https://docs.microsoft.com/en-us/azure/devops/pipelines/release/caching?view=azure-devops>
<https://dev.azure.com/nhsapp/NHS%20App/_build/results?buildId=4596&view=logs&j=46d68182-90a1-5651-c618-877729e79262&t=427ca9d3-930d-5b7a-101c-77270a217ac9>

- No shared volume ability - one job is run on one agent and after the job is finished local storage is cleanup'ed and there is no way to share it efficiently between agents/jobs - there is a caching feature mentioned above, but it's slow and in preview.
example drone-ci implementation - https://docs.drone.io/pipeline/docker/syntax/volumes/temporary/
