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

