# k8s_study

This repository provides a minimal project to practice basic Kubernetes concepts.
The `examples` directory contains a simple Kind configuration and a starter Helm chart.

## Study Path

1. **Set up a local cluster**
   - Install Docker and the `kind` tool.
   - Create a cluster using the config:
     ```bash
     kind create cluster --config examples/kind-cluster.yaml
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
