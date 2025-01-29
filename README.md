# Kubernetes
This repository contains a series of commands and steps for setting up Kubernetes on an Ubuntu system using Minikube. The following instructions will guide you through installing Docker, Kubernetes, and Minikube to create a local Kubernetes cluster for development and testing purposes.

# Kubernetes Setup Using Minikube on Ubuntu

This repository contains a series of commands and steps for setting up Kubernetes on an Ubuntu system using Minikube. The following instructions will guide you through installing Docker, Kubernetes, and Minikube to create a local Kubernetes cluster for development and testing purposes.

## Prerequisites

Ensure you are using an Ubuntu system (preferably Ubuntu 18.04 or later). You should have root or sudo privileges to execute the commands.

## Steps

1. **Update your package list and install Docker:**

   First, update your system's package list and install Docker, a necessary container runtime for Kubernetes.

   ```bash
   sudo apt update
   sudo apt install docker.io
   sudo systemctl start docker
   sudo systemctl enable docker
   
2. **Install Kubernetes APT repository:**
   You need to install additional packages and add Kubernetes' official repository to get access to the latest Kubernetes versions.

   ```bash
   sudo apt install -y apt-transport-https ca-certificates curl
   curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo apt-key add -
   echo "deb https://apt.kubernetes.io/ kubernetes-xenial main" | sudo tee /etc/apt/sources.list.d/kubernetes.list

3.  **Install kubectl for Kubernetes command-line management:**
      Install kubectl, the Kubernetes command-line tool, using Snap.
   
      ```bash
      sudo snap install kubectl --classic
      kubectl version --client

4.  **Install Minikube:**
   Minikube is a tool that runs a local Kubernetes cluster on your machine. Install Minikube by downloading the latest version and installing it.
   
      ```bash
      curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
      sudo install minikube-linux-amd64 /usr/local/bin/minikube
      minikube versiont
      
5.  **Start Minikube with Docker as the driver:**
    Use Docker as the driver for Minikube to spin up a local Kubernetes cluster.
    ```bash
      minikube start --driver=docker

    If you encounter an error related to root privileges, you can force Minikube to start with the following command:
    ```bash
      minikube start --driver=docker --force
    
6.  **Verify Minikube and Kubernetes setup:**
    After starting Minikube, you can check the status of your cluster and verify the Kubernetes nodes and pods.
    ```bash
      minikube status
      kubectl cluster-info
      kubectl config view
      kubectl get nodes
      kubectl get pods

7.  **Access Minikube Dashboard:**
   ```bash
   minikube dashboard  
   

