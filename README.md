## Deploying a Sample Application using Helm 3

### Step 1: Prepare Your Helm Chart

Ensure your Helm chart (`Chart.yaml`, `values.yaml`, and `templates/` directory) is set up correctly. You can create one using the following command:

```bash
helm create sample-chart
```

### Step 2: Install the Helm Chart

Install your Helm chart onto the Kubernetes cluster. Replace `./sample-chart` with the actual path to your Helm chart directory if it's located elsewhere.

```bash
helm install my-app ./sample-chart
```

### Step 3: Verify Deployment

Check the status of your deployed release to ensure everything is running smoothly:

```bash
helm status my-app
```

### Step 4: Access Your Application

Depending on your application, access it through a service exposed via Kubernetes. Use `kubectl get svc` to find service details if your chart exposes services.

### Step 5: Manage Application Lifecycle

Use Helm commands to manage your application's lifecycle as needed:

- **Upgrade** the release:
  ```bash
  helm upgrade my-app ./sample-chart
  ```

- **Rollback** to a previous revision:
  ```bash
  helm rollback my-app 1
  ```

- **Uninstall** the release:
  ```bash
  helm uninstall my-app
  ```
```
