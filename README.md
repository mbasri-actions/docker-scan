# Docker Scan Action

This GitHub Action scans a Docker image for vulnerabilities using Trivy and uploads the scan results as an artifact.

## Features

- Scans Docker images for vulnerabilities using Trivy
- Uploads the scan results as an artifact
- Supports JSON output format


## Inputs

| Name        | Description                          | Default |
|-------------|--------------------------------------|---------|
| `image-ref` | The reference to the Docker image    | `null`  |

## Usage

Here's an example of how to use this action in a GitHub Actions workflow:

```yaml
name: Build, Push and Sign Docker Image

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
      - name: Checkout code
        uses: actions/checkout@main
      - name: Scan Docker image for vulnerabilities
        uses: mbasri-actions/docker-scan@main
        with:
          image-ref: 'ghcr.io/your-username/your-image:latest'
```

## Author

* [**Mohamed BASRI**](https://github.com/mbasri)

## License

This is free and unencumbered software released into the public domain. See the [LICENSE](./LICENSE) file for details.
