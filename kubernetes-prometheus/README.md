# kubernetes-prometheus
Configuration files for setting up prometheus monitoring on Kubernetes cluster.

You can find the full tutorial from here https://devopscube.com/setup-prometheus-monitoring-on-kubernetes/

git clone https://github.com/bibinwilson/kubernetes-prometheus
cd kubernetes-prometheus
kubectl create namespace monitoring

kubectl create -f clusterRole.yaml

kubectl create -f config-map.yaml

kubectl create  -f prometheus-deployment.yaml 
kubectl get deployments --namespace=monitoring
kubectl get pods --namespace=monitoring
kubectl port-forward prometheus-monitoring-<variable> 8080:9090 -n monitoring
kubectl create -f prometheus-service.yaml --namespace=monitoring

open prom dashboard

git clone https://github.com/devopscube/kube-state-metrics-configs.git

kubectl apply -f kube-state-metrics-configs/
Step 3: Check the deployment status using the following command.

kubectl get deployments kube-state-metrics -n kube-system



kubectl create -f AlertManagerConfigmap.yaml
kubectl create -f AlertTemplateConfigMap.yaml
kubectl create -f Deployment.yaml
kubectl create -f Service.yaml

Setup Grafana On Kubernetes

kubectl create -f grafana-datasource-config.yaml
kubectl create -f deployment.yaml

