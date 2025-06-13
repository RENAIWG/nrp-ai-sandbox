# Deploying Ollama with Helm

This guide explains how to deploy the [Ollama Helm chart](https://github.com/otwld/ollama-helm) using the provided `values.yaml` configuration.

## Prerequisites

- [Helm](https://helm.sh/) installed
- Access to a Kubernetes cluster with NVIDIA GPUs
- `kubectl` configured for your cluster

## Steps

1. **Add the Ollama Helm repository:**
   ```sh
   helm repo add otwld https://otwld.github.io/ollama-helm/
   helm repo update
   ```

2. **Clone or copy this directory:**
   Make sure your `values.yaml` is in the working directory.

3. **Install the chart:**
   ```sh
   helm install ollama otwld/ollama -f values.yaml
   ```

   - To upgrade an existing release:
     ```sh
     helm upgrade ollama otwld/ollama -f values.yaml
     ```

4. **Verify the deployment:**
   ```sh
   kubectl get pods
   kubectl get svc
   ```

5. **Access the service:**
   - The service will be available at the hostname specified in `values.yaml` (e.g., `i2-ollama.nrp-nautilus.io`).
   - Ensure your DNS and ingress controller are configured appropriately.

## Customization

- Edit `values.yaml` to change models, GPU settings, ingress, resources, or storage as needed.

## References

- [Ollama Helm Chart Documentation](https://github.com/otwld/ollama-helm)
- [Helm Documentation](https://helm.sh/docs/)
