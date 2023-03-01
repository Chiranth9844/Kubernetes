# Deploy mysql in K8s cluster

We can deploy above provided files in k8s insted of first 2 steps if in case the links are not working <br/>
Can also refer official page https://kubernetes.io/docs/tasks/run-application/run-single-instance-stateful-application/ <hr>

1. Deploy the PV and PVC of the YAML file: <br/> `kubectl apply -f https://k8s.io/examples/application/mysql/mysql-pv.yaml`
2. Deploy the contents of the YAML file: <br/> `kubectl apply -f https://k8s.io/examples/application/mysql/mysql-deployment.yaml`
3. Display information about the Deployment: <br/> `kubectl describe deployment mysql`
4. List the pods created by the Deployment: <br/> `kubectl get pods -l app=mysql`
5. Inspect the PersistentVolumeClaim: <br/> `kubectl describe pvc mysql-pv-claim`
6. Accessing the MySQL instance: 
    - `kubectl exec --stdin --tty [pod-name] -- /bin/bash`
    - `mysql -p`
    <img width="709" alt="image" src="https://user-images.githubusercontent.com/53873995/222078387-4b5e11ec-b226-4cf4-85a2-53d78de24c05.png">
7. Get out of the bash cmd using `exit` command
