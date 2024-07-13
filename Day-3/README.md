## Helm 3 Commands Part 2

### `helm get`
- **Subcommands:**
  - `hooks`: Get hooks for a release.
  - `manifest`: Get the manifest for a named release.
  - `notes`: Get the notes for a release.
  - `values`: Get the values that were used to install a release.
  
  **Example:**
  ```bash
  helm get manifest my-release
  ```
  This command retrieves the manifest (YAML definition) of the resources deployed by the release named `my-release`.

### `helm show`
- **Subcommands:**
  - `all`: Show all information of a chart.
  - `chart`: Show the chart definition.
  - `readme`: Show the README file of a chart.
  
  **Example:**
  ```bash
  helm show readme stable/mysql
  ```
  This command displays the README of the `stable/mysql` chart.

### `helm env`
- **Subcommands:**
  - `subst`: Substitutes environment variables in Helm manifests.
  
  **Example:**
  ```bash
  helm env subst mychart/
  ```
  This command substitutes environment variables in the Helm manifests found in the `mychart/` directory.

### `helm template`
- **Subcommands:**
  - N/A (No subcommands for `helm template`)

  **Example:**
  ```bash
  helm template my-release stable/mysql
  ```
  This command renders the Helm chart `stable/mysql` into Kubernetes YAML manifests and prints the result to stdout.

### `helm lint`
- **Subcommands:**
  - N/A (No subcommands for `helm lint`)

  **Example:**
  ```bash
  helm lint mychart/
  ```
  This command checks the syntax of the Helm chart `mychart/` for possible issues.

### `helm package`
- **Subcommands:**
  - N/A (No subcommands for `helm package`)

  **Example:**
  ```bash
  helm package mychart/
  ```
  This command packages the Helm chart `mychart/` into a versioned chart archive file (`mychart-1.2.3.tgz`).

### `helm dependency`
- **Subcommands:**
  - `build`: Rebuild the charts/ directory based on the Chart.lock file.
  - `list`: List the dependencies for the given chart.
  - `update`: Update charts/ based on the contents of Chart.yaml.

  **Example:**
  ```bash
  helm dependency build mychart/
  ```
  This command rebuilds the `charts/` directory for the Helm chart `mychart/` based on the `Chart.lock` file.

### `helm repo`
- **Subcommands:**
  - `add`: Add a chart repository.
  - `index`: Generate an index file given a directory containing packaged charts.
  - `list`: List chart repositories.
  - `remove`: Remove one or more chart repositories.
  - `update`: Update information of available charts locally from chart repositories.

  **Example:**
  ```bash
  helm repo list
  ```
  This command lists all the added chart repositories.

### `helm search`
- **Subcommands:**
  - `hub`: Search for charts in the Artifact Hub or your own hub instance.
  - `repo`: Search repositories for a keyword in charts.

  **Example:**
  ```bash
  helm search hub wordpress
  ```
  This command searches for charts related to `wordpress` in the Artifact Hub.

### `helm plugin`
- **Subcommands:**
  - `install`: Install one or more Helm plugins.
  - `list`: List installed Helm plugins.
  - `uninstall`: Uninstall one or more Helm plugins.
  - `update`: Update one or more Helm plugins.

  **Example:**
  ```bash
  helm plugin list
  ```
  This command lists all installed Helm plugins.

### `helm completion`
- **Subcommands:**
  - N/A (No subcommands for `helm completion`)

  **Example:**
  ```bash
  helm completion bash
  ```
  This command generates the Bash completion script for Helm.
