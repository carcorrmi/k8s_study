# k8s_study

This repository provides a minimal project to practice basic Kubernetes concepts.
The `examples` directory contains a Kind configuration and a starter Helm chart.

## Prerequisites (macOS)

1. Install [Homebrew](https://brew.sh) if it's not already available.
2. Install Docker Desktop and start it so the Docker daemon is running:
   ```bash
   brew install --cask docker
   ```
3. Install `kind`, `kubectl`, and `helm` using Homebrew:
   ```bash
   brew install kind kubectl helm
   ```
4. Verify the tools are installed:
   ```bash
   docker --version
   kind --version
   kubectl version --client
   helm version
   ```


## Study Path

1. **Set up a local cluster**
   - Create a cluster using the provided config. It maps port `80` from the
     cluster to your laptop and starts two worker nodes for a more realistic
     environment:
     ```bash
     kind create cluster --config examples/kind-cluster.yaml
     ```
   - If you build Docker images locally, load them into the cluster with:
     ```bash
     kind load docker-image <image-name>
     ```

2. **Explore the cluster**
   - Use `kubectl get nodes` and `kubectl get pods -A` to inspect the environment.
   - Deploy simple manifests and experiment with scaling and updating pods.

3. **Learn Helm basics**
   - Review the example chart in `examples/helm`.
   - Install it with:
     ```bash
     helm install demo-chart examples/helm
     ```
   - Modify `values.yaml` and upgrade the release to see how Helm manages changes.

4. **Next steps**
   - Add more resources to the chart (e.g., a Service or Ingress).
   - Experiment with additional kinds of nodes in the Kind configuration.
   - Read the official Kubernetes and Helm documentation for deeper knowledge.
