# Helm Charts

A collection of Helm charts for Kubernetes deployments.

## Charts

### nginx
- **Description**: A Helm chart for deploying nginx on Kubernetes
- **Version**: 0.1.0
- **App Version**: 1.16.0

## Prerequisites
- Kubernetes cluster
- Helm v3.18.6+

## Installation

```bash
# Add the chart repository (if published)
helm repo add charts https://example.com/charts

# Install the nginx chart
helm install my-nginx charts/nginx

# Install with custom values
helm install my-nginx charts/nginx --values custom-values.yaml
```

## Configuration

### nginx Chart Values

| Parameter | Description | Default |
|-----------|-------------|---------|
| `replicas` | Number of nginx replicas | `1` |
| `image.name` | nginx image name | `nginx` |
| `image.tag` | nginx image tag | `latest` |
| `port` | Container port | `80` |

## Development

### Testing
This repository uses chart-testing for linting and validation:

```bash
# Lint charts
ct lint --config ct.yaml --debug
```

### CI/CD
- **Helm CI**: Automated chart linting on pull requests
- **Release**: Automated chart packaging and publishing (configured in `.github/workflows/`)

## Chart Structure
```
charts/
|- nginx/
    |- Chart.yaml          # Chart metadata
    |- values.yaml         # Default configuration values
        |- templates/
            |- deployment.yaml # Kubernetes Deployment
            |- service.yaml    # Kubernetes Service
```
