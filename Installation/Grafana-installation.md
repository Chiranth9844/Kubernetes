
# GRAFANA

## Steps to setup Grafana - locally

1. `brew install grafana`
2. `brew services start grafana`
3. Start prometheus service<br/> 
    `minikube service prometheus-server-ext`<br/>  
    ![Screenshot 2023-02-26 at 5 24 31 PM](https://user-images.githubusercontent.com/53873995/221409159-e99da7dd-f39a-408a-8a3d-0eb73a27d76a.png)<br/>
    the url (ip adress) changes every time when we restart 
4. go to localhost:3000 (grafana) and login 
5. go to settings -> configuration -> data source  and select prometheu 
    ![Screenshot 2023-02-26 at 5 43 57 PM](https://user-images.githubusercontent.com/53873995/221409950-2386967a-b3ea-41ec-9ad9-ae2da32b71af.png)
6. Type the url in it
    ![image](https://user-images.githubusercontent.com/53873995/221410247-30a4c6fa-7a7a-422a-a5d8-641194750a0b.png)
7. Open dashboard and select any one of the imported dashboards 
    ![image](https://user-images.githubusercontent.com/53873995/221410392-879372e5-f5a5-41da-9ddd-6af480f4dec1.png)
    ![image](https://user-images.githubusercontent.com/53873995/221410474-ba0101e9-d256-4dfb-af1d-6995b98af4dd.png)



## Steps to setup Grafana - inside k8s cluster

1. Add repo<br/> 
    `helm repo add grafana https://grafana.github.io/helm-charts`
2. Update the repo <br/> 
    `helm repo update`
3. Install grafana <br/> 
    `helm install my-release grafana/grafana-agent-operator` available here https://grafana.com/docs/agent/latest/operator/helm-getting-started/
    New service will be added after this in my case new service name is kubelet
    <img width="953" alt="image" src="https://user-images.githubusercontent.com/53873995/221383322-398f056a-a8b4-4b76-8c76-9040ba0266b2.png"> 

4. Check the list of helm releases <br/> `helm list`
5. To access the grafana instance from outside so we need to get pods<br/> 
    `kubectl get deployment` <br/>
    `kubectl get pods` <br/>
    `kubectl logs [grafana pod name]`  Eg : `kubectl log `
6. 
