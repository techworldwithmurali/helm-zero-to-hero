# Helm2 Installation on Linux

## Prerequisites
- EKS cluster is created
- `kubectl` is installed
- Access key and Secret key are set up to connect to the EKS cluster

## Steps

### Step 1: Install Helm2
1. **Download the tar file from the release page:**
   - [Helm v2.17.0 Release](https://github.com/helm/helm/releases/tag/v2.17.0)
   - [Helm v2.17.0 tar.gz](https://get.helm.sh/helm-v2.17.0-linux-amd64.tar.gz)
   
2. **Untar the downloaded file:**
   ```bash
   tar -xvf helm-v2.17.0-linux-amd64.tar.gz
   ```

3. **Change the file permission:**
   ```bash
   chmod 777 linux-amd64/helm
   ```

4. **Move the `helm` file to `/usr/local/bin`:**
   ```bash
   sudo mv linux-amd64/helm /usr/local/bin/helm
   ```

5. **Verify the Helm version:**
   ```bash
   helm version
   ```

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
