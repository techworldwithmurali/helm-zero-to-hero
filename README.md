## Helm 3 Commands
# helm create
helm create: Creates a new Helm chart structure. For example:

helm create microservice-one
# helm install 
helm install: Installs a chart onto the Kubernetes cluster. For example:

helm install my-app ./microservice-one
# helm list

helm list: Lists all releases deployed to the cluster. For example:

helm list
# helm status

helm status: Displays the status of a deployed release. For example:

helm status my-app

# helm history
helm history: Shows the revision history of a release. For example:

helm history my-app
# helm upgrade

helm upgrade: Upgrades a release to a new version of a chart. For example:



helm upgrade my-app ./microservice-one
# helm rollback
helm rollback: Rolls back a release to a previous revision. For example:

helm rollback my-app 1
# helm uninstall

helm uninstall: Uninstalls a release from the cluster. For example:



helm uninstall my-app
