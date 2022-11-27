# Heroku Custom Google Cloud Build image

## Installation

See [README](../README.md).

## Usage

1. Get the [Heroku API key](https://devcenter.heroku.com/articles/platform-api-quickstart#authentication).
1. Store it as a secret in the [Secret Manager](https://cloud.google.com/secret-manager) (named, say, `HEROKU_API_KEY`).
2. Add the secret to the `cloudbuild.yaml`:

```yaml
availableSecrets:
  secretManager:
    - versionName: projects/$PROJECT_ID/secrets/HEROKU_API_KEY/versions/latest
      env: 'HEROKU_API_KEY'
```

3. Bind value of the secret to the build step:

```yaml
- name: 'gcr.io/$PROJECT_ID/heroku'
  args: [ 'container:login' ]
  secretEnv: [ 'HEROKU_API_KEY' ]
```

## Links

- https://devcenter.heroku.com/articles/platform-api-quickstart#authentication
- https://cloud.google.com/secret-manager
