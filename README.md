# Kubernetes

# KUBERNETE Basic Commands

> For detailed explination refer https://kubernetes.io/docs/reference/generated/kubectl/kubectl-commands#-strong-getting-started-strong- <hr>
> `NOTE :` -h (help) option at the end of the command gets us the details

## Status check
* Get status of nodes<br/>`kubectl get nodes`<br/>
* Get status of pods<br/>`kubectl get pod`<br/>
* Get status of services<br/>`kubectl get services`<br/>
* Get status of replicaset<br/>`kubectl get replicaset `<br/>
* get All status at once <br/>`kubectl get all`<br/><hr/>

## Deployment
* Create the deployment<br/>
  - `kubectl create deployment NAME --image=image [--dry-run] [options]`
  - Eg: `kubectl create deployment mongo --image=mongo --dry-run=client -oyaml > mongo.yaml`<br/>
    [this creates the yaml file and saves it]
  - `kubectl apply -f [file name] `
* Update the deployment<br/>
  - `kubectl edit deployment [name]`
  - `kubectl apply -f [file name]`<br/>
* Delete the deployment<br/>
  `$ kubectl delete ([-f FILENAME] | [-k DIRECTORY] | TYPE [(NAME | -l label | --all)])`
  - `kubectl delete deployment [deployment name]`
  - `kubectl delete -f [deployment name]`<br/>
  <hr>

## Debug
* debugging pod commands<br/>
  - `kubectl logs [pod name]` (log to console)<br/>
  - `kubectl describe pod [pod name]` (get info about pod)<br/>
  - `kubectl exec -it [pod name] -- bin/bash` (get interactive terminal)<br/>
  <hr>

* to get the status file <br/> `kubectl get deployment [deployment name] -o yaml`<br/>

## Service
* Create a service
  - `$ kubectl expose (-f FILENAME | TYPE NAME) [--port=port] [--protocol=TCP|UDP|SCTP] [--target-port=number-or-name] [--name=name] [--external-ip=external-ip-of-service] [--type=type]`<br/>
    Eg : `kubectl expose deployment example --port=8765 --target-port=9376 \ --name=example-service --type=LoadBalancer`<br/>
  
## port forward(for my reference)

- `kubectl port-forward deployment/prometheus-grafana -n mysql 3000`
- `kubectl port-forward svc/prometheus-operated -n mysql 9090:9090`
- verifying mysql metrics <br/>
  `kubectl port-forward pod/<mysql-pod-name> 9104:9104`

## update exsisting helm parameters
- `helm upgrade bitnami/mysql -n mysql --set metrics.enabled=true --reuse-values`
