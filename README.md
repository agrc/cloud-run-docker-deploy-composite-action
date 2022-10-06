# Cloud Run Docker Deploy Composite Action

A GitHub Action that builds and deploys a docker image to GCP Cloud Run

## Usage

Note that the following inputs map directly to the [google-github-actions/deploy-cloudrun inputs](https://github.com/google-github-actions/deploy-cloudrun#inputs):

* `env-vars`
* `flags`
* `region`
* `service`

```yml
  deploy-dev:
    name: Deploy to staging
    runs-on: ubuntu-latest
    needs: release
    environment:
      name: dev
    if: github.ref_name == 'dev' && needs.release.outputs.release_created

    steps:
      - name: 🚀 Deploy
        uses: agrc/cloud-run-docker-deploy-composite-action@dev
        with:
          identity-provider: secrets.IDENTITY_PROVIDER
          service-account-email: secrets.SERVICE_ACCOUNT_EMAIL
          project-id: secrets.PROJECT_ID
          service: printproxy
          flags: |
            --service-account=cloud-run-sa@${{ secrets.PROJECT_ID }}.iam.gserviceaccount.com
            --allow-unauthenticated
          env-vars: 'OPEN_QUAD_WORD=${{ secrets.OPEN_QUAD_WORD }}'
          service-now-instance: secrets.SN_INSTANCE
          service-now-table: secrets.SN_TABLE
          service-now-system-id: secrets.SN_SYS_ID
          service-now-username: secrets.SN_USERNAME
          service-now-password: secrets.SN_PASSWORD
```
