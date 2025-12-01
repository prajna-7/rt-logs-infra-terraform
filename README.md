# rt-logs-infra-terraform

Terraform repository for the **Real-Time Log Processing Platform on AWS**.

This repo will contain all infrastructure as code for the platform, including:

- VPC, subnets, internet/NAT gateways
- Amazon EKS cluster for the application workloads
- Amazon MSK (or Kafka on Kubernetes) for log streaming
- OpenSearch/Elasticsearch domain for log storage and search
- IAM roles and policies
- S3 + DynamoDB backend for Terraform remote state

## Structure

- `main.tf` – High-level composition of modules and resources.
- `providers.tf` – Provider configuration (AWS, Kubernetes, etc.).
- `backend.tf` – Remote state backend configuration (S3 + DynamoDB).
- `variables.tf` – Input variables for modules and environments.
- `outputs.tf` – Outputs exported by the infrastructure.

- `modules/`
  - `vpc/` – Networking (VPC, subnets, routing, gateways).
  - `eks/` – EKS cluster, node groups, auth.
  - `msk/` – MSK/Kafka resources.
  - `opensearch/` – OpenSearch/Elasticsearch domain and related resources.

- `envs/`
  - `dev.tfvars` – Example environment configuration for the `dev` environment.

## Next steps (future phases)

- Implement Terraform modules for VPC, EKS, MSK, and OpenSearch.
- Configure remote backend (S3 + DynamoDB).
- Add GitHub Actions workflows for `terraform fmt`, `init`, `validate`, and `plan`.
