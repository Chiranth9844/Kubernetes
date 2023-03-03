# PROMETHEUS

We need kinikube, kubectl and helm pre-installed to setup prometheus

## Install helm with brew
    `brew install helm`

## Steps to setup prometheus

1. clean minikube state
2. Add repo for Prometheus using helm <br/>
    `helm repo add prometheus-community https://prometheus-community.github.io/helm-charts`
3. Update the repo <br/>
    `helm repo update`
4. Install charts <br/>
    `helm install prometheus prometheus-community/kube-prometheus-stack`
5. get the status with <br/>
    `kubectl get all`
6. to see available services<br/>
    `kubctl get service`
7. To access the prometheus instance from outside so we need to create a new service <br/>
    `kubectl expose service prometheus-server --type=NodePort --target-port=9090 --name=prometheus-server-ext` <br/>
    check if service is added with 
    `kubctl get service` <br/>
    <img width="820" alt="image" src="https://user-images.githubusercontent.com/53873995/221382295-12128a92-07a4-400b-bfff-2eb823335d85.png">

8. TO get the url of the server to access it from outside in minikube we have an option<br/>
    `minikube service prometheus-server-ext`  <br/>
    <img width="765" alt="image" src="https://user-images.githubusercontent.com/53873995/221382374-3d4c8f24-8cc5-40d0-8d80-6dd0b6e21505.png">
    <img width="1440" alt="image" src="https://user-images.githubusercontent.com/53873995/221382550-ff795d50-4212-4c23-a9e0-61c751463816.png">
