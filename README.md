# Home lab

This repo contains all of the configuration and documentation of my home lab

## Tooling 

- [k3s](https://docs.k3s.io/)
- [Flux](https://fluxcd.io/)

## Goals 
- Run Prometheus and grafana stack 
   - 
- Run own project [Todoist](https://github.com/yuandrk/teledoist) and [OpenWeb](https://openwebui.com/) 
   - Have stacks available with URL
      - ingress 
      - TLS 
      - DNS (AWS Route 53)
- Everything should be deployed using GitOps 
   - Flux 
   - Solution for secrets 

## Todo 

- [x] Flux Installed  
- [x] Terraform  
- [ ] SOPS for Secrets 

## Source: 
- [Flux monitoring stack](https://github.com/fluxcd/flux2-monitoring-example/blob/main/README.md)
- [OpenWeb](https://github.com/open-webui/open-webui)
- [Grafana](https://grafana.com/)
- [Prometeus](https://prometheus.io/)


### inspired by [Mischa van den Burg](https://www.youtube.com/@mischavandenburg)

## Log 

### 2024-07-21
- set up k3s on the master node and worker node
- set up the repository and added documentation of earlier install  
### 2024-07-24 
- Deploy monitoring stack 
- update flux module to 1.3.0
