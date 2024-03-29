# `deploy-action`
> Deploys your feature pipelines to Chalk.

---

## About
This action deploys your feature pipelines to Chalk from GitHub's hosted Actions runners.

This action can be run on `ubuntu-latest` and `macos-latest` 
GitHub Actions runners, and will install and expose a specified version of the 
`chalk` CLI on the runner environment.

---

## Usage

```yaml
steps:
- uses: chalk-ai/deploy-action@v2
  with:
    client-id: ...
    client-secret: ...
```

You can also deploy to branches with this workflow:

```yaml
steps:
- uses: chalk-ai/deploy-action@v2
  with:
    branch: ${{ GITHUB_REF_NAME }}
    client-id: ...
    client-secret: ...
```

---

## Inputs
The action supports the following inputs:

- `client-id`: The Chalk Client ID from the tokens page in your settings.
- `client-secret`: The Chalk Client Secret from the tokens page in your settings.
- `await` (optional): Should this step block until it completes? Defaults to true.
- `branch` (optional): By default, Chalk will deploy to your production environment. With `branch`, your pipelines will deploy to a Chalk branch.
- `version` (optional): The version of `chalk` to install, defaulting to `latest`.
- `api-host` (optional): If you're using a self-hosted deployment, the API host where Chalk is hosted.
- `environment` (optional): The Chalk environment to use. Your token is typically scoped to a single environment, and you won't need to use this parameter.
- `no-promote` (deprecated): By default, Chalk will deploy to your production environment. With `no-promote`, your pipelines will deploy to a preview environment.

---

## License
Apache 2.0
