# sample-github-action

> Spring Boot application with a GitHub Actions CI/CD workflow — builds, tests, packages a Docker image, and deploys to Kubernetes.

[![Java](https://img.shields.io/badge/Java-11+-orange?logo=java&logoColor=white)](https://java.com)
[![Spring Boot](https://img.shields.io/badge/Spring_Boot-2.x-6DB33F?logo=spring&logoColor=white)](https://spring.io/projects/spring-boot)
[![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-CI%2FCD-2088FF?logo=github-actions&logoColor=white)](https://github.com/features/actions)
[![Docker](https://img.shields.io/badge/Docker-ready-2496ED?logo=docker&logoColor=white)](https://docker.com)

## Overview

A reference project demonstrating a complete **GitHub Actions CI/CD pipeline** for a Spring Boot application:

1. **CI:** Build, test, and create Docker image on every push
2. **CD:** Push image to registry and update Kubernetes manifest repo

## Workflow

```
Push to main
    └─► GitHub Actions
            ├─► mvn clean test         (unit tests)
            ├─► docker build & push    (container registry)
            └─► update manifest repo   (GitOps deployment)
```

## Getting Started

```bash
git clone https://github.com/misoboy/sample-github-action.git
cd sample-github-action

# Run locally
./mvnw spring-boot:run
```

### Docker

```bash
docker build -t sample-github-action .
docker run -p 8080:8080 sample-github-action
```

## GitHub Actions Workflows

| Workflow | Trigger | Description |
|----------|---------|-------------|
| `ci.yml` | push, PR | Build and test |
| `cd.yml` | push to main | Docker build + deploy |

## Related

- [sample-manifest](https://github.com/misoboy/sample-manifest) — Kubernetes manifests for this application

## License

MIT

