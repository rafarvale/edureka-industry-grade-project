# Edureka Industry Grade Project (CI/CD + Docker + K8s + Monitoring) by Rafael Vale

## Overview
This repository contains the implementation of the Edureka Industry Grade Project:
- Maven CI pipeline in Jenkins (compile -> test -> package)
- Docker image build/push
- Ansible deployment
- Kubernetes deployment/service
- Monitoring with Prometheus + Node Exporter + Grafana

## Repository Structure
- `src-java/` : Java Maven application source
- `docker/` : Dockerfile used to build the image
- `ansible/` : inventory + playbooks
- `k8s/` : Kubernetes manifests (deployment/service)
- `evidence/` : screenshots proving execution (Jenkins, K8s, Prometheus, Grafana)

## Prerequisites
- Ubuntu server(s) in AWS (Master + Slave)
- Jenkins configured with jobs:
  1.Compile -> 2.Test -> 3.Package -> 4.Deploy_Ansible -> 5.Deploy_K8s
- Docker Hub image: `rafavale/abcapp:1.0`
- Kubernetes cluster initialized using kubeadm (Master control-plane + Slave worker)
- Prometheus scraping Node Exporter from both nodes
- Grafana dashboard configured

## How to Deploy (high level)
### Deploy to Docker (Ansible)
```bash
ansible-playbook -i ansible/inventory.ini ansible/deploy_docker.yml

