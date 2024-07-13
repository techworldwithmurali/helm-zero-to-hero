#### INSTRUCTOR DETAILS

|  Information             | Details                                                                      |
|----------------------    |------------------------------------------------------------------------------|
| **Name**                 | Moole Muralidhara Reddy                                                      |
| **Email**                | techworldwithmurali@gmail.com                                                |
| **Website**              | https://www.techworldwithmurali.com               |
| **LinkedIn profile**     | [Moole Muralidhara Reddy](https://www.linkedin.com/in/moole-muralidhara-reddy) |

## Helm 2 Commands

### helm get
Retrieves information about a named release.
```bash
helm get ms-one
```

### helm template
Generates Kubernetes manifest files from a Helm chart, but does not install anything.
```bash
helm template ./microservice-one
```

### helm verify
Verifies that a chart at the given path has been signed and can be trusted.
```bash
helm verify ./microservice-one
```

### helm dependency
Manages chart dependencies.
```bash
helm dependency update ./microservice-one
```

### helm lint
Checks a chart for possible issues.
```bash
helm lint ./microservice-one
```

### helm repo
Manages Helm chart repositories.
```bash
helm repo add stable https://charts.helm.sh/stable
helm repo update
helm repo list
helm repo remove stable
```
