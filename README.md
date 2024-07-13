# Helm Overview

Helm is a package manager for Kubernetes, designed to simplify the process of installing and managing applications on Kubernetes clusters.

## Helm 2 (Helm Classic)

Helm 2, also known as Helm Classic, was the previous major version of Helm. It operated with a client-server architecture:

- **Client**: The Helm client (`helm`) interacts with the Kubernetes cluster.
- **Server**: Tiller, the server component, runs inside the Kubernetes cluster.

Helm 2 was widely used until Helm 3 was released in 2019.

## Helm 2 Commands

1. **`helm version`**
   - Displays the version of Helm client and server.

   **Example:**
   ```bash
   helm version
   ```

2. **`helm init`**
   - Initializes Helm on both client and server. This command installs Tiller (Helm's server-side component) into your Kubernetes cluster.

   **Example:**
   ```bash
   helm init
   ```

3. **`helm create`**
   - Creates a new chart with the given name.

   **Example:**
   ```bash
   helm create microservice-one
   ```

4. **`helm install`**
   - Installs a chart into your Kubernetes cluster.

   **Example:**
   ```bash
   helm install microservice-one
   ```

5. **`helm list`**
   - Lists releases of deployed charts.

   **Example:**
   ```bash
   helm list
   ```

6. **`helm status`**
   - Displays the status of a named release.

   **Example:**
   ```bash
   helm status ms-one
   ```

7. **`helm upgrade`**
   - Upgrades a release to a new version of a chart.

   **Example:**
   ```bash
   helm upgrade ms-one microservice-one
   ```

8. **`helm rollback`**
   - Rolls back a release to a previous revision.

   **Example:**
   ```bash
   helm rollback ms-one 1
   ```

9. **`helm history`**
   - Displays the history of revisions for a release.

   **Example:**
   ```bash
   helm history ms-one
   ```

10. **`helm inspect`**
    - Inspects a chart by rendering its templates.

    **Example:**
    ```bash
    helm inspect values microservice-one
    ```

11. **`helm delete`**
    - Deletes a named release.

    **Example:**
    ```bash
    helm delete ms-one
    ```
