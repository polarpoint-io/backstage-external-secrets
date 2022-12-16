# backstage-external-secrets

![Version: 1.0.0](https://img.shields.io/badge/Version-1.0.0-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 1.0.0](https://img.shields.io/badge/AppVersion-1.0.0-informational?style=flat-square)

Creation of Kubernetes secrets from Secrets backends for Backstage

## Prerequisites

- Helm v3.10.2+
- External-secrets-operator

## Usage

Charts are available in the following formats:

* [Chart Repository](https://helm.sh/docs/topics/chart_repository/)
* [OCI Artifacts](https://helm.sh/docs/topics/registries/)

### Installing from the Chart Repository

The following command can be used to add the chart repository:

```console
helm repo add bitnami https://charts.bitnami.com/bitnami
helm repo add external-secrets https://charts.external-secrets.io
helm repo add backstage https://backstage.github.io/charts
```

Once the chart has been added, install one of the available charts:

```console
helm upgrade -i <release_name> backstage/backstage-external-secrets
```

### Installing from an OCI Registry

Charts are also available in OCI format. The list of available charts can be found [here](https://github.com/orgs/polarpoint-io/packages?repo_name=charts).

Install one of the available charts:

```shell
helm upgrade -i <release_name> oci://ghcr.io/backstage/charts/backstage-external-secrets --version=<version>
```

## Backstage Chart

More information can be found by inspecting the [backstage chart](charts/backstage).

## Requirements

| Repository | Name | Version |
|------------|------|---------|
| https://charts.external-secrets.io | external-secrets | 0.7.0 |

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| externalSecrets[0].data[0].remoteRefKey | string | `"github-client-id"` |  |
| externalSecrets[0].data[0].secretKey | string | `"AUTH_GITHUB_CLIENT_ID"` |  |
| externalSecrets[0].data[1].remoteRefkey | string | `"github-client-secret"` |  |
| externalSecrets[0].data[1].secretKey | string | `"AUTH_GITHUB_CLIENT_SECRET"` |  |
| externalSecrets[0].data[2].remoteRefkey | string | `"github-token"` |  |
| externalSecrets[0].data[2].secretKey | string | `"GITHUB_TOKEN"` |  |
| externalSecrets[0].name | string | `"backstage-github-authentication"` |  |
| externalSecrets[0].namespace | string | `"platform"` |  |
| externalSecrets[0].targetSecretName | string | `"backstage-github-authentication"` |  |
| externalSecrets[1].data[0].remoteRefkey | string | `"kubernetes-tooling-token"` |  |
| externalSecrets[1].data[0].secretKey | string | `"K8S_TOKEN"` |  |
| externalSecrets[1].data[1].remoteRefkey | string | `"kubernetes-tooling-token-url"` |  |
| externalSecrets[1].data[1].secretKey | string | `"K8S_URL"` |  |
| externalSecrets[1].name | string | `"backstage-kubernetes-authentication"` |  |
| externalSecrets[1].namespace | string | `"platform"` |  |
| externalSecrets[1].targetSecretName | string | `"backstage-kubernetes-authentication"` |  |
| externalSecrets[2].data[0].remoteRefkey | string | `"backstage-postgres-user"` |  |
| externalSecrets[2].data[0].secretKey | string | `"POSTGRES_USER"` |  |
| externalSecrets[2].data[1].remoteRefkey | string | `"backstage-postgres-password"` |  |
| externalSecrets[2].data[1].secretKey | string | `"POSTGRES_PASSWORD"` |  |
| externalSecrets[2].data[2].remoteRefkey | string | `"backstage-postgres-port"` |  |
| externalSecrets[2].data[2].secretKey | string | `"POSTGRES_PORT"` |  |
| externalSecrets[2].name | string | `"backstage-database-authentication"` |  |
| externalSecrets[2].namespace | string | `"platform"` |  |
| externalSecrets[2].targetSecretName | string | `"backstage-database-authentication"` |  |
| global.clusterSecretStore | string | `"cluster-secrets-store"` |  |
| global.refreshInterval | string | `"24h0m0s"` |  |

## Maintainers

| Name | Email | Url |
| ---- | ------ | --- |
| bainss | surj@polarpoint.io |  |
