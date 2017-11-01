# kubernetes-elk
This REPO holds collection of files and instructions for deploying an ELK Stack on K8s. ElasticSearch for Storage/Search, fluentd for collection from each K8s Node, and Kibana for Visualization.


## Instructions for Deployment
+ $ git clone https://github.com/kubernetes/kubernetes.git
+ $ cd ./kubernetes/cluster/addons/fluentd-elasticsearch
+ $ kubectl apply -f ./es-statefulset.yaml
+ $ kubectl apply -f ./es-service.yaml
+ $ kubectl apply -f ./kibana-deployment.yaml
+ $ kubectl apply -f ./kibana-service.yaml
+ $ kubectl apply -f fluentd-daemonset-elasticsearch.yaml
+ $ kubectl proxy
+ In CHROME navigate to http://localhost:8001/api/v1/proxy/namespaces/kube-system/services/kibana-logging/app/kibana#/management/kibana

## Outstanding - Things to do
+ Use Labels to restrict which Nodes get the fluentd collector deployed
+ Use Ingress Controller or Nginx / Haproxy LB to expose Kibana UI interface
+ User Persistent Storage for Elastic Search and Kibana
+

