# Helm2 Installation on Windows

## Prerequisites
- EKS cluster is created
- `kubectl` is installed
- Access key and Secret key are set up to connect to the EKS cluster

## Steps to Install Helm

### 1. Download the Installer
- Go to the Helm GitHub releases page: [Helm Releases](https://github.com/helm/helm/releases).
- Download the latest `helm-windows-amd64.zip` file under Assets.

### 2. Extract the Installer
- Navigate to the location where you downloaded `helm-windows-amd64.zip`.
- Right-click on the zip file and select "Extract All...".
- Choose a destination folder or use the default suggested folder.

### 3. Add Helm to PATH
- Open **Control Panel** and go to **System and Security** > **System**.
- Click on **Advanced system settings** on the left.
- In the System Properties window, click on **Environment Variables**.
- In the Environment Variables window, under **System variables**, find the **Path** variable and select it.
- Click **Edit**.
- Click **New** and add the path to the directory where you extracted the `helm.exe` (e.g., `C:\softwares\helm`).
- Click **OK** on all open windows to save the updated PATH.

### 4. Verify Installation
- Open a new instance of PowerShell (or restart if already open).
- Type `helm version` and press Enter.
- If Helm is installed correctly, you should see the client version displayed.
### Step 2: Connect to the EKS cluster
```bash
aws eks update-kubeconfig --name dev-cluster --region us-east-1
```

### Step 3: Create Tiller Service Account & Cluster Role Binding

**service-account.yaml:**
```yaml
apiVersion: v1
kind: ServiceAccount
metadata:
  name: tiller
  namespace: kube-system
```
###### kubectl apply -f service-account.yaml

**ClusterRoleBinding.yaml:**
```yaml
apiVersion: rbac.authorization.k8s.io/v1
kind: ClusterRoleBinding
metadata:
  name: tiller
roleRef:
  apiGroup: rbac.authorization.k8s.io
  kind: ClusterRole
  name: cluster-admin
subjects:
  - kind: ServiceAccount
    name: tiller
    namespace: kube-system
```
###### kubectl apply -f ClusterRoleBinding.yaml

### Step 4: Deploy Tiller and Initialize Helm
```bash
helm init --service-account=tiller --stable-repo-url=https://charts.helm.sh/stable --upgrade --automount-service-account-token=true --replicas=1 --history-max=100 --wait
```

### Step 5: Verify Tiller is installed properly
```bash
helm version
```
