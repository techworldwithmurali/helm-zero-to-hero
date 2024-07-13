## Helm 3 Commands Part 1
### helm create
**helm create:** Creates a new Helm chart structure. 
For example:
```bash
helm create microservice-one
```
### helm install 
**helm install:** Installs a chart onto the Kubernetes cluster. For example:
```bash
helm install my-app ./microservice-one
```
### helm list

**helm list:** Lists all releases deployed to the cluster. For example:
```bash
helm list
```
### helm status

**helm status:** Displays the status of a deployed release. For example:
```bash
helm status my-app
```

### helm history
**helm history:** Shows the revision history of a release. For example:
```bash
helm history my-app
```
### helm upgrade

**helm upgrade:** Upgrades a release to a new version of a chart. For example:
```bash
helm upgrade my-app ./microservice-one
```

### helm rollback
**helm rollback:** Rolls back a release to a previous revision. For example:
```bash
helm rollback my-app 1
```
### helm uninstall

**helm uninstall:** Uninstalls a release from the cluster. For example:
```bash
helm uninstall my-app
```
