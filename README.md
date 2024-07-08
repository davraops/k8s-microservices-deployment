# Kubernetes Microservices Deployment

This repository contains Kubernetes deployment configurations for deploying microservices using both plain YAML files and Helm charts.

## Deploying with Kubernetes YAML Files

1. Apply the YAML files:

   ```sh
   kubectl apply -f deployments/microservice1.yaml
   kubectl apply -f deployments/microservice2.yaml

## Deploying with Helm

1. Install Helm if you haven't already:

   ```sh
   curl https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3 | bash
   ```

2. Deploy the Helm chart:

   ```sh
   helm install myrelease helm/mychart
   ```
   
## Customizing the Helm Chart

You can customize the Helm chart by editing the values.yaml file in helm/mychart/.

For example, to change the image or replica count for a microservice, modify the corresponding values in `values.yaml`:

```yaml
microservices:
  - name: microservice1
    image: your-docker-registry/microservice1:latest
    replicas: 3
    port: 80
  - name: microservice2
    image: your-docker-registry/microservice2:latest
    replicas: 3
    port: 80
```