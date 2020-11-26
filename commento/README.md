# commento

![Version: 0.1.0](https://img.shields.io/badge/Version-0.1.0-informational?style=flat-square) ![AppVersion: 1.0](https://img.shields.io/badge/AppVersion-1.0-informational?style=flat-square)

A Helm chart to deploy Commento.io

**Homepage:** <https://github.com/duyet/charts/tree/master/commento>

## Maintainers

| Name | Email | Url |
| ---- | ------ | --- |
| duyet | me@duyet.net | https://github.com/duyet/ |

## Requirements

| Repository | Name | Version |
|------------|------|---------|
| https://charts.bitnami.com/bitnami | postgresql | 9.3.3 |

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| affinity | object | `{}` |  |
| akismetKey | string | `nil` | Akismet API key. Create a key in your Akismet dashboard <https://akismet.com/account/>. By default, Akismet integration is turned off when this value is left empty. |
| cdn.cdnPrefix | string | `nil` | CDN Prefix, e.g. cdnPrefix: http://d111111abcdef8.cloudfront.net |
| cdn.enabled | bool | `false` | Enable CDN. Useful if you'd like to use a CDN with Commento |
| dashboardRegistration | bool | `true` | Used to disable new dashboard registrations |
| existingSecret | string | `nil` | Existing secret to use for PostgreSQL passwords |
| extraEnvs | object | [] | Extra environments |
| githubOAuth.enabled | bool | `false` | GitHub OAuth configuration. Create a new OAuth app in GitHub developer settings to generate a set of credentials: https://github.com/settings/developers |
| githubOAuth.key | string | `nil` |  |
| githubOAuth.secret | string | `nil` |  |
| gitlabOAuth.enabled | bool | `false` | Gitlab OAuth configuration. Create a new application in your GitLab settings to generate a set of credentials: https://gitlab.com/profile/applications |
| gitlabOAuth.key | string | `nil` |  |
| gitlabOAuth.secret | string | `nil` |  |
| googleOAuth.enabled | bool | `false` | Google OAuth configuration Create a new project in the Google developer console to generate a set of credentials: https://console.developers.google.com/project |
| googleOAuth.key | string | `nil` |  |
| googleOAuth.secret | string | `nil` |  |
| image.pullPolicy | string | `"IfNotPresent"` |  |
| image.repository | string | `"registry.gitlab.com/commento/commento"` | The image of the commento container. |
| image.tag | string | `"v1.8.0"` | The image tag. |
| ingress.annotations | object | `{}` |  |
| ingress.enabled | bool | `false` |  |
| ingress.hosts[0].host | string | `"chart-example.local"` |  |
| ingress.hosts[0].paths | list | `[]` |  |
| ingress.tls | list | `[]` |  |
| nodeSelector | object | `{}` |  |
| originUrl | string | `""` | COMMENTO_ORIGIN This should be set to the subdomain or the IP address hosting Commento All API requests will go to this server. This may include subdirectories if Commento is hosted behind a reverse proxy, for example. Include the protocol in the value to use HTTP/HTTPS. E.g. http://commento.example.com |
| podAnnotations | string | `nil` | K8S Pod annotations |
| postgresql.enabled | bool | `true` | Enable postgresql |
| postgresql.existingSecret | string | `nil` | This existing secret to use for PostgreSQL passwords |
| postgresql.extraEnv | list | `[]` | Extra envs for postgres |
| postgresql.extraEnvVarsCM | string | `nil` | Extra env configmap for postgres |
| postgresql.persistence.enabled | bool | `false` |  |
| postgresql.postgresqlDatabase | string | `"commento"` | Postgres database name |
| postgresql.postgresqlPassword | string | `"commento"` | Postgres password WARNING: you should NOT use this, instead specify `postgresql.existingSecret` |
| postgresql.postgresqlUsername | string | `"postgres"` | Postgres username |
| postgresql.replication.enabled | bool | `false` | Enable Postgres persistence |
| postgresql.resources | object | Memory: `256Mi`, CPU: `250m` | CPU/Memory resource requests/limits |
| postgresql.volumePermissions.enabled | bool | `false` | Enable Postgres volumn permissions |
| resources | object | "" | Pod resources |
| service.port | int | `8080` |  |
| service.type | string | `"ClusterIP"` |  |
| smtp | object | see below | SMTP credentials and configuration the server should use to send emails. By default, all settings are empty and email features such as email notification and reset password are turned off. |
| smtp.fromAddress | string | `nil` | SMTP fromAddress |
| smtp.host | string | `nil` | SMTP Host |
| smtp.password | string | `nil` | SMTP password |
| smtp.port | int | `nil` | SMTP Port |
| smtp.username | string | `nil` | SMTP user |
| tolerations | object | `{}` |  |
| twitterOAuth.enabled | bool | `false` | Twitter OAuth configuration. Create an app in the Twitter developer dashboard to generate a set of credentials: https://developer.twitter.com/en/apps |
| twitterOAuth.key | string | `nil` |  |
| twitterOAuth.secret | string | `nil` |  |