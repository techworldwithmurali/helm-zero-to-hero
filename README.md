To convert Kubernetes YAML files into Helm Chart YAML, follow these steps:

1. **Deployment  YAML in Kubernetes (`deployment.yaml`):**
```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: my-app
  namespace: dev
spec:
  replicas: 3
  selector:
    matchLabels:
      app: my-app
  template:
    metadata:
      labels:
        app: my-app
    spec:
      containers:
      - name: my-app-container
        image: nginx:latest
```
2. **Converted Helm Chart YAML (`templates/deployment.yaml`):**
```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: {{ .Release.Name }}-my-app
  namespace: {{ .Values.namespace }}
spec:
  replicas: {{ .Values.replicaCount }}
  selector:
    matchLabels:
      app: {{ .Release.Name }}-my-app
  template:
    metadata:
      labels:
        app: {{ .Release.Name }}-my-app
    spec:
      containers:
      - name: my-app-container
        image: {{ .Values.image.repository }}:{{ .Values.image.tag }}
```
3. **Converted Helm Chart YAML (`templates/service.yaml`):**
```yaml
apiVersion: v1
kind: Service
metadata:
  name: my-app-service
  namespace: dev
  annotations:
    service.beta.kubernetes.io/aws-load-balancer-subnets: subnet-028dc499437b2b83f,subnet-0f349567f5fec79de
spec:
  selector:
    app: my-app
  ports:
  - protocol: TCP
    port: 80
    targetPort: 80
  type: LoadBalancer

   ```

4. **Converted Helm Chart YAML (`templates/service.yaml`):**
```yaml
apiVersion: v1
kind: Service
metadata:
  name: {{ .Release.Name }}-my-app-service
  namespace: {{ .Values.namespace }}
  annotations:
    service.beta.kubernetes.io/aws-load-balancer-subnets: {{ .Values.service.annotations.loadBalancerSubnets }}
spec:
  selector:
    app: {{ .Release.Name }}-my-app
  ports:
  - protocol: TCP
    port: 80
    targetPort: 80
  type: LoadBalancer
  
   ```

   Replace `.Release.Name`, `.Values.service.port`, and `.Values.service.targetPort` with appropriate values from your Helm chart `values.yaml` file.
   
### Define Values in values.yaml
Edit the values.yaml file in the my-app directory to include the necessary values:

   ```yaml
replicaCount: 3

image:
  repository: nginx
  tag: latest

namespace: dev

service:
  annotations:
    loadBalancerSubnets: "subnet-028dc499437b2b83f,subnet-0f349567f5fec79de"
```
# Passing Environment Variables into a Helm Chart

To pass environment variables into a Helm Chart, define them in your `values.yaml` file and use them in your Kubernetes manifests:

1. **Define variables in `values.yaml`:**
```yaml
replicaCount: 3

image:
  repository: nginx
  tag: latest

namespace: dev

env:
  - name: MY_ENV_VAR1
    value: "value1"
  - name: MY_ENV_VAR2
    value: "value2"

service:
  annotations:
    loadBalancerSubnets: "subnet-028dc499437b2b83f,subnet-0f349567f5fec79de
   ```

2. **Use them in a Deployment manifest (`templates/deployment.yaml`):**
```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: {{ .Release.Name }}-my-app
  namespace: {{ .Values.namespace }}
spec:
  replicas: {{ .Values.replicaCount }}
  selector:
    matchLabels:
      app: {{ .Release.Name }}-my-app
  template:
    metadata:
      labels:
        app: {{ .Release.Name }}-my-app
    spec:
      containers:
      - name: my-app-container
        image: {{ .Values.image.repository }}:{{ .Values.image.tag }}
        env:
          {{- range .Values.env }}
          - name: {{ .name }}
            value: {{ .value | quote }}
          {{- end }}
   ```

   Replace `.Values.env.database.host`, `.Values.env.database.port`, `.Values.env.database.username`, and `.Values.env.database.password` with appropriate values from your Helm chart `values.yaml` file.

# Creating Multiple Values Files within a Helm Chart

To manage multiple sets of configuration values in Helm, use multiple `values-*.yaml` files:

1. **Example `values-dev.yaml`:**
   ```yaml
   replicaCount: 1
   image:
     tag: dev
   ```

2. **Example `values-prod.yaml`:**
   ```yaml
   replicaCount: 3
   image:
     tag: latest
   ```

3. **Install or upgrade with specific values files:**
   ```bash
   helm install my-app ./my-chart --values values-dev.yaml
   ```

   ```bash
   helm upgrade my-app ./my-chart --values values-prod.yaml
   ```

   You can also combine multiple values files:
   ```bash
   helm install my-app ./my-chart --values values.yaml --values values-dev.yaml
   ```

   This approach allows you to manage different configurations for different environments or use cases within your Helm charts effectively.
```
