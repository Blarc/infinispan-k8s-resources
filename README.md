# Infinispan Operator Kubernetes Resources

This repository contains Custom Resource Definitions (CRDs) for the Infinispan Kubernetes Operator. The CRDs are automatically generated from the [Infinispan Operator repository](https://github.com/infinispan/infinispan-operator) for each Infinispan release.

## How it Works

A GitHub workflow automatically:
1. Detects new Infinispan releases
2. Clones the Infinispan Operator repository
3. Generates the CRDs
4. Creates a new tag with the CRDs
5. Pushes the tag to this repository

## Using the CRDs

You can use these CRDs without needing the Operator Lifecycle Manager (OLM) by applying them directly to your Kubernetes cluster:

```bash
# Replace X.Y.Z with the Infinispan version you want to use
export INFINISPAN_VERSION=X.Y.Z

# Apply the CRDs
kubectl apply -f https://raw.githubusercontent.com/infinispan/infinispan-k8s-resources/${INFINISPAN_VERSION}/backups.infinispan.org-v1.yml
kubectl apply -f https://raw.githubusercontent.com/infinispan/infinispan-k8s-resources/${INFINISPAN_VERSION}/batches.infinispan.org-v1.yml
kubectl apply -f https://raw.githubusercontent.com/infinispan/infinispan-k8s-resources/${INFINISPAN_VERSION}/caches.infinispan.org-v1.yml
kubectl apply -f https://raw.githubusercontent.com/infinispan/infinispan-k8s-resources/${INFINISPAN_VERSION}/infinispans.infinispan.org-v1.yml
kubectl apply -f https://raw.githubusercontent.com/infinispan/infinispan-k8s-resources/${INFINISPAN_VERSION}/restores.infinispan.org-v1.yml
kubectl apply -f https://raw.githubusercontent.com/infinispan/infinispan-k8s-resources/${INFINISPAN_VERSION}/kubernetes.yml
```

## Manually Generating CRDs

If you need to manually generate CRDs for a specific Infinispan version, you can trigger the workflow manually:

1. Go to the "Actions" tab in this repository
2. Select the "Generate and Tag CRDs" workflow
3. Click "Run workflow"
4. Enter the Infinispan version you want to generate CRDs for
5. Click "Run workflow"

The CRDs will be generated and tagged with the specified version.
