# Kubernetes YAML Configuration

This repository contains a Kubernetes YAML files used to deploy and manage resources within a Kubernetes cluster.

## Overview

This YAML file defines the configuration for a Kubernetes resource. Kubernetes uses these files to manage the state of the cluster, Create pods, ReplicaSets, Deployments and Namespaces

## Prerequisites

Before applying the configuration, ensure you have the following tools installed:

- **kubectl**: Command-line tool for interacting with the Kubernetes API
- **Kubernetes Cluster**: Ensure you have access to a Kubernetes cluster. You can use cloud providers such as AWS, GCP, or a local solution like **Minikube**.

### Installation

1. Install **kubectl**:  
   Follow the [official documentation](https://kubernetes.io/docs/tasks/tools/) to install `kubectl`.
2. Install **kubectl**:  
   Follow the [official documentation](https://minikube.sigs.k8s.io/docs/start/) to install `minikube`. you can use Minikube for local development or
3. Set up your **Kubernetes Cluster**:  
   Make sure you have a running cluster.  provision a cluster on a cloud platform like AWS EKS, GCP GKE, or Azure AKS.

## Usage

### Apply the YAML file

1. Clone the repository:
   ```bash
   git clone Kubernetes-labs
   cd Kubernetes-labs
   ```

2. Apply the configuration to your Kubernetes cluster:
   ```bash
   kubectl apply -f <your-file.yaml>
   ```

3. Verify that the resources have been created:
   ```bash
   kubectl get all
   ```

### Customize the YAML

You can modify the YAML file to suit your specific requirements. For example, you can change:

- **Replica count** for scaling the number of pods
- **Image name** to specify the container image you want to use
- **Resource limits** for CPU and memory allocations
- **Service type** for external or internal access

After modifying the file, reapply the configuration:
```bash
kubectl apply -f <your-modified-file.yaml>
```

### Deleting the resources

If you need to remove the resources created by the YAML file, use the following command:
```bash
kubectl delete -f <your-file.yaml>
```

## YAML Breakdown

### Key Components

- **apiVersion**: Specifies the Kubernetes API version being used.
- **kind**: Defines the type of resource, e.g., `Deployment`, `Service`, `ConfigMap`.
- **metadata**: Includes resource-specific information like `name` and `labels`.
- **spec**: Contains the configuration details for the resource such as `replicas`, `containers`, `ports`, and `volumes`.

## Troubleshooting

- **Resource not found**: Verify that the resource exists using `kubectl get all`.
- **Invalid YAML**: Ensure that the YAML syntax is correct. You can validate the syntax using online YAML validators or tools like `yamllint`.
- **Pod Errors**: Use `kubectl describe pod <pod-name>` or `kubectl logs <pod-name>` to debug issues with your pods.

## Additional Resources

- [Kubernetes Documentation](https://kubernetes.io/docs/home/)
- [kubectl Cheat Sheet](https://kubernetes.io/docs/reference/kubectl/cheatsheet/)
- [Minikube Setup](https://minikube.sigs.k8s.io/docs/start/)

---

