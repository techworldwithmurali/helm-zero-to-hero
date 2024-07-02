# Helm Commands Cheat Sheet (Part 2)

## helm get
Displays information about a named release. For example:

```bash
helm get manifest my-app
```

## helm show
Shows chart details such as the README, values, or templates. For example:

```bash
helm show readme my-chart
```

## helm env
Displays the Helm client environment information. For example:

```bash
helm env
```

## helm template
Generates Kubernetes YAML from a Helm chart without installing it. For example:

```bash
helm template my-app ./my-chart
```

## helm lint
Checks a chart for possible issues. For example:

```bash
helm lint ./my-chart
```

## helm package
Packages a chart directory into a chart archive (tgz). For example:

```bash
helm package ./my-chart
```

## helm dependency
Manages chart dependencies. For example:

```bash
helm dependency update ./my-chart
```

## helm repo
Manages Helm chart repositories. For example:

```bash
helm repo add stable https://charts.helm.sh/stable
```

## helm search
Searches for Helm charts in repositories. For example:

```bash
helm search repo wordpress
```

## helm plugin
Manages Helm plugins. For example:

```bash
helm plugin list
```

## helm completion
Generates shell completion scripts for Helm commands. For example:

```bash
helm completion bash
```

## helm test
Runs tests defined in a chart. For example:

```bash
helm test my-app
```
