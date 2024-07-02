## Helm 2 Commands

### helm get
Retrieves information about a named release.
```bash
helm get my-release
```

### helm template
Generates Kubernetes manifest files from a Helm chart, but does not install anything.
```bash
helm template ./mychart
```

### helm verify
Verifies that a chart at the given path has been signed and can be trusted.
```bash
helm verify ./mychart
```

### helm dependency
Manages chart dependencies.
```bash
helm dependency update ./mychart
```

### helm lint
Checks a chart for possible issues.
```bash
helm lint ./mychart
```

### helm repo
Manages Helm chart repositories.
```bash
helm repo add stable https://charts.helm.sh/stable
helm repo update
helm repo list
helm repo remove stable
```
