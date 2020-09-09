# Introduction

Everything here shall help to quickly set up an OpenShift 4.x Cluster using ArgoCD and automation. 

Prereq:
 - OpenShift 4 Cluster with authenticated used
 - Ansible 

# Rollout and Configure ArgoCD Operator
Before everything starts, we need ArgoCD deployed in a newly created OpenShift cluster.
The following role deployes ArgoCD operator and creates the initial configuration. It will use the group "argocdadmins" which will be able to create objects in ArgoCD.

ansible-playbook roles/argocd-base-setup/apply/main.yaml

# Rollout OpenShift Logging with ArgoCD

Let's roll out openshift-logging, based on Elasticsearch, fluentd and Kibana. 
The following role creates the application in ArgoCD. However, no autosync is enabled so far. 

ansible-playbook roles/cluster_bootstrap/apply/openshift-logging.yaml

# Rollout everything with ArgoCD
ansible-playbook roles/cluster_bootstrap/apply/main.yaml
