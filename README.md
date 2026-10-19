# Getting Started with Terraform

Docker provider を使い、ローカルに nginx コンテナを立てながら Terraform の基本（provider / resource / module / 環境分割）を学びます。

## Prerequisites

- [Terraform](https://developer.hashicorp.com/terraform/install) (>= 1.14.0)
- Docker（Docker Desktop または Rancher Desktop）

## Clone

```bash
git clone https://github.com/CyberAgentHack/getting-started-with-terraform.git
cd getting-started-with-terraform
```

## Structure

```
.
├── environments/
│   ├── xxx/nginx/   # 環境 xxx（localhost:8000）
│   └── yyy/nginx/   # 環境 yyy
└── modules/
    └── nginx/       # nginx コンテナを作る module
```

## Usage

```bash
cd environments/xxx/nginx
terraform init
terraform apply
curl http://localhost:8000

terraform destroy
```

Rancher Desktop の場合は `docker_host` を上書きします。

```bash
terraform apply -var="docker_host=unix://$HOME/.rd/docker.sock"
```
