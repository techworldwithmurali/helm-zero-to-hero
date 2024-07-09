# Helm3 Installation in Linux

## Steps:
### 1.1: Download the tar file from the Helm release page:
- Visit [Helm Releases](https://github.com/helm/helm/releases)
- Example direct download link: [helm-v3.15.2-linux-amd64.tar.gz](https://get.helm.sh/helm-v3.15.2-linux-amd64.tar.gz)

### 1.2: Untar the downloaded file:
```bash
tar -xvf helm-v3.15.2-linux-amd64.tar.gz
```

### 1.3: Change the file permissions:
```bash
chmod 777 linux-amd64/helm
```

### 1.4: Move the Helm executable to /usr/local/bin (requires sudo):
```bash
sudo mv linux-amd64/helm /usr/local/bin/helm
```

### 1.5: Verify the Helm version:
```bash
helm version
```
