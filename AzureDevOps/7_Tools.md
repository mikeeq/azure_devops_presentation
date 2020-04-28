# Azure DevOps - Tools

## Security Scans

- Hawkeye - integrates multiple check into one CLI app,
- OWASP ZAP
- ClamAV Scan <https://github.com/djdefi/gitavscan>

### Container Vulnerabilities

- Clair - just a database, you need to use external client for scanning your Images
- Trivy - builtin client, lightweight

  ```
  docker run \
  --rm \
  -t \
  -v /var/run/docker.sock:/var/run/docker.sock \
  "${RUNNER_DOCKER_IMAGE}" /bin/bash -c "
    trivy --exit-code 0 --severity UNKNOWN,LOW,MEDIUM --ignore-unfixed --no-progress ${IMAGE_TO_SCAN} && \
    trivy --exit-code 1 --severity HIGH,CRITICAL --ignore-unfixed --no-progress ${IMAGE_TO_SCAN} \
  "
  ```

- Snyk - the only one with .Net, NuGet vulnerabilities database - requires connection to external service, it also stores the result there
- Twistlock/Prisma Cloud


## Static Analysis

- Hadolint - Dockerfile Linter
- yamllint- YAML Linter
- ShellCheck - Bash/Sh Linter
- kube-score - scans k8s yamls, suggests improvements to your resource definitions
- popeye - similar to kube-score but scans k8s cluster itself, not yamls

### Terraform
- terraform fmt - builtin feature in terraform CLI to scan your terraform code for any syntax issues and even automatically correct it


### If you're using Helm templates

You can render them using `helm




## Useful links

Example GitLab-CI security pipeline: <https://github.com/hysnsec/DevSecOps-Studio/wiki/Lesson-three:-Adding-SAST-and-DAST-into-the-pipeline>
