# Rollout and Configure ArgoCD Operator
ansible-playbook roles/argocd-base-setup/apply/main.yaml

# Rollout OpenShift Logging with ArgoCD
ansible-playbook roles/cluster_bootstrap/apply/openshift-logging.yaml

# Rollout everything with ArgoCD
ansible-playbook roles/cluster_bootstrap/apply/main.yaml
