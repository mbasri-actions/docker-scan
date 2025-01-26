# Docker Scan Action

This GitHub Action scans a Docker image for vulnerabilities using Trivy and uploads the scan results as an artifact.

## Features

- Scans Docker images for vulnerabilities using `Trivy`
- Uploads the scan results as an artifact
- Supports JSON output format

## Requirements

| Name | Version |
|------|---------|
| <a name="requirement_aquasecurity_trivy_action"></a> [aquasecurity/trivy-action](https://github.com/aquasecurity/trivy-action) | 0.29.0 |
| <a name="requirement_actions_upload_artifact"></a> [actions/upload-artifact](https://github.com/actions/upload-artifact) | 4.6.0 |

## Inputs

| Name | Description | Required | Default |
| --- | --- | --- | --- |
| <a name="input_image_ref"></a> [image-ref](#input_image_ref) | The reference to the Docker image  | true | `null` |

## Outputs

`No Outputs`

## Usage

Here's an example of how to use this action in a GitHub Actions workflow:

```yaml
name: Scan Docker Image

on:
  push:
    branches: [ main, dev ]
  pull_request:
    branches: [ main ]
  workflow_dispatch:

jobs:
  build-and-sign:
    runs-on: ubuntu-latest

    steps:
    - uses: mbasri-actions/docker-scan@v1.0.0
      with:
        image-ref: ghcr.io/my-image:dev
```

## Author

* [**Mohamed BASRI**](https://github.com/mbasri)

## License

This is free and unencumbered software released into the public domain. See the [LICENSE](./LICENSE) file for details.
