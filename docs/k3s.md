# K3s 

Decided to use k3s for installing Kubernetes

## Installing K3s 

Just used the docs. Following link `https://docs.k3s.io`

Struggled a bit with the error `k3s: The connection to the server localost:8080 was refused - did you specify the right host or port?`.

Problem was a faulty kubeconfig configuration 
Fixed using with below command 
``` bash 
$ mkdir ~/.kube
$ sudo k3s kubectl config view --raw | tee ~/.kube/config
$ chmod 600 ~/.kube/config
```
And then add variable `export KUBECONFIG=~/.kube/config` to env 

# K3s - Lightweight Kubernetes

## Introduction

This document outlines the process of installing K3s, a lightweight and easy-to-install Kubernetes distribution, ideal for edge, IoT, and CI/CD environments.

## Prerequisites

- Ensure that you have administrative access to the host machine.
- Familiarity with basic Linux commands and environments is recommended.

## Installation of K3s

K3s simplifies the setup of a Kubernetes cluster. Follow the instructions from the official K3s documentation:

- **Documentation Link:** [K3s Official Documentation](https://docs.k3s.io)

### Common Installation Issue

During the installation, you might encounter an error related to the Kubernetes connection:

`k3s: The connection to the server localhost:8080 was refused - did you specify the right host or port?`

This error typically indicates a misconfiguration in the kubeconfig file.

### Resolving the Kubeconfig Error

Follow these steps to correct the kubeconfig file:

1. **Create a `.kube` directory in your home:**
   ```bash
   mkdir ~/.kube
2. **Extract and save the correct kubeconfig settings:**
   ```bash 
   sudo k3s kubectl config view --raw | tee ~/.kube/config 
3. **Set the correct file permissions:**
   ``` bash
   chmod 600 ~/.kube/config
4. **Configure the KUBECONFIG environment variable: Add the following line to your shell configuration file (e.g., .bashrc, .zshrc):**
   ``` bash 
   export KUBECONFIG=~/.kube/config
   