# Installing Helm 3 on Windows

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
