# kubernetes-prometheus
Configuration files for setting up prometheus monitoring on Kubernetes cluster.


git clone https://github.com/pariwesh06/prom-grafana-java-demo.git

kubectl create namespace monitoring
kubectl apply -f prom-grafana-java-demo/kubernetes-prometheus

kubectl get deployments --namespace=monitoring
kubectl get pods --namespace=monitoring
kubectl port-forward prometheus-deployment-77cb49fb5d-j8qsx 8080:9090 -n monitoring

open prom dashboard


kubectl apply -f prom-grafana-java-demo/kube-state-metrics-configs/

 Check the deployment status using the following command.

kubectl get deployments kube-state-metrics -n kube-system

Alert Manager installation
kubectl apply -f prom-grafana-java-demo/kubernetes-prometheus/alert-config

open on port 31000

Setup Grafana On Kubernetes
kubectl apply -f prom-grafana-java-demo/kubernetes-prometheus/grafana
kubectl create -f grafana-datasource-config.yaml
kubectl create -f deployment.yaml

Access Grafana on http://localhost:32000
8588

container_memory_usage_bytes    
container_memory_failcnt
kube_node_status_capacity
container_cpu_load_average_10s{container="POD", job="kubernetes-cadvisor"}[445m]  

sum(rate(container_cpu_usage_seconds_total{container_name="POD"}[5m])) by (pod_name)  

https://github.com/kubernetes/kube-state-metrics/tree/master/docs

