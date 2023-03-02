1. helm install mysql bitnami/mysql -n mysql --set auth.rootPassword=password --set auth.username=user --set auth.password=password
2. helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
3. helm upgrade mysql bitnami/mysql -n mysql --set metrics.enabled=true --reuse-values
4. kubectl port-forward pod/mysql-0 9104:9104 -n mysql
5. <img width="1109" alt="image" src="https://user-images.githubusercontent.com/53873995/222415891-e54efff7-e5c8-49be-a719-7f22bd51c463.png">
