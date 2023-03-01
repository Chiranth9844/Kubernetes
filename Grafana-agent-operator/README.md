Deploying Grafana agent operator in kubernetes cluster by deploying above files using `kubectl apply -f [file-name]` in the order as given below
- GrafanaAgent.yaml
- MetricsInstance.yaml
- basicAuth.yaml
- ServiceMonitor.yaml
- cAdvisor.yaml
- LogsInstance.yaml
- LogInstance-secret.yaml
- PodLogs.yaml
<img width="622" alt="image" src="https://user-images.githubusercontent.com/53873995/222121978-59be7717-38bb-40b8-a6f6-4f63023ab9fb.png">
