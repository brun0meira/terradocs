# Passo a Passo

Este tutorial oferece uma introdução detalhada ao uso do Terraform para provisionar infraestrutura na AWS. Ao seguir esses passos, você poderá criar e gerenciar uma instância EC2 na AWS.

## Criando uma Instância EC2 com Terraform

1. Crie um arquivo de configuração Terraform chamado `main.tf` com o seguinte conteúdo:
```hcl
    provider "aws" {
        region = "us-east-1"
    }

    resource "aws_instance" "example" {
        ami           = "ami-0c02fb55956c7d316"  # Amazon Linux 2 AMI (HVM), SSD Volume Type
        instance_type = "t2.micro"

    tags = {
        Name = "TerraformExample"
    }
    }
```

## Inicializando o Terraform

1. Abra o terminal no diretório onde está o arquivo `main.tf` e execute:
```bash
terraform init
```

## Planejando a Infraestrutura

1. Para ver o que será criado, execute:
```bash
terraform plan
```

## Aplicando a Configuração

1. Para criar a instância EC2, execute:
```bash
terraform apply
```
2. Digite `yes` quando solicitado para confirmar a aplicação da configuração.

## Resolvendo Erros de AMI

1. Se você encontrar o erro `InvalidAMIID.NotFound`, significa que o ID da AMI não é válido para a região especificada. Para encontrar uma AMI válida, você pode usar o comando AWS CLI:
```bash
aws ec2 describe-images --owners amazon --filters "Name=name,Values=amzn2-ami-hvm-2.0.????????-x86_64-gp2"
```
2. Isso retornará uma lista de AMIs válidas que você pode usar. Substitua o ID da AMI em seu arquivo `main.tf` por uma das AMIs listadas.

## Limpando a Infraestrutura

1. Para destruir a instância criada, execute:
```bash
terraform destroy
```
2. Digite `yes` quando solicitado para confirmar a destruição da infraestrutura.
