# Helm Overview

## What is Helm?
Helm is a package manager for Kubernetes, enabling streamlined application deployment and management using charts.

## Why do we require Helm?
Helm simplifies Kubernetes deployment by packaging applications and their dependencies into charts, facilitating easy installation, upgrades, and management.

---

# Helm Usage

## Without and With Helm Chart
- **Without Helm**: Manual creation and management of Kubernetes YAML manifests for each resource.
- **With Helm Chart**: Applications are packaged into reusable Helm charts, including templates for Kubernetes manifests, values files, and metadata.

## Difference between Helm 2 and Helm 3
- **Helm 2**:
  - Uses Tiller (server-side component) for managing releases.
  - Centralized chart repository.
  - Initialization (`helm init`) required.
  - Security concerns related to Tiller.
  
- **Helm 3**:
  - No Tiller; client-only architecture.
  - Charts stored locally or in repositories.
  - Simplified installation and enhanced security.
  - Improved namespace isolation.

---

# Helm Chart Structure

A Helm chart consists of:

- **Chart.yaml**: Metadata about the chart.
- **Templates/**: Directory for Kubernetes manifest templates.
- **Values.yaml**: Default configuration values.
- **Charts/**: Dependency charts (if any).
- **README.md**: Documentation for the chart.

---

# Installation

## Installation of Helm 2

### Linux
```bash
curl https://raw.githubusercontent.com/helm/helm/master/scripts/get-helm-2 | bash
```
# Installing Helm on Windows

## Prerequisites
Before installing Helm on Windows, ensure you have the following prerequisites:
- **Windows Operating System**: Helm supports installation on Windows.
- **PowerShell**: Use PowerShell for executing commands.

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
