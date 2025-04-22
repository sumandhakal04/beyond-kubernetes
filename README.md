
# Beyond Kubernetes

This repository offers a structured approach to deploying and managing Kubernetes clusters components using GitOps principles, with Helm and Kustomize.

## 📁 Repository Structure

- **infrastructure/**: Responsible for creating the cluster components used by the applications,

- **clusters/**: Houses environment-specific configurations and manifests for Kubernetes clusters, facilitating multi-environment deployments.

- **apps/**: Includes Helm charts and Kubernetes manifests for deploying applications and services onto the clusters.

- **scripts/**: Downloads the Flux OpenAPI schemas, then it validates the Flux custom resources and the kustomize overlays using kubeconform.

## 🚀 Getting Started

1. **Clone the Repository**:

   ```bash
   git clone https://github.com/sumandhakal04/beyond-kubernetes.git
   cd beyond-kubernetes
   ```

2. **Set up Flux using bootstrap scripts**:
    https://fluxcd.io/flux/installation/bootstrap/

3. **Configure Clusters**:

   Configure apps.yaml and patch infrastructure.yaml to patch the infrastructure to create cluster components.

4. **Set Up Infrastructure**:

   Cluster components resources are added inside `infrastructure/` directory.

4. **Deploy Applications**:

   Any platform applications are deploy using the Helm charts and patch in the `apps/` directory.

5. **Utilize Automation Scripts**:

   Run validate.sh inside `scripts/` to validate flux custom resource changes before each push

## 🧰 Tools and Technologies

- **Helm**: Package manager for Kubernetes, used for deploying applications.

- **GitHub Actions**: CI/CD workflows to automate deployments and other tasks.

- **Kustomize**: Patches the chart’s manifests once they are fully rendered by Helm.

- **FluxCD**: A pull-based, Kubernetes-native, and self-healing GitOps tool.

**Detailed explanation**: https://howtodoitincloud.medium.com/beyond-kubernetes-installing-cluster-components-782885a1d67b