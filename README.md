## Deploy a sample application using Helm 2
To deploy a sample application using Helm 2, you'll need to have a Helm chart ready that defines your application's deployment configuration. Here’s a basic example assuming you have a Helm chart prepared:

1. **Prepare Your Helm Chart:**
   - Ensure your Helm chart (`Chart.yaml`, `values.yaml`, and `templates/` directory) is set up correctly. You can create one using `helm create` command as shown earlier.

2. **Initialize Helm (if not already done):**
   - If you haven't initialized Helm yet, you can do so with:
     ```bash
     helm init
     ```

3. **Install the Helm Chart:**
   - Assuming your Helm chart is named `sample-chart` and is located in the current directory, install it using:
     ```bash
     helm install my-app ./sample-chart
     ```
   - Here, `my-app` is the release name for your application. Replace `sample-chart` with the actual path to your Helm chart if it's located elsewhere.

4. **Verify Deployment:**
   - Check the status of your deployed release to ensure everything is running smoothly:
     ```bash
     helm status my-app
     ```

5. **Access the Application:**
   - Depending on your application, access it through a service exposed via Kubernetes. You can find service details using `kubectl get svc` if your chart exposes services.

6. **Manage Application Lifecycle:**
   - Use Helm commands to manage your application's lifecycle as needed:
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
       helm delete my-app
       ```
