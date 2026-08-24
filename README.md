# trivy_scan

This repository includes a GitHub Actions workflow at
`.github/workflows/trivy-acr-image-scan.yml`
that scans a container image stored in Azure Container Registry with
[`aquasecurity/trivy-action`](https://github.com/marketplace/actions/aqua-security-trivy).

## Required configuration

- `AZURE_CREDENTIALS` GitHub secret containing Azure service principal credentials
  with access to the target registry.
- `ACR_NAME` GitHub variable with the Azure Container Registry name.
- `ACR_IMAGE_REPOSITORY` GitHub variable with the image repository name.
- Optional `ACR_IMAGE_TAG` GitHub variable. Defaults to `latest`.
- Optional `ACR_LOGIN_SERVER` GitHub variable if you need to override the default
  `<acr-name>.azurecr.io` login server.

You can also start the workflow manually with `workflow_dispatch` inputs to
override the configured registry name, image repository, and image tag.
