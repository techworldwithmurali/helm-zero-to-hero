# Helm Overview

Helm is a package manager for Kubernetes, designed to simplify the process of installing and managing applications on Kubernetes clusters.

## Helm 2 (Helm Classic)

Helm 2, also known as Helm Classic, was the previous major version of Helm. It operated with a client-server architecture:

- **Client**: The Helm client (`helm`) interacts with the Kubernetes cluster.
- **Server**: Tiller, the server component, runs inside the Kubernetes cluster.

Helm 2 was widely used until Helm 3 was released in 2019.

## Helm 2 Commands

### helm version
Displays the Helm client and server versions.
```bash
helm version
```

### helm init
Initializes Helm on both client and server. Note: Helm 2 is deprecated, consider using Helm 3.
```bash
helm init
```

### helm create
Creates a new Helm chart structure.
```bash
helm create mychart
```

### helm install
Installs a chart onto the Kubernetes cluster.
```bash
helm install my-release ./mychart
```

### helm list
Lists all releases deployed to the cluster.
```bash
helm list
```

### helm status
Displays the status of a deployed release.
```bash
helm status my-release
```

### helm upgrade
Upgrades a release to a new version of a chart.
```bash
helm upgrade my-release ./mychart
```

### helm rollback
Rolls back a release to a previous revision.
```bash
helm rollback my-release 1
```

### helm history
Shows the revision history of a release.
```bash
helm history my-release
```

### helm inspect
Shows detailed information about a chart.
```bash
helm inspect mychart
```

### helm delete
Deletes a named release.
```bash
helm delete my-release
```

Note: Helm 2 is deprecated; it's recommended to use Helm 3 for new projects and migrate existing Helm 2 setups to Helm 3.
