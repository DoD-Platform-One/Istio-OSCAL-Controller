<!-- Warning: Do not manually edit this file. See notes on gluon + helm-docs at the end of this file for more information. -->
# oscal-controller

![Version: 0.0.3-bb.1](https://img.shields.io/badge/Version-0.0.3--bb.1-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 0.0.3](https://img.shields.io/badge/AppVersion-0.0.3-informational?style=flat-square) ![Maintenance Track: bb_maintained](https://img.shields.io/badge/Maintenance_Track-bb_maintained-yellow?style=flat-square)

A Helm chart for OSCAL Controller

## Upstream Release Notes

This package has no upstream release note links on file. Please add some to [chart/Chart.yaml](chart/Chart.yaml) under `annotations.bigbang.dev/upstreamReleaseNotesMarkdown`.
Example:
```yaml
annotations:
  bigbang.dev/upstreamReleaseNotesMarkdown: |
    - [Find our upstream chart's CHANGELOG here](https://link-goes-here/CHANGELOG.md)
    - [and our upstream application release notes here](https://another-link-here/RELEASE_NOTES.md)
```

## Learn More

- [Application Overview](docs/overview.md)
- [Other Documentation](docs/)

## Pre-Requisites

- Kubernetes Cluster deployed
- Kubernetes config installed in `~/.kube/config`
- Helm installed

Install Helm

https://helm.sh/docs/intro/install/

## Deployment

- Clone down the repository
- cd into directory

```bash
helm install oscal-controller chart/
```

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| nameOverride | string | `""` |  |
| fullnameOverride | string | `""` |  |
| image.repository | string | `"registry1.dso.mil/ironbank/tetrate/oscal-controller"` |  |
| image.tag | string | `"0.0.3"` |  |
| image.pullPolicy | string | `"IfNotPresent"` |  |
| imagePullSecrets[0].name | string | `"private-registry"` |  |
| replicaCount | int | `1` |  |
| service.type | string | `"ClusterIP"` |  |
| service.port | int | `8080` |  |
| podAnnotations."prometheus.io/scrape" | string | `"true"` |  |
| podAnnotations."prometheus.io/port" | string | `"8080"` |  |
| exemptedNamespaces[0] | string | `"istio-operator"` |  |
| exemptedNamespaces[1] | string | `"kube-system"` |  |
| exemptedNamespaces[2] | string | `"gmp-public"` |  |
| exemptedNamespaces[3] | string | `"gmp-system"` |  |
| exemptedNamespaces[4] | string | `"kube-public"` |  |
| exemptedNamespaces[5] | string | `"kube-node-lease"` |  |
| exemptedNamespaces[6] | string | `"flux-system"` |  |
| args.logOutputLevel | string | `"controller:debug"` |  |

## Contributing

Please see the [contributing guide](./CONTRIBUTING.md) if you are interested in contributing.

---

_This file is programatically generated using `helm-docs` and some BigBang-specific templates. The `gluon` repository has [instructions for regenerating package READMEs](https://repo1.dso.mil/big-bang/product/packages/gluon/-/blob/master/docs/bb-package-readme.md)._

