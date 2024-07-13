# Helm 3 Commands Part 1

1. **Creating a Helm Chart:**
    ```bash
    helm create microservice-one
    ```
    **Explanation:** This command generates a new Helm chart named `microservice-one`. It creates the necessary directory structure and template files to define your Kubernetes application.

2. **Installing a Helm Chart:**
    ```bash
    helm install ms-one microservice-one
    ```
    **Explanation:** This command installs the Helm chart `microservice-one` with the release name `ms-one` into your Kubernetes cluster. It deploys the application defined in the Helm chart.

3. **Listing Installed Helm Releases:**
    ```bash
    helm list
    ```
    **Explanation:** This command lists all the Helm releases currently deployed in your Kubernetes cluster. It displays the release names, chart names, namespaces, and statuses.

4. **Checking the Status of a Release:**
    ```bash
    helm status ms-one
    ```
    **Explanation:** This command shows the status of the Helm release `ms-one`. It provides details about the deployed resources, their current status, and any related notes or outputs.

5. **Viewing the History of a Release:**
    ```bash
    helm history ms-one
    ```
    **Explanation:** This command displays the deployment history of the Helm release `ms-one`, including all revisions. It shows when each revision was deployed and their statuses.

6. **Upgrading a Helm Release:**
    ```bash
    helm upgrade ms-one microservice-one
    ```
    **Explanation:** This command upgrades the Helm release `ms-one` to the latest version of the `microservice-one` chart. It applies any changes or updates made to the Helm chart or its values.

7. **Helm Rollback: Reverting Changes in Chart Deployment:**
    ```bash
    helm rollback ms-one 1
    ```
    **Explanation:** This command rolls back the Helm release `ms-one` to revision `1`. It reverts the deployment to the state it was in after the first deployment, useful for undoing problematic updates.

8. **Uninstalling a Helm Release:**
    ```bash
    helm uninstall ms-one
    ```
    **Explanation:** This command uninstalls the Helm release `ms-one` from the Kubernetes cluster. It removes all resources associated with the release, effectively deleting the deployed application.
