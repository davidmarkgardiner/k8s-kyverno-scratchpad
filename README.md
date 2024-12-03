# Kyverno Dynamic Resource Management

This repository contains Kyverno policies for dynamically managing resource limits and requests in Kubernetes based on Prometheus metrics.

## Structure

- `policies/`: Contains Kyverno policy definitions
- `examples/`: Example deployments and pod definitions
- `prometheus/`: Prometheus configuration and queries

## Prerequisites

1. Kubernetes cluster
2. Kyverno installed
3. Prometheus installed
4. Metrics collection configured

## Installation

1. Install Kyverno:
```bash
helm repo add kyverno https://kyverno.github.io/kyverno/
helm install kyverno kyverno/kyverno --namespace kyverno --create-namespace
```

2. Apply the policies:
```bash
kubectl apply -f policies/
```

## Testing

1. Deploy the example application:
```bash
kubectl apply -f examples/test-deployment.yaml
```

2. Verify the resource limits are set:
```bash
kubectl get pod -o yaml
```

## Monitoring

Monitor policy application:
```bash
kubectl get policyreport -A
```