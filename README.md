# Cloud Run Docker Deploy Composite Action

A GitHub Action that builds and deploys a docker image to GCP Cloud Run

## Usage

Note that the following inputs map directly to the [google-github-actions/deploy-cloudrun inputs](https://github.com/google-github-actions/deploy-cloudrun#inputs):

- `env-vars`
- `flags`
- `region`
- `service`
- `mounted-secrets`*

_\* doesn't map directly_

Note that the following inputs map directly to the [docker/build-push-action](https://github.com/docker/build-push-action#inputs) with a `docker-` prefix:

```yml
name: Push Events

on:
  push:
    branches:
      - dev
      - main

permissions:
  contents: write
  id-token: write
  deployments: write
  pull-requests: write

concurrency:
  group: ${{ github.workflow }}-${{ github.ref }}
  cancel-in-progress: true

jobs:
  release:
    name: Create release
    runs-on: ubuntu-latest
    outputs:
      release_created: ${{ steps.release.outputs.release_created }}

    steps:
      - name: 🚀 Create Release
        id: release
        uses: agrc/release-composite-action@v1
        with:
          prerelease: ${{ github.ref_name == 'dev' }}
          repo-token: ${{ secrets.GITHUB_TOKEN }}
          github-app-id: ${{ secrets.UGRC_RELEASE_BOT_APP_ID }}
          github-app-key: ${{ secrets.UGRC_RELEASE_BOT_APP_KEY }}
          github-app-name: ${{ secrets.UGRC_RELEASE_BOT_NAME }}
          github-app-email: ${{ secrets.UGRC_RELEASE_BOT_EMAIL }}
          
  deploy-dev:
    name: Deploy to staging
    runs-on: ubuntu-latest
    needs: release
    environment:
      name: dev
    if: github.ref_name == 'dev' && needs.release.outputs.release_created

    steps:
      - name: 🚀 Deploy
        uses: agrc/cloud-run-docker-deploy-composite-action@v1
        with:
          identity-provider: ${{ secrets.IDENTITY_PROVIDER }}
          service-account-email: ${{ secrets.SERVICE_ACCOUNT_EMAIL }}
          project-id: ${{ secrets.PROJECT_ID }}
          service: printproxy
          flags: |
            --service-account=cloud-run-sa@${{ secrets.PROJECT_ID }}.iam.gserviceaccount.com
            --allow-unauthenticated
          env-vars: |
            OPEN_QUAD_WORD=${{ secrets.OPEN_QUAD_WORD }}
            ANOTHER_VAR=example
          service-now-instance: ${{ secrets.SN_INSTANCE }}
          service-now-table: ${{ secrets.SN_TABLE }}
          service-now-system-id: ${{ secrets.SN_SYS_ID }}
          service-now-username: ${{ secrets.SN_USERNAME }}
          service-now-password: ${{ secrets.SN_PASSWORD }}
          repo-token: ${{ secrets.GITHUB_TOKEN }}
```
