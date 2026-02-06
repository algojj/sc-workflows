# sc-workflows

Workflows reutilizables para todos los repos de algojj.

## Uso

### CI (en tu repo)

```yaml
name: CI
on: [push, pull_request]

jobs:
  ci:
    uses: algojj/sc-workflows/.github/workflows/ci.yml@main
```

### Deploy (en tu repo)

```yaml
name: Deploy
on:
  release:
    types: [published]
  workflow_dispatch:

jobs:
  deploy:
    uses: algojj/sc-workflows/.github/workflows/deploy.yml@main
    with:
      k8s_deployment: "mi-deployment"
      image_name: "sc-mi-repo"
    secrets: inherit
```
