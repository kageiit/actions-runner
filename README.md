# Actions Runner

A custom GitHub Actions runner Docker image with pre-installed development tools and languages.

## Overview

This repository builds and publishes a customized GitHub Actions runner image based on the official `actions-runner` image. The custom image includes additional development tools, languages, and utilities commonly needed in CI/CD workflows.

## Features

### Pre-installed Languages & Runtimes
- **Python** (3.7-3.12) with PyPy support
- **Node.js** (16, 18, 20)
- **Go** (1.19-1.21)
- **Rust** (stable toolchain with rustfmt and clippy)
- **Java** development tools
- **Ruby** runtime
- **PHP** runtime
- **R** language support
- **Swift** development tools

### Development Tools
- **Git** version control
- **GitHub CLI** (`gh`)
- **Docker** and Docker Compose
- **Azure CLI** and Azure DevOps CLI
- **AWS CLI** and tools
- **Kubernetes** tools (kubectl, helm, etc.)
- **Terraform** infrastructure as code
- **Bicep** ARM template language
- **Apache** and **Nginx** web servers
- **Build tools**: GCC, Clang, CMake, build-essential
- **Container tools**: AzCopy, Heroku CLI

### System Configuration
- Ubuntu 22.04 LTS base
- Optimized package sources and repositories
- Pre-configured environment variables
- Helper scripts for common operations

## Usage

### Docker Image

The image is automatically built and published to GitHub Container Registry:

```bash
docker pull ghcr.io/kageiit/actions-runner:latest
```

### In GitHub Actions Workflows

Use as a self-hosted runner or in containerized jobs:

```yaml
jobs:
  build:
    runs-on: ubuntu-latest
    container:
      image: ghcr.io/kageiit/actions-runner:latest
    steps:
      - uses: actions/checkout@v4
      - name: Build with pre-installed tools
        run: |
          # All tools are pre-installed and ready to use
          node --version
          python --version
          rust --version
          go version
```

## Building Locally

```bash
docker build -t actions-runner .
```

## Image Variants

- `latest` - Latest stable build from main branch
- `2.316.1` - Specific runner version tag

## Contributing

Contributions are welcome! Please feel free to submit issues or pull requests.

## License

This project follows the same license as the base actions-runner image.
